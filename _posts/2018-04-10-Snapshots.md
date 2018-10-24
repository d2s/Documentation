---
layout: post
title:  "Snapshots"
permalink: Snapshots
---
Snapshot is very effective method for saving changed and deleted data. As an example my GitHub local catalog is about 677 MB in size. This is the size of the oldest snapshot. There are 17 snapshots of my GitHub local catalog and all of them is only 994 MB in size including the oldest snapshot.
![](/images/RsyncOSX/master/snapshots/snapdemo1.png)
All 17 snapshots are about 150,000 files and catalogs. Most of them are [hardlinks](https://en.wikipedia.org/wiki/Hard_link) only. If all snapshots was expanded there should be about 16 times more data stored in my NAS. Only changed or deleted files are stored. Files which are not changed or deleted are hardlinked only.
![](/images/RsyncOSX/master/snapshots/snapdemo2.png)
The snapshot feature enables saving changed and deleted files ahead of a new synchronizing task. The snapshot saves the current state of all files in a separate directory ahead of any changes or deletions. Changed and deleted files can then be restored utilizing the [copy single files](/CopySingleFiles) features. The [full restore](/Fullrestore) will copy the **last** snapshot from remote storage to either the source directory or a temporary restore directory.

- snapshots works on both local attached disks and remote hosts
- standard rsync sync tasks (backup tasks) cannot be *converted* to snapshots, creating snapshots starts with a full sync in the first snapshot catalog (`~/snapshots/data/1`)
- the snapshot feature utilizes the `--link-dest` parameter to rsync, please use either version 3.1.2 or 3.1.3 of [rsync](https://rsync.samba.org/)
  - [version 3.1.2](https://download.samba.org/pub/rsync/src/rsync-3.1.2-NEWS) of rsync fixed a bug regarding the `--link-dest` parameter
  - [version 3.1.3](https://download.samba.org/pub/rsync/src/rsync-3.1.3-NEWS) of rsync was released 28 January 2018
    - see [RsyncOSX Readme](https://github.com/rsyncOSX/RsyncOSX) if you want to compile rsync yourself
- use copy files function for restore of single files or catalogs

## How does the snapshots works?

Every snapshot is in sync with local catalog at the time of creating the snapshot. Previous versions of files can be restored from snapshots. The snapshot is by utilizing the `--link-dest` parameter to rsync. The rsync parameters for snapshots are:

`--link-dest=~/snapshots/data/n-1 /Volumes/.../user/data/ user@remote.server:~/snapshots/data/n`

where

- `n` is the number of snapshots
- and `/Volumes/.../data/` is the source catalog
- and the remote catalogs is `~/snapshots/data/`

If remote catalog is a local volume full path must be added. The source catalog is **never** touched, only read by rsync. RsyncOSX creates the snapshots within the remote catalog. The `~` is expanded to the user home catalog on remote server. Utilizing snapshot on local attached disks require full path for remote catalog.

- `~/snapshots/data/1` - snapshot 1
  - a full sync when snapshot is created
- `~/snapshots/data/2` - snapshot 2
  - the next snapshots saves the changed files and makes hard links for files not changed
- `~/snapshots/data/n` - snapshot n
  - n is the latest snapshot

When the old snapshots are deleted, the filesystem takes care of saving the real files which are hard linked.

### Create a snapshot task

In the samples below:

- the source catalog is `/Volumes/Home/user/Documents/`
- and the snapshots in catalog `~/Documents/` on server `freenas.local`

To create a snapshot task select `snapshots` as type.

![Execute view](/images/RsyncOSX/master/add/add2.png)

### Ready for next snapshot

The rsync command shows the command to be executed.

![Execute view](/images/RsyncOSX/master/snapshots/readyforbackup.png)

```
Important: do not copy and paste command for execution within
a terminal window. RsyncOSX saves the number n to the
configuration. The number n is the next snapshot number.
The number n is used when computing the parameter for rsync
and is picked up from the configuration.
```

### Snapshot administration

The administration part supports delete of `n - 1` snapshots. The last snapshot `n` is never deleted. After a delete the view is updated to reflect the current number of snapshot catalogs. The number of snapshots to be deleted are marked red.

![Execute view](/images/RsyncOSX/master/snapshots/delete.png)

## Logs, search and restore

A full restore of the latest snapshot by utilizing the full restore. It is recommended to restore to a temporary catalog.

![Execute view](/images/RsyncOSX/master/snapshots/fullrestore.png)

By utilizing the copy files functionality single files or catalogs can be restored from snapshots. Logs are marked with snapshot number.

![Execute view](/images/RsyncOSX/master/snapshots/copyfiles1.png)

Filter all files in snapshot #65.

![Execute view](/images/RsyncOSX/master/snapshots/copyfiles2.png)
