### Configurations (tasks)


The configurations are read from the permanent storage and kept in memory until a new profile is loaded or RsyncOSX is quit. Each record (one task) are read from permanent storage as a `NSDictionary` item and loaded into an `Array<configuration>`. A [Configuration](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/Configuration.swift) is a struct holding all data about one task.

The object [Configurations.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/Configurations.swift) holds all data and methods operating on configurations. Every time a configuration is read the rsync arguments are [computed](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/RsyncProcessArguments.swift) and hold by the struct [ArgumentsOneConfiguration.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ArgumentsOneConfiguration.swift) in memory. There are four types of arguments which are computed during startup, arguments for `--dry-run` and real run and both arguments for presentation on screen. Each configuration is allocated a uniq computed nonsense key `hiddenID = Int`.

The object [Configurations.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/Configurations.swift) is responsible for reading and computing arguments for all tasks.

The object [Configurations.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/Configurations.swift) creates an `Array<NSMutableDictionary>` which holds all data about `Configuration` and computed values of arguments. Computed values are **not** saved to permanent storage. They are computed when RsyncOSX starts or a new profile is loaded. The object holds all data and methods about all tasks and parameters.

### Changes to configurations

All changes to configurations (edit, delete, new, parameters to rsync) is a three step operation:

- any changes to configurations are updated in memory (to the `Array<configuration>`)
  - [Configurations.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/Configurations.swift) is a struct holding all attributes for one configuration
  - the `Array<NSMutableDictionary>` is computed and read-only after loaded in memory
- after a change of [Configurations.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/Configurations.swift) in memory, the changed configuration in memory is saved to permanent storage
- the object [Configurations.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/Configurations.swift) is created and new values are computed
  - a new, computed and read only `Array<NSMutableDictionary>` is loaded

No code needed for partly update and it secures a 100% correct and updated configuration in memory at all time.
