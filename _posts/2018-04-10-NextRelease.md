---
layout: post
title:  "Next release"
permalink: NextRelease
---
There will be some enhancements in next version:
- select and delete log records from the log view
- the full restore of a backup task is reimplemented
- collecting info from destination is cached

## Delete log records
Possibility to select log rows for delete.
![](/images/RsyncOSX/v5.4.0/nr3.png)
Filter logs and select filtered logs for delete.
![](/images/RsyncOSX/v5.4.0/nr4.png)
Confirmation of delete logs.
![](/images/RsyncOSX/v5.4.0/nr5.png)

## Refactor of restore
The new restore is implemented and included in the updated release candidate.
Select the task to restore.
![](/images/RsyncOSX/v5.4.0/restore1.png)
The view does an estimate of numbers to transfer, selecting restore button commence the restore process. **It is advised to restore to a temporary catalog.** To do so copy the original task and set local catalog to the temporary restore catalog. The restore will copy any file in destination to the temporary local restore catalog. To copy a task select the task to restore in the main view. Select the Add tab and within Add tab the Copy button. Change the local catalog to the temporary restore catalog and then, in main view, select the added "restore" task and restore button.
![](/images/RsyncOSX/v5.4.0/restore2.png)
- the **backup** radio button shows the actual rsync command (**dry-run**)for backup task including any parameters
- the **restore** radio button shows the rsync command (**dry-run**) for restore
![](/images/RsyncOSX/v5.4.0/backup.png)
![](/images/RsyncOSX/v5.4.0/restore.png)
And for snaphots tasks as well.
![](/images/RsyncOSX/v5.4.0/backupsnap.png)
![](/images/RsyncOSX/v5.4.0/restoresnap.png)


## Caching
Caching of estimates. Estimates are forced updated after execution of task.
![](/images/RsyncOSX/v5.4.0/nr1.png)
Caching of local and remote info one task. As above, estimates are forced updated after execution of task.
![](/images/RsyncOSX/v5.4.0/nr2.png)
