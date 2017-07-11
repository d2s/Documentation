# Documentation of RsyncOSX source

This is documentation of the design and code of RsyncOSX. I have just commenced the process (June 2017) and it will take time to complete. Why am I doing it? Well, primary for fun but i might learn something from it as well. The design of RsyncOSX is based upon ideas of the [MVC](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller) pattern. One of the objectives in MVC is to separate the views and models.

First will the data model and some of the methods operating on the data be documented. After that some of the high level details about how RsyncOSX is working. RsyncOSX kicks off the `rsync` utility to do the real work. The `rsync` is executed in a `Process` object. Every time RsyncOSX [executes](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/processCmd.swift) a command, RsyncOSX is listening for two notifications `didTerminateNotification` and `NSFileHandleDataAvailable`. Those two notifications kicks of other functions depended upon the state of RsyncOSX.

# Data model

The views has no knowledge about the models or data stored about configurations, schedules and logdata. Data presented in RsyncOSX are mostly table data. Presenting table data in all views utilizes the `NSTableViewDelegate`. All data which are saved to permanent storage are saved as xml-files ([plist](https://en.wikipedia.org/wiki/Property_list) files). RsyncOSX does not utilize the Core Data because the data about `configurations`, `schedules` and `logs` are simple and there is no need for a complex datamodel.

All data is kept in memory (utilizing singelton objects) during lifetime of RsyncOSX. The main reason for this approach is that all views in RsyncOSX is guaranteed correct and updated data any time. When data is changed, in any view or by any operation, the singelton objects saves data to permanent storage and make sure saved data is loaded into memory again before any other operations is performed.

## Configurations

A configuration holds required data about all tasks including all parameters for rsync and user selected parameters. Adding a task results in two new records, one for backup and for restore. All configurations are stored in memory in an Array of configurations in order loaded from permanent storage. Last timestamp for execution is also stored in configuration.

Documentation of [configurations](configs/configuration.md).

## Scheduled tasks and log records

All log records are stored in a Schedule record. For one task it might be several schedule records depended upon type of schedule and start of scheduled task. Only backup tasks can be scheduled, not restore task. The type of schedules are `manual`,`once`, `daily` and `monthly`. If Schedules is not used meaning only manually executed tasks, one Schedule record is created with type `manual`. All log records for this manually executed tasks are added to this record.

Documentation of [scheduled tasks and log records](configs/configurationSchedule.md).


## Reading and writing data to permanent storage

One object takes care of reading and writing data to permanent storage. The object is also responsible to either read or write data utilizing profiles.

Documentation of [reading and writing](configs/readwrite.md).
