---
layout: post
title:  "Next release"
permalink: NextRelease
---
There will be some enhancements in next version:
- select and delete log records from the log view
- the full restore part of backup task will be refactored, creation of the restore part is removed in the rc
- collecting info from destination is cached

## Delete log records
Possibility to select log rows for delete.
![](/images/RsyncOSX/v5.4.0/nr3.png)
Filter logs and select filtered logs for delete.
![](/images/RsyncOSX/v5.4.0/nr4.png)
Confirmation of delete logs.
![](/images/RsyncOSX/v5.4.0/nr5.png)

## Refactor of restore
The restore part will be redesigned. The rsync parameters for full restore is calculated during loading of profile based upon the parameters for backup task.
- the **backup** radio button shows the actual rsync command (**dry-run**)for backup task including any parameters
- the **restore** radio button shows the rsync command (**dry-run**) for restore
![](/images/RsyncOSX/v5.4.0/backup.png)
![](/images/RsyncOSX/v5.4.0/restore.png)
And for snaphots tasks as well.
![](/images/RsyncOSX/v5.4.0/backupsnap.png)
![](/images/RsyncOSX/v5.4.0/restoresnap.png)
The new restore is implemented, need some more test before uploaded as release candidate.
Select the task to restore.
![](/images/RsyncOSX/v5.4.0/restore1.png)
The view does an estimate of numbers to transfer, selecting restore button commence the restore process. It is advised to restore to a temporary catalog. To do so copy the original task and set local catalog to the temporary restore catalog. The restore will copy any file in destination to the temporary local restore catalog.
![](/images/RsyncOSX/v5.4.0/restore2.png)

## Caching
Caching of estimates. Estimates are forced updated after execution of task.
![](/images/RsyncOSX/v5.4.0/nr1.png)
Caching of local and remote info one task. As above, estimates are forced updated after execution of task.
![](/images/RsyncOSX/v5.4.0/nr2.png)
