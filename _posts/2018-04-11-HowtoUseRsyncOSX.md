---
layout: post
title:  "Important notes about rsync and RsyncOSX"
permalink: HowtoUseRsyncOSX
---
Rsync is a **file based** synchronization tool. There is no custom solution for the backup archive. You can quit utilizing RsyncOSX (and rsync) at any time and still have access to all synchronized files. Be sure you understand the basics how rsync works before using RsyncOSX (and rsync).

RsyncOSX is a GUI for the rsync command-line tool. The main use are:

- backup and restore of local files on your Mac to remote servers connected to Internet or local network
- backup and restore local files on Mac to local storage (attached disks)

```
Warning: default parameters for rsync is to synchronize the
source and destination. A "restore" will delete all files in
the source which are not in the destination. The main
objective to RsyncOSX is to keep source directory and
destination (backup) directory synchronized. When a source
directory is backed up, the destination is 100% synchronized
with the source in the moment the backup task is completed.
There are no revisions of files in the backup in default
RsyncOSX. Old files in the backup are either replaced with
new ones or deleted if so is true in source.
```
- **source**: the local volume to be copied
- **destination**: the remote location where source files and catalogs are copied (e.g. backed up)

What about **revisions** or **deleted** files? Either use the [snapshot feature](/Snapshots) or by [backup parameters](/Parameters) to rsync.

## Why use RsyncOSX (and rsync)?

There is only one simple answer to the question and the answer is [rsync](https://en.wikipedia.org/wiki/Rsync). Rsync is a *rock solid*, *well proven*, *secure*, *fast*, *reliable* and *wide accessibility* across platforms command line tool. RsyncOSX is just a GUI for executing rsync commands. Rsync is a command line tool with tons of parameters. Choosing the right parameter and to get the predicted result from rsync might be a challenge. RsyncOSX does the job for you. RsyncOSX also stores configurations in profiles and makes it easy to use different configurations.

The following features are implemented in RsyncOSX:

- do single backup tasks, synchronize source and destination (backup)
- do snapshot backups tasks, previous snapshots are saved to restore previous versions of or deleted files
- do quick backups tasks, either single tasks or group of tasks, both synchronize and snapshot tasks
- do backups utilizing predefined parameters to save changed or deleted files (by using rsync parameters, predefined parameter)
- do batch tasks, both synchronize and snapshot tasks
- adding new tasks by drag and drop (for local volumes)
- tasks my be aborted at any time
- choose other version of rsync in user configuration
- user defined rsync parameters
  - the user can add parameters to rsync
- manage backup tasks in profiles
- either a full restore or restore of single files from remote storage
- scheduling of backup tasks
  - once, daily or weekly schedules
- detailed logging of tasks

## RsyncOSX is not suitable to all users

The primary objective for me to write and use RsyncOSX is for storing backup of local volumes to *low cost remote server* and assist me to keep my *two MacBook desktops in sync*. The remote servers might be running either Linux, Solaris, OpenSolaris, FreeBSD or other BSD based server OS. To set up and use all the functionality of RsyncOSX require some computer skills as login to a remote server (from terminal) and set up private and public ssh keys for password-less logins. Some basic understanding of the command-line tool rsync is also recommended.

To fully understand and use RsyncOSX I recommend the following:

- you have some understanding of the command-line tool `rsync`
- you have some knowledge about running either Linux, Solaris, OpenSolaris, FreeBSD or other BSD based server OS
- you are able to [setup a ssh password-less login](/PasswordlessLogin) between the Mac and the remote server

There is a short [intro](/Intro) to RsyncOSX.
