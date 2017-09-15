### Configurations (tasks)


The configurations are read from the permanent storage and kept in memory until a new profile is loaded or RsyncOSX quits. Each record (one task) are read from permanent storage as a `NSDictionary` item and loaded into an `Array<configuration>`.

* the **struct** [Configuration.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/Configuration.swift) holds data about one task
* the **object** [Configurations.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/Configurations.swift) holds all computed data and methods operating on tasks
  * the object is also responsible for initiate reading data from permanent store when the object is created
  * the object is also responsible for initiate a write operation after any change in configurations

Every time a configurations are read from permanent store, the rsync arguments are [computed](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/RsyncProcessArguments.swift) and hold by the struct [ArgumentsOneConfiguration.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ArgumentsOneConfiguration.swift) in memory. There are four types of arguments which are computed during startup, arguments for `--dry-run` and real run and both arguments for presentation on screen. Each configuration is allocated a uniq computed nonsense key `hiddenID = Int`.

The object [Configurations.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/Configurations.swift) creates an `Array<NSMutableDictionary>` which holds all data about `Configuration` and computed values of arguments. Computed values are **not** saved to permanent storage. They are computed when RsyncOSX starts or a new profile is loaded. The object holds all data and methods about all tasks and parameters.

### Changes to configurations

Changes to configurations (edit, delete, new, parameters to rsync) is a three step operation:

- any change, delete or add operations to configurations are updated in memory (to the `Array<Configuration>`)
  - [Configuration.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/Configuration.swift) is a struct holding all attributes for one task
- any change, delete or add operation causes a write operation to permanent store of all configurations
- the object [Configurations.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/Configurations.swift) is created and new values are computed

No code needed for partly update and it secures a 100% correct and updated configuration in memory at all time.
