## Important notes about rsync and RsyncOSX

Index of [RsyncOSX documentation](https://rsyncosx.github.io/Documentation/).

RsyncOSX is a GUI for the rsync command-line tool. The main use are:

- backup (and restore) local files on your Mac to remote servers connected to Internet or local network
- backup (and restore) local files on Mac to local storage (attached disks)
  - if this is *the only use* there might be *other tools* more useful than RsyncOSX

Why use rsync for backup? See notes below. Be sure you understand the basics how rsync works before using RsyncOSX (and rsync).
```
Warning: default parameters for rsync is to synchronize the source and destination.
A "restore" will delete all files in the source which are not in the destination.
The main objective to RsyncOSX is to keep source directory and destination (backup)
directory synchronized. When a source directory is backed up, the destination is 100%
synchronized with the source in the moment the backup task is completed. There are
no revisions of files in the backup in default RsyncOSX. Old files in the backup are
either replaced with new ones or deleted if so is true in source.
```
- _source_: the local volume to be copied
- _destination_: the remote location where source files and catalogs are copied

What about **revisions and deleted** files? Either use the [snapshot feature](Snapshots.md) or by [backup parameters](Parameters.md) to rsync.

## Why use RsyncOSX (and rsync)?

There is only one simple answer to the question and the answer is [rsync](https://en.wikipedia.org/wiki/Rsync). Rsync is a _rock solid_, _well proven_, _secure_, _fast_, _reliable_ and _wide accessibility_ across platforms command line tool. RsyncOSX is just a GUI for executing rsync commands. Rsync is a command line tool with tons of parameters. Choosing the right parameter and to get the predicted result from rsync might be a challenge. RsyncOSX does the job for you. RsyncOSX also stores configurations in profiles and makes it easy to use different configurations.

The following features are implemented in RsyncOSX:

- execute **single** tasks
  - an *estimation* run is required before the real task is executed (an estimation run is executed by the setting the `--dry-run` parameter to rsync)
  - either by a double click on row or by pressing the Execute button **after** the estimation progress indicator has stopped executes the real task
  - if another row (task) is selected after estimation is done a new estimation run is required
- snapshot backups
- quick backups
- execute **batch** tasks
  - batch tasks are automatically executed until all are completed (the estimate run and execute run are executed in one go)
  - if you want tasks to be executed in one go mark them for batch
- adding **new tasks** either by drag and drop (for local volumes) or by GUI
- single- and batch tasks might be **aborted** at any time
- choose **other version** of rsync in **user configuration**
- user defined **rsync parameters**
  - the user can add parameters to rsync
  - there are predefined parameters for saving old files in a backup directory
- **enable** save backups of changed or deleted files (by using rsync parameters, predefined parameter)
- **delete** and **edit** configurations
- manage backup tasks in **profiles**
	- as many profiles as wanted
- **restore of single files or catalogs** from remote storage
- **scheduling of backup tasks**
  - daily, weekly or monthly schedules
- **detailed logging** of tasks
  - switch on/off

## RsyncOSX is not suitable to all users

The primary objective for me to write and use RsyncOSX is for storing backup of local volumes to _low cost remote server_ and assist me to keep my _two MacBook desktops in sync_. The remote servers might be running either Linux, Solaris, OpenSolaris, FreeBSD or other BSD based server OS. To set up and use all the functionality of RsyncOSX require some computer skills as login to a remote server (from terminal) and set up private/public key based ssh password-less login. Some basic understanding of the command-line tool rsync is also recommended.

Any user just looking for an easy to use backup tool is advised to use other and probably more suitable tools than RsyncOSX. To fully understand and use RsyncOSX I recommend the following:

- you have some understanding of the command-line tool rsync
- you have some knowledge about running either Linux, Solaris, OpenSolaris, FreeBSD or other BSD based server OS
- you are able to [setup a ssh password-less login](PasswordlessLogin.md) between the Mac and the remote server

There is a short [intro](Intro.md) to RsyncOSX.
