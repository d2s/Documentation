---
layout: post
title:  "User configuration"
permalink: UserConfiguration
---
There are only a few parameters to choose in user configuration. Configurations are saved to permanent store.

![](/images/RsyncOSX/master/userconfig/user.png)

## Rsync

 - 3.1.2 or 3.1.3 rsync - set optional path in NOT in /usr/local/bin
   	- any version of rsync should work, but only rsync  version 3.1.2, version 3.1.3 protocol version 31 and rsync  version 2.6.9  protocol version 29 are tested and verified
    - utilizing the [snapshot feature](/Snapshots) require either version 3.1.2 or 3.1.3
- optional path for rsync
    - if other version of rsync is installed in other path than `/usr/local/bin` it must be set here
- temporary path restore
    - preset temporary path for restoring single files or volumes
    - preset temporary path for [full restore](/Fullrestore)

If there is a not valid rsync path is set an error is presented in bottom of user configuration. If there still is missing rsync in optional path no execution of tasks is allowed.

## Paths for RsyncOSX and RsyncOSXsched

- Automatic execution of local configurations
- path RsyncOSX
- path RsyncOSXsched

## Logging

- detailed logging on or off
   	- if detailed logging is on all backup tasks are logged, if off only last date for task is updated in Execute view

## Logging to file

Logging is saved to permanent store.

- either minimum (last 10 lines) or full logging of output from rsync, be carful not logging everything, the log file might be big
- log file is `Documents/rsynclog.txt`
- logging to file is off when RsyncOSX starts

## Number of days

- Number of days
  - in Execute view tasks older than number of days are marked red

## Check data when loading

- Check data

## Environment

- Enable environment
