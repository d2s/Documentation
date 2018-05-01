---
layout: post
title:  "The main opening view and a short intro to RcloneOSX"
permalink: RcloneIntro
---

This page is a short intro to RcloneOSX and a brief walkthrough of the main functions of RcloneOSX. The intro is based on a early version. There has been updates to the application after the intro was made. RcloneOSX is a "quick and dirty" port of RsyncOSX to utilize `rclone`. I will spend some more time to refactor code and include some more `rclone` enhancements.

See [changelog](/RcloneChangelog). See also the [RsyncOSX readme](https://rsyncosx.github.io/AboutRsyncOSX) for more info about how RcloneOSX is working. Most of the functions are equal as RcloneOSX is built by adapting code from RsyncOSX.

I have tested the following cloud services (enabled through `rclone config`):

- Dropbox
- Microsoft Onedrive
- Google Drive

All configurations to execute are listed in table. From the main view most actions (edit configurations, adding parameters to rclone, delete configurations) regarding configurations are executed. Configurations can be saved in user selected **profiles**. The **profile** in use is shown in label `Profile: name`.

**Caution:** The screenshots are from an early version. After release of version 1.5.0 screenshots and this intro will be updated.

## How to execute tasks

There are four ways to execute tasks (`backup` tasks only). Due to how a `restore` works a restore can only be executed by a test run (`--dry-run`) before the real run. This is a precaution (see warning above).
- a double click on a row executes first a test run (`--dry-run`), the next double click executes the real task
  - selecting another row after a `--dry-run` resets the work queue
- `⌘R` - shortcut for immediate execute task after selecting a row
  - if a task is executed by shortcut `⌘R`, a select of another row during execution will terminate (abort) the current task
- mark backup tasks for batch, select the batch button executes all tasks marked for batch in one go
- schedule a task, scheduled tasks are executed according to date and time, ether once, daily or weekly

All tasks can be aborted during execution.

## Executing single tasks

![Main view](/images/RcloneOSX/master/intro/main.png)
A **double click** on row executes the task. Next task is a *Estimate* run as indicated on left in main view. An estimate run is a `--dry-run` execution of rclone. Tasks can also be executed in one go by selecting the batch button
The result of a estimate run is presented. Next task is *Execute*. *Execute* is the real run as indicated on left side in main view rcloneOSX. Selecting a new row resets the tasks. The pictures show a transfer of about 310 MB of data to Google Drive in about 3 1/2 hours.
![Main view](/images/RcloneOSX/master/intro/executing.png)
During a real run a progress bar show the progress of backup or restore task. All tasks can be aborted during execution.
![Main view](/images/RcloneOSX/master/intro/finished.png)

### Batch mode

Tasks can be executed in one go in batch mode.
![](/images/RcloneOSX/master/intro/batch.png)
Testing batch and logging numbers. Only tasks `sync` and `copy` allowed for batch (as well as scheduled tasks).
![](/images/RcloneOSX/master/intro/batch2.png)
![](/images/RcloneOSX/master/intro/batch3.png)
Tasks are updated with last execution dates.
![](/images/RcloneOSX/master/intro/batch4.png)

## Adding configurations

It is easy to add new tasks. RcloneOSX shows only (dynamically) added cloud services in rclone config file.
![Main view](/images/RcloneOSX/master/intro/add.png)

## Restore files or catalogs

Search and restore files and catalogs in cloud services.
![Main view](/images/RcloneOSX/master/intro/restore.png)

## Scheduling tasks

Only **backup** tasks can be scheduled. When a task is scheduled RcloneOSX counts down when task is kicked off. The first scheduled task to be executed is marked green in table and the column `In` shows when task is due for execution.
![Main view](/images/RcloneOSX/master/intro/schedule.png)
When a task is executed a dropdown menu is automatically presented in main view.

## Logging

RcloneOSX is logging all tasks. The user can choose in user configuration, to disable or enable detailed logging. Detailed logging is on as default. In log view all tasks with date, number of files and size transferred is logged. In the main view only date and time for last execution is set.
![Main view](/images/RcloneOSX/master/intro/logs.png)
Searching (filter) logs shows logrecords by applying the filter.

## Rclone parameters

The user can pass any parameter to rclone or choose some predefined parameters.
![Main view](/images/RcloneOSX/master/intro/parameters.png)

## Profiles

rcloneOSX uses profiles. If not used all configurations are saved in the default profile. Which profile in use is labeled on left top of table.

**Double click** on a profile name to select a profile.

In the profiles menu there are two options:

- `OK`. Name of new profile must be set in `New profile name` before `OK` button is selected. If `New profile name` is empty the view is closed (not loading a new profile).
- `Delete` profile. Select profile to be deleted in list of profiles and select `Delete` button to delete.
- `Default` button selects the default profile.
![Main view](/images/RcloneOSX/master/intro/profile.png)

### RcloneOSX configuration files

RcloneOSX configuration file, scheduled tasks which also includes log records and user configuration are plain XML-files ([property list files](https://en.wikipedia.org/wiki/Property_list)). Files are saved in:

- `~/Documents/Rclone/MacID/configRsync.plist` - configurations
  - `~/` is user home directory
  - `MacID` is the Mac serial number and is automatically set by rcloneOSX
- `~/Documents/Rclone/MacID/schedulerRsync.plist` - scheduled tasks including log records
- `~/Documents/Rclone/MacID/config.plist` - user config

If _profile_ is used:

- `~/Documents/Rclone/MacID/profile/configRsync.plist`
- `~/Documents/Rclone/MacID/profile/scheduleRsync.plist`
  - `profile` is the profile name
- `~/Documents/Rclone/MacID/config.plist` - user config
