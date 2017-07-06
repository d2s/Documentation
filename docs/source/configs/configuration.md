### Configurations (tasks)

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
