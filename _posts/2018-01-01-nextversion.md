---
layout: post
title:  "Next version"
permalink: nextversion
---
The work on snapshots is commenced. Deleting snapshots is now by mark the snapshots or by selecting by number. In the next release there will be a plan for snapshots. A plan can be keep one snapshot each week, each month and so on. Plans or not yet implemented but will be before a new release.

I have cleaned up my own snapshots by utilizing the updated prerelease. Deleting snapshots is a **destructive** operation and should be performed with care. My plan was to delete most of the snapshots and keep only the last snapshot each Sunday and all for the current week.

## Selecting snapshots to delete

Select the Snapshots tab and mark snapshots for deletion. I selected snapshots according to plan above. After select press delete button.

![](/images/RsyncOSX/master/nextversion/preparedeletedocuments.png)
![](/images/RsyncOSX/master/nextversion/deletedocuments.png)

## Selecting logs to delete

After cleaning up snapshots I deleted all logs not required. All logs with `Snap` marked are logs connected to a existing snapshot.

![](/images/RsyncOSX/master/nextversion/keeplogsdocuments.png)

Select all logs for delete and unmark logs connected to a existing snapshot. Delete logs not required.

![](/images/RsyncOSX/master/nextversion/deletelogsdocuments.png)

The Snapshots view presents all snapshots with linked log record.

![](/images/RsyncOSX/master/nextversion/afterdeletedocuments.png)


## Number of files deleted

Applying the plan "delete all snapshots and keep only the last snapshot each Sunday and all for last week" reduced the number of files for my synchronized GitHub repository from 671,316 files to 125,939 files. I have kept 11 snapshots.

Before cleaning.

![](/images/RsyncOSX/master/nextversion/githubbefore.png)

After cleaning.

![](/images/RsyncOSX/master/nextversion/githubafter.png)
