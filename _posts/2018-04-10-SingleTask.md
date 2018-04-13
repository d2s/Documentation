---
layout: post
title:  "Executing single tasks"
permalink: SingleTask
---
Index of [RsyncOSX documentation](/AboutRsyncOSX).

In main view (which is the opening view) tasks can be executed as **single**- and/or **batch** tasks. Execute single tasks requires a couple of **double clicks** : one for **estimation** run and the second for **executing** the real task. The output from rsync is presented after each run (see below).

There are three options for editing after selecting a task in row:

- *Edit task* (see below)
- *Parameters* (to rsync, see [parameters](Parameters.md))
- *Delete task*

For Parameters see below. After selecting a row choosing one of the above pops up a new view according to selection. Select `Edit` task to editing basic information about task. Select `Delete` task to delete the selected row (task).

There are _some status_ fields in the view :

- *Next task* - text is either _Estimate_ or _Execute_ - valid for single tasks only
	- "Estimate" (yellow light) - a double click on row does a --dry-run
	- "Execute" (green light) - a double click on row  does the real job, backup or restore
	- select a new row resets the work queue
- *Process info*
	- "Estimating" - a progress circel is shown when an estimation run is executing, during a real run a progress bar presents the progress
- *Scheduled job* - a progress bar shows when a scheduled job is executing

The TCP-button does a background check of TCP-connections. Red rows after a TCP-check indicates that there are no contact with remote server.

## Execute single tasks

Execute single tasks is a **two step** operation, one for **estimation** (dry-run) and one for the **real task**. A drop down view is automatically presented after both tasks. A single task is executed by  a **double click** on the selected task/row.
![Main view](/images/RsyncOSX/master/singletask1.png)
The process info is updated when either a estimation task is executing or if a scheduled task is executing. There are five numbers in bottom page. Only version 3.x counts the number of remote directories. The numbers are files to be transferred and remote numbers.

### Estimating and Executing

The actual rsync command to be executed is shown below right corner in view. It is only the estimation command which is shown. You might copy the command and paste it into a terminal for execution. You have to delete the --dry-run parameter to execute the real task.
![Main view](/images/RsyncOSX/master/singletask2.png)
*Next task* shows what the next task is. It shows three status : *Estimate*, *Execute* or *Abort*. If Abort is pressed any executing task is aborted. After estimate run is completed and result is checked, a real run is executed by selecting the Execute button again. If you select another row after estimation a new estimation run must be completed.
![Main view](/images/RsyncOSX/master/singletask3.png)
The logg shows result of task. The latest log on top.
![Main view](/images/RsyncOSX/master/singletask4.png)
Selecting `Abort` aborts the current task.

### Edit task

To edit a task select row (task) and choose edit. Either `Close`to discard changes or `OK` to save.

![Execute](/images/RsyncOSX/master/singletask/edit.png)
