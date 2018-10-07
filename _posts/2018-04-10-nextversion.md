---
layout: post
title:  "Next version"
permalink: nextversion
---
This is some info about next version of RsyncOSX.

Updated 7 Oct 2018.

Name of backup task is changed from `backup` to `synchronize` which is more precise. Name of task are automatically converted.
![](/images/RsyncOSX/master/nextversion/main.png)
![](/images/RsyncOSX/master/nextversion/add.png)
Copy single files or catalogs are redesigned. Remote files can be filtered and by enter remote info in `Remote catalog:` also updates the restore command.
![](/images/RsyncOSX/master/nextversion/copy.png)
By estimate changes default selects tasks to be executed.
![](/images/RsyncOSX/master/nextversion/synch.png)
It is possible to connect RsyncOSX and RcloneOSX. I have set up RcloneOSX to encrypt a copy of a local catalog. RsyncOSX is set up to copy the encrypted catalog to e remote server. Those two tasks are connected to encrypt data and synchronize updates to a remote server.
![](/images/RsyncOSX/master/nextversion/combined.png)
The copy single files are also updated in RcloneOSX (next version).
![](/images/RsyncOSX/master/nextversion/rclonecopy.png)
