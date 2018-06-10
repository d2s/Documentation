---
layout: post
title:  "Next release"
permalink: NextRelease
---
I am working on next release v5.3.6.

## Delete log records

Possibility to select log rows for delete.
![](/images/RsyncOSX/v5.4.0/nr3.png)
Filter logs and select filtered logs for delete.
![](/images/RsyncOSX/v5.4.0/nr4.png)
Confirmation of delete logs.
![](/images/RsyncOSX/v5.4.0/nr5.png)

## Refactor of restore

The restore part will be redesigned. The rsync parameters for full restore is calculated during loading of profile based upon the parameters for backup task.
![](/images/RsyncOSX/v5.4.0/backup.png)
![](/images/RsyncOSX/v5.4.0/restore.png)
And for snaphots tasks as well.
![](/images/RsyncOSX/v5.4.0/backupsnap.png)
![](/images/RsyncOSX/v5.4.0/restoresnap.png)

## Caching

Caching of estimates. Estimates are forced updates after execution of task.
![](/images/RsyncOSX/v5.4.0/nr1.png)
Caching of local and remote info one task. As above are forced updated after execution of task.
![](/images/RsyncOSX/v5.4.0/nr2.png)
