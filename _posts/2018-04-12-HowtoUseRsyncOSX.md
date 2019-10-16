---
layout: post
title:  "Important notes about RsyncOSX  and rsync"
permalink: HowtoUseRsyncOSX
---
RsyncOSX is a GUI for the rsync command-line tool. The main uses are:

- synchronize and restore of local files on your Mac to **remote servers** connected to Internet and local network
- synchronize and restore local files on Mac to **local storage** (attached disks)

```
Warning: default parameters for rsync is to synchronize the
source and the remote (backup). A "restore" will delete all
files in the source which are not in the remote. The main
objective to RsyncOSX is to keep source directory and
remote directory synchronized. When the source
directory is synchronized, the remote is 100% in sync
with the source in the moment the synchronize task is
completed. There are no revisions of files in the remote
in default RsyncOSX. Old files in the remote are either
replaced with new ones or deleted if so is true in source.
```
```
Caution about RsyncOSX and the `--delete` parameter. The
`--delete` is a default parameter. The parameter instructs
rsync to keep the source and destination synchronized (equal).
The parameter instructs rsync to delete all files in the
destination which are not present in the source.

Every time you add a new task to RsyncOSX, execute an
estimation run (--dry-run parameter) and inspect the result
before executing a real run. If you by accident  set an
empty catalog as source RsyncOSX will delete all files in
the destination.

To save deleted and changes files either utilize snapshots
(https://rsyncosx.github.io/Snapshots) or the `--backup`
feature (https://rsyncosx.github.io/Parameters).

The --delete parameter and other default parameters might
be deleted if wanted.
```
What about revisions and deleted files? Either use the [snapshot feature](/Snapshots) or by [backup parameters](/Parameters) to rsync.

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
