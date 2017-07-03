# Documentation of RsyncOSX source

This is documentation of the design and code of RsyncOSX. I have just commenced the documentation (June 2017) and it will take time to complete. Why am I doing it? Well, primary for fun but i might learn something from it as well. The design of RsyncOSX is based upon ideas of the [MVC](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller) pattern. One of the objectives in MVC is to separate the views and models.

First will the data (model) and some of the methods operating on the data be documented. Then details about how RsyncOSX is working. RsyncOSX kicks off the `rsync` utility to do the real work. The `rsync` is executed in a `Process` object. Every time RsyncOSX [executes](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/processCmd.swift) a command, RsyncOSX is listening for two notifications `didTerminateNotification` and `NSFileHandleDataAvailable`. Those two notifications kicks of other functions depended upon the state of RsyncOSX.

# High Level design

The views has no knowledge about the models or data stored about configurations, schedules and logdata. All data presented in RsyncOSX are mostly table data. Presenting table data utilizes the `NSTableViewDelegate`. All data which are saved to permanent store are saved as xml-files ([plist](https://en.wikipedia.org/wiki/Property_list) files). RsyncOSX does **not** utilize the Core Data because the data about `configurations`, `schedules` and `logs` are simple and there is no need for a complex datamodel.

## Configurations (tasks)

The configurations are read from the permanent store and kept in memory during RsyncOSX lifetime. Each record (one task) are read from permanent store as a `NSDictionary` item and loaded into an `Array<configuration>`. A [configuration](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/configuration.swift) is a struct holding all data about one task.

The object [SharingManagerConfigurations.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/SharingManagerConfiguration.swift) holds all data and methods operating on configurations. The method `readAllConfigurationsAndArguments` loads all data about configurations in memory. Every time a configuration is read the rsync arguments are computed and hold by the struct [argumentsOneConfiguration.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/argumentsOneConfiguration.swift) in memory. There are four types of arguments which are computed during startup, arguments for `--dry-run` and real run and both arguments for presentation on screen. Each configuration is allocated a uniq computed nonsense key `hiddenID = Int`.

The object [SharingManagerConfigurations.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/SharingManagerConfiguration.swift) creates an `Array<NSMutableDictionary>` which holds all data about `configuration` and computed values of arguments. Computed values are **not** saved to permanent store. They are computed when RsyncOSX starts or a new profile is loaded. The method `getConfigurationsDataSource()` returns the computed `Array<NSMutableDictionary>` and it is the data object which is loaded by the `NSTableViewDelegate` delegate methods into tables. As an example see [ViewControllertabMain.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ViewControllertabMain.swift) and `func tableView(_ tableView: NSTableView, objectValueFor tableColumn: NSTableColumn?, row: Int) -> Any?` how data is loaded into tables.

### Changes to configurations

All changes to configurations (edit, delete, new, parameters to rsync) is a three step operation:

- any changes to configurations are updated in memory (to the `Array<configuration>`)
  - [configuration](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/configuration.swift) is a struct holding all attributes for one configuration
  - the `Array<NSMutableDictionary>` is computed and read-only after loaded in memory
- after a change of [configuration](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/configuration.swift) in memory, the changed configuration in memory is saved to permanent store
- all configurations in memory are wiped out and loaded into memory from the permanent store to compute any new values due to changes
  - a new, computed and read only `Array<NSMutableDictionary>` is loaded
  - a refresh of present tableView is executed to update table in view

This is a kind of brute force. No code needed for partly update and it secures a 100% correct and updated configuration in memory at all time. Saving, wiping memory and reading configurations is done in matter of milliseconds.

## Schedules and log data

Schedules and log data are loaded into a separate data structure. [Schedules](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/configurationSchedule.swift) are linked to [configuration](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/configuration.swift) by `hiddenID=Int`. Schedules and logs are also saved in a separate XML-file (plist). Manually executed task is stamped with date (US-format) `01 Jan 1900 00:00`". Record of scheduled backups are stamped with date for execution, example `01 Jun 2017 22:35` and type of schedule, either `once`, `daily` or `monthly`. Manually executed task is of type `manuel`.

A log record is constructed by number of files, size of transferred files in time (`58 files : 5.04 MB in 2.50 seconds`) as reported from rsync. The output from rsync is checked and all numbers are copied from the rsync output. Every log record is linked to its parent bye the function `computeKey` and used when records are deleted.

A **log record** is appended to the **schedule record** as a `NSMutableDictionary`.

The object [SharingManagerSchedule.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/SharingManagerSchedule.swift) holds all data and operations working on Schedule data. The object [ScheduleWriteLoggData.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ScheduleWriteLoggData.swift) takes care of adding and deleting log records. As for configurations changes are applied to structure in memory and then saved to permanent store.

If a **schedule record** is marked for delete a delete flag is set on the record. When saved all records marked for delete are omitted. The schedules are marked dirty and a write operation is performed. All **log records** connected to the deleted schedule are also deleted. Schedule data in memory is wiped and reloaded from permanent store into memory. Single log records might be deleted as well. The log record is removed in memory, schedules are marked dirty and write operation is performed.

This is also a kind of brute force method. It is effective and there is no need to handle changes to data structure loaded in memory. Wipe memory, reread from permanent store and reload data into memory. If a refresh of table data is performed in view after a delete of a record the refresh will cause a nil pointer exception if not explicit taken care of. The actual number of records to refresh is `N-1` and the delegate method `numberOfRows` still think number of rows are `N`. A reread of data and then force a refresh of current table view solve the problem.

### Scheduled backups

The object [ScheduleSortedAndExpanded.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ScheduleSortedAndExpanded.swift) reads the schedules, expands scheduled tasks, sorts them by date and time and creates a result stack. The object is created every time a schedule is changed and a read from permanent store is performed. A `daily` task which is set to kick of at 12:00 o'clock for å period of time is one record only in schedule. If this period is from mid June to mid July it is scheduled to start about 30 times during this period. When the sorted and expanded object is created only scheduled tasks with start date in future are put on stack. The first task is the first element on stack.

The scheduled task (record on stack) holds three attributes (as a `NSDictionary`) -  the `hiddenID`, which is key to task, time to start and schedule either `once`, `daily` or `monthly`.

If the object `ScheduleSortedAndExpanded.swift` is not nil there is scheduled tasks. RsyncOSX pops off the first element of stack, calculates the number of seconds to start and creates a [Timer](https://developer.apple.com/documentation/foundation/timer) object. The timer object is set to wait for number of seconds and when time is due kick off the scheduled task. When the scheduled task is completed the next task on top of stack is popped off. Another timer object is created and waits for å number of seconds. And so forth.

If the user deletes a task any scheduled operations are deleted as well.

When a scheduled task is executing the user is not allowed to manually execute a task. RsyncOSX does also notify in view when a scheduled task is executing.

A scheduled task is object of type [Operation](https://developer.apple.com/documentation/foundation/operation). When the time is due for scheduled task to execute RsyncOSX creates an [OperationQueue](https://developer.apple.com/documentation/foundation/operationqueue) and appends the [operation object](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/executeTask.swift) to the [queue object](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ScheduleOperation.swift). The queue object checks that all required conditions are met before executing the `main()` method in Operation object.

## Reading and writing data to permanent store

RsyncOSX holds all data i memory as a [Singelton](https://en.wikipedia.org/wiki/Singleton_pattern) object. When data is loaded from permanent store all arguments are computed. The object [readwritefiles.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/readwritefiles.swift) decides if data should be read from memory or permanent store. All data (configurations, schedules and logs, user config) is read from permanent store utilizing the [NSDictionary](https://developer.apple.com/documentation/foundation/nsdictionary) foundation class. The singelton class saves the state of data is dirty or not. If not dirty RsyncOSX get the data from memory, if dirty a reread of data is forced before RsyncOSX get data from memory. By this data is only read from permanent store if there has been a change in data.
