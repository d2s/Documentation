---
layout: post
title:  "Next version"
permalink: nextversion
---
This is some info about next version of RsyncOSX.

Released 8 Oct 2018, version 5.5.4 rc.

Name of backup task is changed from `backup` to `synchronize` which is more precise. Name of task is automatically converted.
![](/images/RsyncOSX/master/nextversion/main.png)
![](/images/RsyncOSX/master/nextversion/add.png)
Copy single files or catalogs is redesigned. Remote files can be filtered by search strings in `Search`. By enter remote info in `Remote catalog:` also updates the restore command and result of a restore. The restore catalog can also be changed.
![](/images/RsyncOSX/master/nextversion/copy.png)
By estimate changes now default selects tasks to be executed.
![](/images/RsyncOSX/master/nextversion/synch.png)
It is possible to connect RsyncOSX and RcloneOSX. I have set up RcloneOSX to encrypt a copy of a local catalog. RsyncOSX is set up to copy the encrypted catalog to a remote server. Those two tasks are connected to encrypt data and synchronize updates to a remote server.
![](/images/RsyncOSX/master/nextversion/combined.png)

### Snapshots

I am also working on snapshots, added functions for deleting old snapshots by number of days. Work in progress and not yet as a release candidate.
![](/images/RsyncOSX/master/nextversion/snapnum.png)
![](/images/RsyncOSX/master/nextversion/dayssnap.png)
