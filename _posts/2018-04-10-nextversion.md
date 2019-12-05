---
layout: post
title:  "Next version"
permalink: nextversion
---
Updated 5 December 2019

Version 6.0.5 release candidate, will be released sometime in Q1 next year.

The following are changes in the rc. There are no bugfixes (none reported).

The schedule part is refactored. Select a configuration and all schedules are listed. Schedules can be stopped and deleted. Logs can be deleted.

Logs are stored by configuration and schedule. There has been a bug in storing logs which creates more records than necessary. By setting `check data` in userconfig, RsyncOSX will clean up. The `check data` flag is **not** persistent and have to be set each time.
![](/images/RsyncOSX/master/nextversion/1.png)
Do a reload of profile and schedule data is checked.
![](/images/RsyncOSX/master/nextversion/2.png)
The menu app (RsyncOSXsched) is minimized.
![](/images/RsyncOSX/master/nextversion/6.png)
