---
layout: post
title:  "A short intro to aRsyncGUI"
permalink: aRsyncGUIIntro
---
This page is a short intro to aRsyncGUI. For more details about the various functions of aRsyncGUI please see the [documentation](/AboutaRsyncGUI) (RsyncOSX) about each function. Also be sure you understand  [the basics](/HowtoUseaRsyncGUI) (RsyncOSX) about how rsync works before using aRsyncGUI and rsync.

All configurations to execute are listed in table. From the Execute view most actions (edit configurations, adding parameters to rsync, delete configurations) regarding configurations are executed.

Configurations can be saved in user selected **profiles**. The profile in use is shown in label `Profile: profilname`. Information about **new or delete** files and **numbers remote** of directories are only available if version 3.x of rsync is used.

## When you start

aRsyncGUI is a sandboxed macOS app and the first to do is ask for permission to read the users home catalog. The first time the user starts the app a view asking for allow.

First to do is open a terminal and `cd` and `mkdir .ssh`. This creates the .ssh catalog which is required for enabling ssh passwordless logins to remote servers. After creating the `.ssh` catalog and start aRsyncGUI you are asked to allow aRsyncGUI to access the home catalog. Caution: you might have to change the selected catalog to the home catalog. 

![](/images/RsyncOSX/master/aRsyncGUIIntro/allow.png)
![](/images/RsyncOSX/master/aRsyncGUIIntro/main5.png)

## Where to start?

You can get up and running in just a few clicks. Open aRsyncGUI and select the `Add` tab.
![](/images/RsyncOSX/master/aRsyncGUIIntro/main1.png)
In the `Add` tab, as an example, add the Documents catalog as source and the tmp catalog as remote. This will setup a task to synchronize (backup) all content of the Documents to the tmp catalog. The tmp catalog can be an attached disk. Use drag and drop from Finder to add data.

Select `Add` button to add task.
![](/images/RsyncOSX/master/aRsyncGUIIntro/main2.png)
![](/images/RsyncOSX/master/aRsyncGUIIntro/main3.png)
Go back to the `Execute` tab, select the task and you are ready to go.
![](/images/RsyncOSX/master/aRsyncGUIIntro/main4.png)

## Type of tasks

There are **three** types of how to synchronize source and destination (backup):

(1) **synchronize** source and backup location, any changed and deleted files in backup location will either be overwritten or deleted
  - this is the standard synchronize task in aRsyncGUI, after execution source and destination (backup) is 100% in sync if there are no `--exclude` parameters to rsync
  - an `--exclude` parameter instructs rsync to disregard files, catalogs and patterns included in the parameter

(2) **snapshot**  tasks, a [snapshot](/Snapshots) of previous synchronize task is stored before a new task is executed, number of snapshots are user defined, copy deleted or previous versions of files from snapshots

(3) **synchronize** and **save changed** and **deleted** files in a separate backup catalog by adding a [parameters](/Parameters) to rsync

## How to execute any type of tasks

All tasks can be **aborted** at any time by selecting the stop button.

![](/images/RsyncOSX/master/aRsyncGUIIntro/menu1.png)

First select **one** task in Execute view, applies to (1) and (2) below.

(1) single task, a **double click** on a task executes first a test run (`--dry-run`), the next double click executes the real run

(2) **`⌘R`** (execute one task now) - shortcut for immediate execute the selected task
- if a task is executed by shortcut `⌘R`, a select of another task during execution will terminate (abort) the current task

(3) **`⌘B`** (execute all tasks now) - shortcut for **automatic executing** backups or by select the double arrow, the command checks tasks for files to be synchronized and automatically executes those tasks

![](/images/RsyncOSX/master/aRsyncGUIIntro/menu4.png)

(4) **quick backup**, select the marked arrow button in menu bar

![](/images/RsyncOSX/master/aRsyncGUIIntro/menu2.png)

- start with dynamic view of local vs remote storage, automatically selecting tasks with files to be synchronized

(5) mark backup tasks for **batch**, select the marked arrow button in menu bar

![](/images/RsyncOSX/master/aRsyncGUIIntro/menu3.png)

- tasks which are marked for batch are selected

(6) **schedule** a task, scheduled tasks are executed according to date and time, either once, daily or weekly

## YouTube videos (of aRsyncGUI)

There are four short YouTube videos of aRsyncGUI:

- adding and executing the [first backup](https://youtu.be/8oe1lKgiDx8)
- doing a full [restore](https://youtu.be/-R6n_8fl6Ls) to a temporary local restore catalogs
