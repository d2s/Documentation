## Snapshots

Index of [RsyncOSX documentation](https://rsyncosx.github.io/Documentation/).

**Important 1**: the snapshot functionality is in beta yet. Use copy files function for restore of single files or catalogs. Snapshot works on attached disks (localhost) and remote hosts.

**Important 2**: snapshots is work in progress and for the moment, functions for administration of snapshots are missing.

**Important 3**: standard rsync sync tasks (backup tasks) cannot be *converted* to snapshots. Creating snapshots starts with a full sync in the first snapshot catalog (`~/snapshots/Documents/1`)

The snapshot will be like:

local catalog:

- `/Volume/home/thomas/Documents/`

remote catalog:

Snapshots are created (by rsync) within the

- `~/snapshots/Documents/1` - snapshot 1
  - a full sync when snapshot is created
- `~/snapshots/Documents/2` - snapshot 2
- .....
- `~/snapshots/Documents/NN` - snapshot NN
  - NN is the latest snapshot

Every snapshot is in sync with local catalog at the time of creating the snapshot. Previous versions of files can be restored from snapshots. The snapshot is set by using the `--link-dest` parameter of rsync. The parameters for snapshot is:

`--link-dest=~/snapshots/Documents/2 /Volumes/Home/thomas/Documents/ thomas@freenas.local:~/snapshots/Documents/3`

The source catalog (`/Volumes/Home/thomas/Documents/`) is **never** touched, only read by rsync.

### Create a snapshot task

![Main view](screenshots/master/snapshots/createtask.png)

### Ready for next snapshot

![Main view](screenshots/master/snapshots/readyforbackup.png)

### Snapshots on server

The terminal view shows there are two snapshots on server. When next task is executed there are three catalogs and `current` will point `current -> 3` (automatically set by RsyncOSX).

![Main view](screenshots/master/snapshots/snapshotroot.png)

## Search and restore

I have not yet design a search and restore special for snapshots. By using the copy files functionality single files or catalogs can be restored from snapshots.

![Main view](screenshots/master/snapshots/search1.png)
![Main view](screenshots/master/snapshots/search2.png)
