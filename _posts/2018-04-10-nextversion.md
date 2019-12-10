---
layout: post
title:  "Next version"
permalink: nextversion
---
Updated 10 December 2019

Version 6.0.5 release candidate, will be released sometime in Q1 next year.

The following are changes in the rc. There are no bugfixes (none reported).

- added new type of task `syncremote`
- added possibility to remove the trailing `/` when adding tasks, if you remove the trailing `/` be sure you understand what it means
- added parameter to set `$date` on backup folder
- refactor of schedule
- check of schedule logs
- minimized GUI of the menu app


## New task

The `syncremote` task is a kind of restore. The task synchronize a remote catalog to a local catalog on your Mac.

![](/images/RsyncOSX/master/nextversion/7.png)
![](/images/RsyncOSX/master/nextversion/8.png)

## New parameter

You can add a date to the backup catalog. The date is set as current date. Add `+$date` to the `backup_catalog+$date`.

![](/images/RsyncOSX/master/nextversion/9.png)

## Schedule part

The schedule part is refactored. Select a configuration and all schedules are listed. Schedules can be stopped and deleted. Logs can be deleted. Logs are stored by configuration and schedule. There has been a bug in storing logs which creates more records than necessary. By setting `check data` in userconfig, RsyncOSX will clean up. The `check data` flag is **not** persistent and have to be set each time.
![](/images/RsyncOSX/master/nextversion/1.png)
Do a reload of profile and schedule data is checked.
![](/images/RsyncOSX/master/nextversion/2.png)

## The menu app
The menu app (RsyncOSXsched) is minimized.
![](/images/RsyncOSX/master/nextversion/6.png)
