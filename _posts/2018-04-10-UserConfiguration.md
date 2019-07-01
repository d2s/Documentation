---
layout: post
title:  "User configuration"
permalink: UserConfiguration
---
There are only a few parameters to choose in user configuration. Configurations are saved to permanent store.

![](/images/RsyncOSX/master/userconfig/user.png)

## Rsync, paths and logging

 - 3.1.2 or 3.1.3 of rsync
   	- any version of rsync should work, but only rsync  version 3.1.2, version 3.1.3 protocol version 31 and rsync  version 2.6.9  protocol version 29 are tested and verified
    - utilizing the [snapshot feature](/Snapshots) require either version 3.1.2 or 3.1.3
- optional path for rsync
    - if other version of rsync is installed in other path than `/usr/local/bin` it must be set here
- detailed logging on or off
   	- if detailed logging is on all backup tasks are logged, if off only last date for task is updated in Execute view
- temporary path restore
    - preset temporary path for restoring single files or volumes
    - preset temporary path for [full restore](/Fullrestore)
- Scheduled tasks (default on: dispatch, if off: timer)
    - don´t bother to switch, it is only how (technical) scheduled tasks are kicked off

If there is a not valid rsync path is set an error is presented in bottom of user configuration. If there still is missing rsync in optional path no execution of tasks is allowed.

## Logging to file

Logging is saved to permanent store.

- either minimum (last 10 lines) or full logging of output from rsync, be carful not logging everything, the log file might be big
- log file is `Documents/rsynclog.txt`
- logging to file is off when RsyncOSX starts

## Number of days

- Number of days
  - in Execute view tasks older than number of days are marked red

## Snapshot day of week to keep

- The day of week to keep when selecting a [plan](/Plansnapshots) for deleting snapshots

### Paths for RsyncOSX and RsyncOSXsched

- path RsyncOSX
- path RsyncOSXsched
  - the path for both apps should be set if scheduled tasks are executed in RsyncOSXsched, green light indicates apps are found in path

See [scheduled backups](/ScheduleTasks) and [menu app](/Menuapp) for more info.
