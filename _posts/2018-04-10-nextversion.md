---
layout: post
title:  "Next version"
permalink: nextversion
---
Released 24 December 2019

## New task

The `syncremote` task is a kind of restore. The task synchronize a remote catalog to a local catalog on your Mac. Remote server is required for `syncremote`.

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
