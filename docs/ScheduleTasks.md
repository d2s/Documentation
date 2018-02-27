## Schedule task

Index of [RsyncOSX documentation](https://rsyncosx.github.io/Documentation/).

![](screenshots/master/menuapp/menuapp.png)

A scheduled task is only active within the profile in use. If you add a scheduled task in one profile and change profile, the schedule will be inactive until profile is loaded again.  By selecting a row and choose schedule applies a scheduled backup to a task. There are three choices for schedules :

- `once`
	- is executed _once_ at date and time given
- `daily`
	- is executed _every 24-hour_
- `weekly`
	- as for daily, but _every 7 day_

Select task (row), set the start date and time and select the schedule (once, daily or weekly) to set up a schedule of backup. Every time RsyncOSX starts, the schedule is computed. Every time there is a change in a schedule the schedule is recomputed. The schedule is a stack of tasks. The top most element is the first task to be executed. RsyncOSX keeps track of the first task only. All other scheduled tasks remains on stack until popped of.

The stack is a reference only to a configuration (by a hidden key). The user can change anything regarding a configuration up to the moment the task is executed by schedule. If a configuration is deleted all scheduled tasks connected to configuration is deleted as well.

When the first scheduled task is _completed_, RsyncOSX checks the next top element of stack. In example the schedule *once* is selected. First scheduled backup is scheduled in one hour.

From version 5.1.1 of RsyncOSX there is the `menu app` for executing scheduled tasks in RsyncOSX. The idea is to add scheduled tasks in RsyncOSX, quit RsyncOSX and let the menu app take care of executing the scheduled tasks.

The `menu app` should be started from RsyncOSX. This require paths for both apps to be entered into userconfiguration.  The paths are used for activating the apps from either within RsyncOSX or RsyncOSXsched.
Adding paths for applications automatically enables, if both apps are found, executing scheduled apps in the `menu app`. To disable delete paths.

Only scheduled tasks from the selected profile is active. A flag in RsyncOSX indicates where the scheduled tasks is set to be executed. If both RsyncOSX and the menu app is active at the same time only one of them is allowed to executed scheduled tasks.
![](screenshots/master/menuapp/sched0.png)
Both RsyncOSX and the `menu app` submit a notification when a scheduled tasks is completed. A scheduled task is either of type `once`, `daily` or `weekly`.

![](screenshots/master/menuapp/notifications1.png)

Adding scheduled for tasks in RsyncOSX. After adding tasks either keep RsyncOSX running or select main menu and select the menuapp button. If you decide to let RsyncOSX execute the scheduled tasks remember to set the correct settings in user configuration.
![](screenshots/master/menuapp/sched4.png)
Double click on row brings up details about schedules and logs for one task.
![](screenshots/master/menuapp/sched1.png)
The green light in column `Schedule` indicates a scheduled tasks within next hour (green lights). Selecting the `Menuapp` in main view quits RsyncOSX and starts the menu application. The default profile is selected when it starts.
![](screenshots/master/menuapp/sched2.png)
The status light is green indicates there are active tasks waiting for execution.
![](screenshots/master/menuapp/sched5.png)

### Logging

There is a minimal logging in menu app. The log is not saved to disk, it lives only during lifetime of menu app. The menu app logs the major actions within the menu app.
![](screenshots/master/menuapp/log1.png)
