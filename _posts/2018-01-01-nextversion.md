---
layout: post
title:  "Next version"
permalink: nextversion
---

Deleting snapshots is a **destructive** operation and should be performed with care.

The `Plan` button is available after selecting a task and RsyncOSX has collected info about snapshots from remote server. The following snapshots are **not** marked for delete (see rules below).
* 28 October 2018 is the last Sunday in October
* 25 November 2018 is the last Sunday in November
* 2, 9, 16 and 23 December 2018 are all Sundays in `this month`
* 24, 25 and 26 December are days in this week.

![](/images/RsyncOSX/master/nextversion/plan1.png)
![](/images/RsyncOSX/master/nextversion/plan2.png)

The following plan is in test. The plan is split into three parts, this week, this month and previous months. Selecting the button `Plan` only evaluates and suggests which snapshots to delete based upon the plan.

**Snapshots to keep**

All snapshots to keep are marked either `this week` or as `Sunday`. `Sunday` is either this month (not this week) or previous months.

**Previous months**:

- in previous months: keep snapshots last Sunday each month.
  - snapshots marked for delete are marked `prev months`

**This week and month**:

- in the current week (this week): keep all snapshots
  - snapshots are marked with `this week`
- in the current month (this month): for all weeks in the current month exclude current week, keep all snapshots each Sunday
  - snapshots marked for delete are marked `this month`

To delete the suggested snapshots press the `Delete` button.

**Remote capacity**

In the Add view querying for remote capacity is added. The query get info from configurations as listed in main view. After adding a new task the query also includes the new task. The query only works for **online remote** servers. In the screenshot the server 10.0.0.57 is not available.

![](/images/RsyncOSX/master/nextversion/capacity.png)
