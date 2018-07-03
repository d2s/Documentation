---
layout: post
title:  "User configuration"
permalink: UserConfiguration
---
There are only a few parameters to choose in user configuration. The parameters are:

 - **v3.1.2 or 3.1.3** of rsync
 	- any version of rsync should work, but only rsync  version 3.1.2, version 3.1.3 protocol version 31 and rsync  version 2.6.9  protocol version 29 are tested and verified
- **optional path for rsync**
  - if other version of rsync is installed in other path than `/usr/local/bin` it must be set here
 - **detailed logging on or off**
 	- if detailed logging is **on** all backup tasks are logged, if **off** only last date for task is updated in Execute view
- **temporary path restore**
  - preset temporary path for [restoring single files or volumes](/CopySingleFiles)
  - preset temporary path for [full restore](/Fullrestore)
- Scheduled tasks (default on: dispatch, if off: timer)
  - don´t bother to switch, it is only how (technical) scheduled tasks are kicked off
- **loggfile**
  - either minimum (last 10 lines) or full logging of output from rsync, be carful not logging everything, the log file might be big
  - loggfile is `Documents/rsynclog.txt`
  - logging to file is off when RsyncOSX starts
- **Number of days**
  - in main view tasks older than number of days are marked red
- **path RsyncOSX**
- **path RsyncOSXsched**
  - the path for both apps should be set if scheduled tasks are executed in RsyncOSXsched, green light indicates apps are found in path
  - see [scheduled backups](/ScheduleTasks) and [menu app](/Menuapp) for more info

If the user selects another version of rsync, RsyncOSX does check if there is a rsync in path set by user. If there is no rsync in path RsyncOSX will not execute any tasks.

![](/images/RsyncOSX/master/userconfig/user.png)

In right corner down the version of rsync utilized is presented.

### No rsync i path

The views below is what happens if a not valid rsync path is set. An error is presented in bottom of user configuration.
![](/images/RsyncOSX/master/userconfig/user2.png)
If there still is a missing rsync in optional path no execution of tasks is allowed (it gives no meaning of executing a task without a rsync).
![](/images/RsyncOSX/master/userconfig/user4.png)
