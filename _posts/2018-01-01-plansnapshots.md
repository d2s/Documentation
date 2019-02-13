---
layout: post
title:  "Plan for snapshots"
permalink: Plansnapshots
---

The plans for delete and keep snapshots are split into three parts:

- this week
- this month
- previous months

Selecting a plan, either `last` or `every` only evaluates and suggests which snapshots to delete based upon the plan. Deleting snapshots is a **destructive** operation and should be performed with care.

### Snapshots to keep

All snapshots to keep are tagged:
- `this week`
- `Day this month`
- `last Day month`.

`Day` is selectable in user configuration and one of seven Days.

### This week and month:

- in the current week (this week): keep all snapshots
  - snapshots are tagged with `this week`
- in the current month (this month): for all weeks in the current month exclude current week, keep all snapshots each Sunday
  - snapshots marked for delete are tagged `this month`
  - snapshots to keep are tagged `Day this month`

To delete the suggested snapshots press the `Delete` button.

### Previous months:

- in previous months: keep snapshots either last `Day` each previous month or every `Day` in previous month.
  - snapshots marked for delete are tagged `prev months`
  - snapshots to keep are tagged `last Day month` or `Day prev month`

Selecting a plan is available after selecting a task and RsyncOSX has collected info about snapshots from remote server.

Plan `last`, choosen day is Sunday:

![](/images/RsyncOSX/master/plansnapshots/last.png)

Plan `every`, choosen day is Sunday:

![](/images/RsyncOSX/master/plansnapshots/every.png)
