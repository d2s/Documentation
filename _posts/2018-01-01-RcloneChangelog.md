---
layout: post
title:  "Rclone Changelog"
permalink: RcloneChangelog
---
This is the Changelog for RcloneOSX. RcloneOSX is a port of RsyncOSX to utilize `rclone`.

Rclone is *rsync for cloud storage*. Even if they are somewhat equal they are also different in many ways. RcloneOSX is built upon the ideas from RsyncOSX. But it is not possible to clone all functions in RsyncOSX to RcloneOSX. I spend most of my time developing RsyncOSX and from time to time some of the functions within RcloneOSX are ported from RsyncOSX. I am quite sure I could do more development in RcloneOSX, but my main focus is RsyncOSX. I am not an advanced user of rclone. I am synchronizing my GitHub catalog to Dropbox and Google.

I have also implemented [encrypted](/Encrypted) backup in RsyncOSX by utilizing RcloneOSX.  


See [releases](https://github.com/rsyncOSX/rcloneosx/releases) for download.

## Next version

Updated 9 August 2018.

I have commenced working on a new version of RcloneOSX. Most of the updates are enhancements from RsyncOSX. The updates are in the following functions:

- if task is selected in Execute view, only logs for selected task is presented in log view
- some enhancements in copy single files, fixed a memory leak
- implementing a new restore function from Execute view
- a new info view showing output from rclone during execution of single tasks
- and probably some more enhancements as well

A release candidate will be released within some weeks.

## Version 1.5.4

- released 21 June 2018
- fixed a bug (crash) if RcloneOSX is started without installing rclone first
- some enhancements in [logs](/Logging) and caching of remote info

## Version 1.5.2

- released 1 July 2018
- new app icon from [Zsolt Sándor](https://github.com/graphis)
- some refactor of code
- compiled with latest version of Xcode, version 9.4 (9F1027a)

## Version 1.5.1

There are several enhancements in this release:
- released 6 May 2018
- `⌘I` gets remote info about tasks
- `⌘B` commence an automatic backup for `sync` tasks with data to sync
- selecting the i-button commence an estimating run for all `sync` tasks

Estimate all sync tasks.
![Execute view](/images/RcloneOSX/v1.5.1/nr1.png)
Automatic backups, finding all tasks with data to transfer.
![Execute view](/images/RcloneOSX/v1.5.1/nr2.png)
![Execute view](/images/RcloneOSX/v1.5.1/nr3.png)
![Execute view](/images/RcloneOSX/v1.5.1/nr4.png)
![Execute view](/images/RcloneOSX/v1.5.1/nr5.png)
`⌘I` gets remote info about task.
![Execute view](/images/RcloneOSX/v1.5.1/nr6.png)

## Version 1.4.0

- released 23 April 2018
- minor fix for enable restore of encrypted backups (see [encrypted](/Encrypted) backups in RsyncOSX)

## Version 1.3.6

- released 28 March 2018
- maintenance release, fixed a bug in schedules
- added a new new for all profiles
- added sort and filter in logs and all profiles

## Version 1.3.5

- released 6 March 2018
- refactor schedules
- cleanup of Execute view
- notification when scheduled tasks are completed

## Version 1.3.0

- released 23 January 2018
- some minor fixes

## Version 1.2.6

- released 9 January 2018
- a couple of minor bugfixes (logging)
- new function for quick backups, sort and select which tasks to be executed in one go
- sort and filter in **quick backups**

## Version 1.2.0

- v1.2.0 released 17 Dec 2017
- some bugfixes
- added scheduling of tasks

## Version 1.1.5

Scheduling tasks is disabled in this update. Schedules might be setup but it is not effective. Parts of the schedules needs refactor. Schedules will be enabled again when in next release.

- v1.1.5 is updated 10 Dec 2017
- focus on GUI single tasks and batch
- adding several shortcuts
	- after selecting a row the following shortcuts are effective
	- `⌘E` - shortcut for edit task
	- `⌘O` - shortcut for rclone parameters to task
	- `⌘D` - shortcut for delete task
	- `⌘R` - shortcut for immediate execute task, executing
	task by shortcut seems to be more effective compared execute by batch and single tasks
	- `⌘A` - Abort task

If a task is executed by shortcut `⌘R`, a select of another row during execution will terminate (abort) the current task. Scheduled task also might be aborted by selection the stop symbol.

## Version 1.1.1

- released 1 Dec 2017
- fixed a bug in batchview causing batch not executing properly

## Version 1.1.0

- released 28 Nov 2017
- new buttons are implemented
- fixed a typo and some minor fixes

## Version 1.0.0

- released 24 Nov 2017
- logging result after execution of tasks is fixed
- added possibility of logging, either minimum or full, output from rsync to loggfile in `Documents/rclonelog.txt`
	- the logging to file is default off when starting RcloneOSX, status of logging is not saved in userconfiguration
	- the log function appends new logs, be careful not logging all actions
- fixed some other minor glitches
- added number of days since last backup in Execute view

## version 0.2.5

* released 19 Nov 2017
* restore files and catalogs from cloud services
* minor bugfixes
* problem with logging is *probably* solved

## version 0.2.0

* new app icon and a few more bugfixes...
* enhancements in batchview

## Next version 0.1.5

* released 13 Nov 2017
* color rows in main table (`check` task in blue and `move` tasks in red)
* initial statistics and numbers are working
* only tasks `sync`, `copy` and `move` adding logs

## Version 0.0.3

* released 11 Nov 2017
* fixed a couple of bugs
* added command `check`
* only `sync`and `copy` tasks allowed executing in batch and by schedule
  - command `move` may cause some unwanted effects when executed, always do a `--dry-run` before executing
  - executing single tasks is always a two step task, first a `--dry-run` and then the real task after inspecting the result of the `--dry-run` task

## Version 0.0.2

* released 10 Nov 2017
* more fixes and enhancements, all commands as `copy`, `sync` and `move` are implemented
* still alfa release, but most functions work
* still work to do regarding numbers and statistics

## Version 0.0.1

By a couple of hours work with RcloneOSX I managed to do a `rclone copy` of a local directory to remote directory at Dropbox and Microsoft Onedrive. The Numbers part does not work yet because the output from `rclone` is quite different compared to `rsync`. Below are some screenshots from testing.

Adding cloud services is done by using the command line interface `rclone config`.

### What is working v0.0.1

* only `rclone copy`
  - verified with Dropbox and Microsoft Onedrive, expect others to work as well
* adding and executing single tasks
* batch tasks
* scheduled tasks
* logging tasks (only date, no numbers)
* profile, storing tasks in profiles
* change and delete configurations
* some parameters are working (just a few tests)

### What is not working v0.0.1

* numbers and statistics of transferred data
* for the moment only `rclone copy`
  - my knowlegde about rclone and its use is growing every day...
* no gui for `rclone config`
  - don't know if is possible to make a GUI for setting up rclone
  - for the moment investigating this issue is put on hold
