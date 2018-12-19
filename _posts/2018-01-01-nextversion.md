---
layout: post
title:  "Next version"
permalink: nextversion
---
The work on snapshots is commenced. Deleting snapshots is now by mark the snapshots or by selecting by number. In the next release there will be a plan for snapshots. A plan can be keep one snapshot each week, each month and so on. Plans or not yet implemented but will be before a new release.

Deleting snapshots is a **destructive** operation and should be performed with care.

![](/images/RsyncOSX/master/nextversion/plan.png)

The following plan is in test (by choosing the button `Plan`). The plan is split into three parts, this week, this month and previous months. Selecting the button `Plan` only evaluates and suggests which snapshots to delete based upon the plan.

**This week and month**:

- in the current week (this week): keep all snapshots
  - snapshots are marked with `this week`
- in the current month (this month): for all weeks in the current month exclude current week, keep all snapshots each Sunday
  - snapshots marked for delete are marked `this month`

**Previous months**:

- in previous months: keep snapshots last Sunday each month.
  - snapshots marked for delete are marked `prev months`

To delete the suggested snapshots press the `Delete` button.

In the Add view querying for remote capacity is added. The query get info from configurations as listed in main view. After adding a new task the query also includes the new task. The query only works for **online remote** servers. In the example the server 10.0.0.57 is not available.

![](/images/RsyncOSX/master/nextversion/capacity1.png)
![](/images/RsyncOSX/master/nextversion/capacity2.png)
