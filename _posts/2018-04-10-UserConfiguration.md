---
layout: post
title:  "User configuration"
permalink: UserConfiguration
---
Index of [RsyncOSX documentation](/AboutRsyncOSX).

There are only a few parameters to choose in user configuration. The parameters are:

 - another version of rsync
 	- any version of rsync should work, but only _rsync  version 3.1.2  protocol version 31_ and _rsync  version 2.6.9  protocol version 29_ is tested and verified.
 - detailed logging on or off
 	- if detailed logging is **on** all _backup_ tasks are logged, if **off** only last date for task is updated in Execute view
- temporary path restore
  - preset path for [restoring single files or volumes](CopySingleFiles.md)
- Scheduled tasks (default on: dispatch, if off: timer)
  - don´t bother to switch, it is only how (technical) scheduled tasks are kicked off
- loggfile
  - either minimum (last 10 lines) or full logging of output from rsync, be carful not logging everything, the log file might be big
  - loggfile is `Documents/rsynclog.txt`
  - logging to file is *off* when RsyncOSX starts
- Number of days
  - in main view tasks older than number of days are marked red

If the user selects another version of rsync, RsyncOSX does check if there is a rsync in path set by user. If there is no rsync in path RsyncOSX will not execute any tasks. The red _configurations_ (rows in table) is only because I have not started my VirtualBox FreeBSD instance and RsyncOSX does not receive any answer (check is done automatically)
![](/images/screenshots/master/userconfig/user.png)

### No rsync i path

The views below is what happens if a not valid rsync path is set. An error is presented in bottom of user configuration.
![](/images/screenshots/master/userconfig/user2.png)
If there still is a missing rsync in optional path no execution of tasks is allowed (it gives no meaning of executing a task without a rsync).
![](/images/screenshots/master/userconfig/user3.png)
