---
layout: post
title:  "Executing single tasks"
permalink: SingleTask
---
In Synchronize view (which is the opening view) tasks can be executed as **single**- and/or **batch** tasks. Execute single tasks requires a couple of double clicks: one for **estimation** run and the second for **executing** the real task. The output from rsync is presented after each run.

![](/images/RsyncOSX/master/singletask/singletask.png)

There are three options for editing after selecting a task in row:

- Edit task
- Parameters (to rsync, see [parameters](/Parameters))
- Delete task

After selecting a row choosing one of the above pops up a new view according to selection. Select `Edit` task to editing basic information about task. Select `Delete` task to delete the selected row (task).

## Execute single tasks

Execute single tasks is a **two step** operation, one for **estimation** (dry-run) and one for the **real task**. A drop down view is automatically presented after both tasks. A single task is executed by  a **double click** on the selected task/row. The process info is updated when either a estimation task is executing or if a scheduled task is executing. There are five numbers in bottom page. Only version 3.x counts the number of remote directories. The numbers are files to be transferred and remote numbers.

See also the [intro](/Intro) about executing tasks.

### Estimating and Executing

The actual rsync command to be executed is shown below right corner in view. It is only the estimation command which is shown. You might copy the command and paste it into a terminal for execution. You have to delete the --dry-run parameter to execute the real task.

If Abort is pressed any executing task is aborted. After estimate run is completed and result is checked, a real run is executed by selecting the Execute button again. If you select another row after estimation a new estimation run must be completed.
The logg shows result of task. The latest log on top.
Selecting `Abort` aborts the current task.
