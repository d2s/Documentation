## Schedule task

By selecting a row and choose schedule applies a scheduled backup to a task. There are four(three) choices for schedules :

- **Once**
	- is executed once at date and time given
- **Daily**
	- is executed every 24-hour and stops at given date and time
first backup in 24-hour
- **Weekly**
	- as for daily, but every 7 days
- **Details**
	- stop or delete scheduled tasks

Select task (row), set the start date and time and select the schedule (once, daily or weekly) to set up a schedule of backup. Every time RsyncOSX starts, the schedule is computed. Every time a change in any schedule the schedule is computed. The schedule is a stack of tasks. The top most element is the first task to be executed. RsyncOSX keeps track of the first task only (in time). Rest of the scheduled operations remains on stack until popped of the stack.

The stack is a reference only to a configuration (by a hidden key). The user can change anything regarding the task up to the moment the task is executed by schedule. If the task is deleted RsyncOSX cancel the schedule, computes the stack again and starts tracing in time next scheduled task.

When the first scheduled task is **completed**, RsyncOSX checks the next top element of stack. If start date and time is in the future RsyncOSX tracks task in time. 

<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;">
<tbody>
<tr><td style="text-align: center;">
<div class="separator" style="clear: both; text-align: center;">
<a href="https://3.bp.blogspot.com/-pJYPTGFb4vY/WAmhkSC5fhI/AAAAAAAAL50/Wn0PKn2m2bsi2t0aKIiD_K8M0z92BPZrQCLcB/s1600/Screen%2BShot%2B2016-10-20%2Bat%2B09.23.45.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="336" src="https://3.bp.blogspot.com/-pJYPTGFb4vY/WAmhkSC5fhI/AAAAAAAAL50/Wn0PKn2m2bsi2t0aKIiD_K8M0z92BPZrQCLcB/s640/Screen%2BShot%2B2016-10-20%2Bat%2B09.23.45.png" width="640" /></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">Select task for scheduling.</td></tr>
</tbody>
</table>
Schedule **once** is selected to execute about in one hour. Remote serverthe local volume to be backed up is shown.
<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;">
<tbody>
<tr><td style="text-align: center;">
<a href="https://4.bp.blogspot.com/-qPey9NI5Wnk/WAmhkX5ckcI/AAAAAAAAL54/kwZaACuWAgsNq6cuWOB7m8WTMaVO4-cRQCLcB/s1600/Screen%2BShot%2B2016-10-20%2Bat%2B09.24.05.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="336" src="https://4.bp.blogspot.com/-qPey9NI5Wnk/WAmhkX5ckcI/AAAAAAAAL54/kwZaACuWAgsNq6cuWOB7m8WTMaVO4-cRQCLcB/s640/Screen%2BShot%2B2016-10-20%2Bat%2B09.24.05.png" width="640" /></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">Schedule is created and time for next schedule is displayed.</td></tr>
</tbody>
</table>

<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;">
<tbody>
<tr><td style="text-align: center;">
<a href="https://2.bp.blogspot.com/-3W2nahamOLs/WAmhkY4mz8I/AAAAAAAAL58/gx3onllf-2siECKAcKu4aXzCbHAZhhPSgCLcB/s1600/Screen%2BShot%2B2016-10-20%2Bat%2B09.24.13.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="336" src="https://2.bp.blogspot.com/-3W2nahamOLs/WAmhkY4mz8I/AAAAAAAAL58/gx3onllf-2siECKAcKu4aXzCbHAZhhPSgCLcB/s640/Screen%2BShot%2B2016-10-20%2Bat%2B09.24.13.png" width="640" /></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">In the Execute view a number behind task displays how many times task will be executed by schedule.</td></tr>
</tbody>
</table>

### Stopping a scheduled task

Select row and then **details**. Either stop or delete task. If a task is deleted all logs regarding the task is deleted.

<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;">
<tbody>
<tr><td style="text-align: center;">
<a href="https://2.bp.blogspot.com/-3CKoR1TM0Yg/WAmhkxhhCYI/AAAAAAAAL6A/PK3o5esw6Kkf8ChF2NXY6DeuyoMy3qaowCLcB/s1600/Screen%2BShot%2B2016-10-20%2Bat%2B09.24.25.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="336" src="https://2.bp.blogspot.com/-3CKoR1TM0Yg/WAmhkxhhCYI/AAAAAAAAL6A/PK3o5esw6Kkf8ChF2NXY6DeuyoMy3qaowCLcB/s640/Screen%2BShot%2B2016-10-20%2Bat%2B09.24.25.png" width="640" /></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">Stopping and deleting tasks (and logs).</td></tr>
</tbody>
</table>