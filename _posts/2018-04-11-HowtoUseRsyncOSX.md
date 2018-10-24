---
layout: post
title:  "Important notes about RsyncOSX  and rsync"
permalink: HowtoUseRsyncOSX
---
Rsync is a **file based** synchronization tool. There is no custom solution for the backup archive. You can quit utilizing RsyncOSX (and rsync) at any time and still have access to all synchronized files. Be sure you understand the basics how rsync works before using RsyncOSX (and rsync).

RsyncOSX is a GUI for the rsync command-line tool. The main use are:

- backup and restore of local files on your Mac to remote servers connected to Internet and local network
- backup and restore local files on Mac to local storage (attached disks)

```
Warning: default parameters for rsync is to synchronize the
source and the remote (backup). A "restore" will delete all
files in the source which are not in the remote. The main
objective to RsyncOSX is to keep source directory and
remote directory synchronized. When the source
directory is backed up, the remote is 100% synchronized
with the source in the moment the synchronize task is
completed. There are no revisions of files in the remote
in default RsyncOSX. Old files in the remote are either
replaced with new ones or deleted if so is true in source.
```
- **source**: the local volume to be copied
- **remote**: the remote location where source files and catalogs are copied (e.g. backed up)

What about **revisions** and **deleted** files? Either use the [snapshot feature](/Snapshots) or by [backup parameters](/Parameters) to rsync.

## Why use RsyncOSX and rsync?

There is only one simple answer to the question and the answer is [rsync](https://en.wikipedia.org/wiki/Rsync). Rsync is a *rock solid*, *well proven*, *secure*, *fast*, *reliable* and *wide accessibility* across platforms command line tool. RsyncOSX is just a GUI for executing rsync commands. Rsync is a command line tool with tons of parameters. Choosing the right parameter and to get the predicted result from rsync might be a challenge. RsyncOSX does the job for you. RsyncOSX also stores configurations in profiles and makes it easy to use different configurations.

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
