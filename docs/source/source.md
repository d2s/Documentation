# Documentation of RsyncOSX source

This is documentation of the design and code of RsyncOSX. I have just commenced the documentation (June 2017) and it will take time to complete. Why am I doing it? Well, primary for fun but i might learn something from it as well. The design of RsyncOSX is based upon ideas of the [MVC](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller) pattern. One of the objectives in MVC is to separate the views and models.

First will the data (model) and some of the methods operating on the data be documented. Then details about how RsyncOSX is working. RsyncOSX kicks off the `rsync` utility to do the real work. The `rsync` is executed in a `Process` object. Every time RsyncOSX [executes](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/processCmd.swift) a command, RsyncOSX is listening for two notifications `didTerminateNotification` and `NSFileHandleDataAvailable`. Those two notifications kicks of other functions depended upon the state of RsyncOSX.

# High Level design

The views has no knowledge about the models or data stored about configurations, schedules and logdata. All data presented in RsyncOSX are mostly table data. Presenting table data utilizes the `NSTableViewDelegate`. All data which are saved to permanent store are saved as xml-files ([plist](https://en.wikipedia.org/wiki/Property_list) files). RsyncOSX does **not** utilize the Core Data because the data about `configurations`, `schedules` and `logs` are simple and there is no need for a complex datamodel.

## Configurations

Documentation of [configurations](configs/configuration.md).

## Scheduled tasks and log records

Documentation of [scheduled tasks](configs/configurationSchedule.md).


## Reading and writing data to permanent store

RsyncOSX holds all data i memory as a [Singelton](https://en.wikipedia.org/wiki/Singleton_pattern) object. When data is loaded from permanent store all arguments are computed. The object [readwritefiles.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/readwritefiles.swift) decides if data should be read from memory or permanent store. All data (configurations, schedules and logs, user config) is read from permanent store utilizing the [NSDictionary](https://developer.apple.com/documentation/foundation/nsdictionary) foundation class. The singelton class saves the state of data is dirty or not. If not dirty RsyncOSX get the data from memory, if dirty a reread of data is forced before RsyncOSX get data from memory. By this data is only read from permanent store if there has been a change in data.

RsyncOSX configuration file, scheduled tasks which also includes log records and user configuration are plain XML-files ([property list files](https://en.wikipedia.org/wiki/Property_list)). Files are saved in:

- `~/Documents/Rsync/MacID/configRsync.plist` - configurations
  - `~/` is user home directory
  - `MacID` is the Mac serial number and is automatically set by RsyncOSX
- `~/Documents/Rsync/MacID/scheduleRsync.plist` - scheduled tasks including log records
- `~/Documents/Rsync/MacID/config.plist` - user config

If _profile_ is used:

- `~/Documents/Rsync/MacID/profile/configRsync.plist`
- `~/Documents/Rsync/MacID/profile/scheduleRsync.plist`
  - `profile` is the profile name
- `~/Documents/Rsync/MacID/config.plist` - user config
