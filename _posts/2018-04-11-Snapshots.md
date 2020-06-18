---
layout: post
title:  "Snapshots"
permalink: snapshots
---
Snapshot is an effective method for saving changed and deleted data. Snapshot utilize [hardlinks](https://en.wikipedia.org/wiki/Hard_link) and only changed and deleted data are saved as separate files in a snapshot. Files which are not changed are  hardlinks to the original file in the snapshot.

## What is a snapshots?

A snapshot is a saved state or backup of data at a specific point of time. Every snapshot is in sync with local catalog at the time of creating the snapshot. Previous versions of files can be restored from snapshots. The snapshot is by utilizing the `--link-dest` parameter to rsync. The rsync parameter for next snapshot to save is:

`--link-dest=~/snapshots/n-1 /Volumes/user/data/ user@remote.server:~/snapshots/n`

where

- `n` is the number of next snapshot to be saved
- `n-1` is the latest saved snapshot
- `/Volumes/user/data/` is the source catalog
- `~/snapshots/` is the remote catalog where snapshots are saved, the remote catalog is set by the user

If remote catalog is a local volume full path must be added. The source catalog is **never** touched, only read by rsync.

RsyncOSX creates the snapshots within the remote catalog. The ~ is expanded to the user home catalog on remote server. Utilizing snapshot on local attached disks require full path for remote catalog.

- `~/snapshots/1` - snapshot one
  - a full sync when snapshot is created
- `~/snapshots/2` - snapshot two
  - the next snapshots saves the changed files and makes hard links for files not changed
  - `~/snapshots/n-1` - snapshot n
    - n-1 is the latest snapshot saved to disk
- `~/snapshots/n` - snapshot n
  - n is the latest snapshot to be saved

When the old snapshots are deleted, the filesystem takes care of saving the real files which are hard linked.

## Create a snapshot

To create a snapshot task select `snapshot` as type in Add tab.

![](/images/RsyncOSX/master/snapshots/snapshot1.png)

Do **not** copy and paste command for execution within a terminal window. RsyncOSX saves the number n to the configuration. The number n is the next snapshot number. The number n is used when computing the parameter for rsync
and is picked up from the configuration.

## Snapshot administration

It is important to administrate snapshots. By administrate means deleting snapshots. If snapshots are never deleted the number of snapshots might become difficult to use. A snapshot is most likely used to restore old and deleted files. This is why a plan to administrate snapshots are important. RsyncOSX can assist you in this.

To administrate snapshots select the snapshot tab. Deleting snapshots is a **destructive** operation and should be performed with care. It is important to have a plan about which snapshots to keep and which to delete. RsyncOSX utilizes a simple plan for delete and keep snapshots. The plan is based upon three parts:

- the current week
  - keep all the snapshots within the current week
- the current month minus the current week
  - keep all snapshots for the selected Day of week, e.g all snapshots every Sunday this month
- previous months (and years)
  - keep the snapshot in the last week of month for selected Day of week, e.g the last Sunday in the month

Snapshots which does not follow plan are automatically marked for deleting. To actually delete the marked snapshots require to select the Delete button.
