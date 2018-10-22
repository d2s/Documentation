---
layout: post
title:  "Next version"
permalink: nextversion
---
Updated 21 Oct 2018, version 5.5.4 rc.

Name of backup task is changed from `backup` to `synchronize` which is more precise. Name of task is automatically converted.
![](/images/RsyncOSX/master/nextversion/main.png)
![](/images/RsyncOSX/master/nextversion/add.png)
Quickbackup is redesigned. Select the marked button to commence a quickbackup.
![](/images/RsyncOSX/master/nextversion/quickbackup1.png)
The quickbackup executes a estimation run and selects all tasks with files to be synchronized. To commence the actual synchronizing select the marked play button.
![](/images/RsyncOSX/master/nextversion/quickbackup2.png)
There is a progressview on each row indicating the progress.
![](/images/RsyncOSX/master/nextversion/quickbackup3.png)
Copy single files or catalogs is redesigned. Remote files can be filtered by search strings in `Search`. By enter remote info in `Remote catalog:` also updates the restore command and result of a restore. The restore catalog can also be changed.
![](/images/RsyncOSX/master/nextversion/copy.png)
I am also working on snapshots, added functions for deleting old snapshots by number of days.
![](/images/RsyncOSX/master/nextversion/snapnum.png)
![](/images/RsyncOSX/master/nextversion/days.png)
It is possible to connect RsyncOSX and RcloneOSX. I have set up RcloneOSX to encrypt a copy of a local catalog. RsyncOSX is set up to copy the encrypted catalog to a remote server. Those two tasks are connected to encrypt data and synchronize updates to a remote server.
![](/images/RsyncOSX/master/nextversion/combined.png)
