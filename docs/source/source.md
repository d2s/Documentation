# Documentation of RsyncOSX source

This is documentation of the design and code of RsyncOSX. I have just commenced the process (June 2017) and it will take time to complete. Why am I doing it? Well, primary for fun but i might learn something from it as well. The design of RsyncOSX is based upon ideas of the [MVC](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller) pattern. One of the objectives in MVC is to separate the views and models.

First will the data model and some of the methods operating on the data be documented. After that some of the high level details about how RsyncOSX is working. RsyncOSX kicks off the `rsync` utility to do the real work. The `rsync` is executed in a `Process` object. Every time RsyncOSX [executes](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ProcessCmd.swift) a command, RsyncOSX is listening for two notifications `didTerminateNotification` and `NSFileHandleDataAvailable`. Those two notifications kicks of other functions depended upon the state of RsyncOSX.

Further documentation of code is put on hold until Xcode 9 and Swift 4 are released. There are quite a few changes to code compared to master branch and even more to do. The main reason for refactor code is to make code compliant with [SwiftLint](https://github.com/realm/SwiftLint) guidelines for coding in Swift.

# Data model

The views has no knowledge about the models or data stored about configurations, schedules and logdata. Data presented in RsyncOSX are mostly table data. Presenting table data in all views utilizes the `NSTableViewDelegate`. All data which are saved to permanent storage are saved as xml-files ([plist](https://en.wikipedia.org/wiki/Property_list) files). RsyncOSX does not utilize the Core Data because the data about `configurations`, `schedules` and `logs` are simple and there is no need for a complex datamodel.

All data is loaded in memory when default view is loaded or if a new profile is either selected or created. There are two main objects which holds the information about configurations and schedules including logdata. The objects lives only during lifetime of RsyncOSX or until a profile is either selected or created. Classes in swift are `by reference` and both objects are created in the main view of RsyncOSX. Other objects utilizing data and methods in objects are by protocol functions getting the reference for the objects.

## Configurations

A configuration holds required data about all tasks including all parameters for rsync and user selected parameters. Adding a task results in two new records, one for backup and for restore. All configurations are stored in memory in an Array of Configurations in order loaded from permanent storage. Last timestamp for execution is also stored in configuration.

Documentation of [Configurations](configs/configuration.md).

## Scheduled tasks and log records

All log records are stored in a Schedule record. For one task it might be several schedule records depended upon type of schedule and start of scheduled task. Only backup tasks can be scheduled, not restore task. The type of schedules are `manual`,`once`, `daily` and `monthly`. If Schedules is not used meaning only manually executed tasks, one Schedule record is created with type `manual`. All log records for this manually executed tasks are added to this record.

Documentation of [scheduled tasks and log records](configs/configurationSchedule.md).


## Reading and writing data to permanent storage

One object takes care of reading and writing data to permanent storage. The object is also responsible to either read or write data utilizing profiles.

Documentation of [reading and writing](configs/readwrite.md).

# Parameters to rsync

Rsync utilizes a ton of parameters. RsyncOSX let the user pass any parameter to rsync. A few rsync parameters are predefined, both mandatory and user selected. Documentation of which rsync parameters are mandatory and predefined is [here](../Parameters.md).

Documentation of [rsync parameters in RsyncOSX](parameters/parameters.md).
