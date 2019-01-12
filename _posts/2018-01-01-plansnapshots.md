---
layout: post
title:  "Plan for snapshots"
permalink: Plansnapshots
---

The plan for delete and keep snapshots is split into three parts:

- this week
- this month
- previous months

Selecting the button `Plan` only evaluates and suggests which snapshots to delete based upon the plan. Deleting snapshots is a **destructive** operation and should be performed with care.

**Snapshots to keep**

All snapshots to keep are tagged `this week`, `Sunday this month` or `last Sunday month`.

**This week and month**:

- in the current week (this week): keep all snapshots
  - snapshots are tagged with `this week`
- in the current month (this month): for all weeks in the current month exclude current week, keep all snapshots each Sunday
  - snapshots marked for delete are tagged `this month`
  - snapshots to keep are tagged `Sunday this month`

To delete the suggested snapshots press the `Delete` button.

**Previous months**:

- in previous months: keep snapshots last Sunday each month.
  - snapshots marked for delete are tagged `prev months`
  - snapshots to keep are tagged `last Sunday month`

The `Plan` button is available after selecting a task and RsyncOSX has collected info about snapshots from remote server. The following snapshots are **not** marked for delete (see rules below).
* 28 October 2018 is the last Sunday in October
* 25 November 2018 is the last Sunday in November
* 2, 9, 16 and 23 December 2018 are all Sundays in `this month`
* 24, 25 and 26 December are days in this week.

![](/images/RsyncOSX/master/plansnapshots/plan1.png)
![](/images/RsyncOSX/master/plansnapshots/plan2.png)

**Remote capacity**

In the Add view querying for remote capacity is added. The query get info from configurations as listed in main view. After adding a new task the query also includes the new task. The query only works for **online remote** servers. In the screenshot the server 10.0.0.57 is not available.

![](/images/RsyncOSX/master/plansnapshots/capacity.png)
