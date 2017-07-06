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

Documentation of [reading and writing](configs/readwrite.md).
