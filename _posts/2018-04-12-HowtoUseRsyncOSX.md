---
layout: post
title:  "Important notes about RsyncOSX  and rsync"
permalink: HowtoUseRsyncOSX
---
RsyncOSX is a GUI for the rsync command-line tool. The main uses are:

- synchronize and restore of local files on your Mac to **remote servers** connected to Internet and local network
- synchronize and restore local files on Mac to **local storage** (attached disks)

What about revisions and deleted files? Either use the [snapshot feature](/Snapshots) or by [backup parameters](/Parameters) to rsync.

## Why use RsyncOSX and rsync?

There is one simple answer to the question and the answer is [rsync](https://en.wikipedia.org/wiki/Rsync). Rsync is a **rock solid, well proven, secure, fast, reliable** and **very accessible** command line tool across platforms. RsyncOSX is just a GUI for executing rsync commands. Rsync is a command line tool with tons of parameters. Choosing the right parameter and to get the predicted result from rsync might be a challenge. RsyncOSX does the job for you. RsyncOSX also stores configurations in profiles and makes it easy to use different configurations.

The following features are implemented in RsyncOSX:

- do single synchronize tasks, synchronize source and destination (backup)
- do snapshot tasks, previous snapshots are saved to restore previous versions or deleted files
- do quick synchronize tasks, either single tasks or group of tasks, both synchronize and snapshot tasks
- do synchronize tasks utilizing predefined parameters to rsync to save changed and deleted files
- do batch tasks, both synchronize and snapshot tasks
- adding new tasks by drag and drop (for local volumes)
- tasks my be aborted at any time
- choose other version of rsync in user configuration
- user defined rsync parameters
  - the user can add parameters to rsync
- manage tasks in profiles
- either a full restore or restore of single files from remote storage
- scheduling of tasks
  - once, daily or weekly schedules
- detailed logging of tasks
