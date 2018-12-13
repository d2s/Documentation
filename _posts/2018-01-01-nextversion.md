---
layout: post
title:  "Next version"
permalink: nextversion
---
The work on snapshots is commenced. Deleting snapshots is now by mark the snapshots or by selecting by number. In the next release there will be a plan for snapshots. A plan can be keep one snapshot each week, each month and so on. Plans or not yet implemented but will be before a new release.

Deleting snapshots is a **destructive** operation and should be performed with care.

![](/images/RsyncOSX/master/nextversion/plan1.png)

The following plan is in test (by choosing the button `Plan`). The plan is split into three parts, this week, this month and previous months. Selecting the button `Plan` only evaluates and suggests which snapshots to delete based upon the plan.

**This week and month**:

- in the current week (this week): keep all snapshots
  - snapshots are marked with `this week`
- in the current month (this month): for all weeks except this the current week keep all snapshots each Sunday
  - snapshots marked for delete are marked `this month`

**Previous months**:

- in previous months: keep snapshots last Sunday each month.
  - snapshots marked for delete are marked `prev months`

![](/images/RsyncOSX/master/nextversion/plan2.png)

To delete the suggested snapshots press the `Delete` button.
