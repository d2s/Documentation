## RsyncOSXsched and menu app

There are some issues regarding how to enter `daily` and `weekly` schedules.  There will be a minor redesign of the schedule part. The changes for all schedules will be to enter a start and type of schedule. The schedule will be active until stopped. This applies to schedules `daily` and `weekly`. Schedule `once` executes once, that is it. The updated release candidate includes a revised schedule.

Initial listing v0.0.1, it compiles and executes but still need some more testing before released. This is the menu app (popover) for executing scheduled tasks RsyncOSX. The idea is add scheduled tasks in RsyncOSX, quit RsyncOSX and let the menu app take care of executing the scheduled tasks. Only scheduled tasks from the selected (active) profile is active.

The menu app can be started from RsyncOSX and RsyncOSX can be activated from the menu app. This require paths for both apps to be entered into user configuration.  The paths are used for activating the apps from either within RsyncOSX or RsyncOSXsched. Toggle on/off if scheduled tasks in menu app only.
![](screenshots/master/menuapp/sched0.png)
Adding scheduled for tasks (in profile `Snapshots`) in RsyncOSX. After adding tasks either keep RsyncOSX running or select main menu and select the button `Menuapp`.

A notification is submitted when a scheduled tasks is completed.

![](screenshots/master/menuapp/notifications1.png)
![](screenshots/master/menuapp/notifications2.png)

![](screenshots/master/menuapp/sched1.png)
Double click on row brings up details about schedules and logs for one task.
![](screenshots/master/menuapp/sched3.png)
The green and yellow lights in column `Schedule` indicates two scheduled tasks within next hour (green lights) and one more than one hour (yellow light).
![](screenshots/master/menuapp/sched2.png)
Selecting the `Menuapp` in main view quits RsyncOSX and starts the menu application. The default profile is selected when it starts. There are no active schedules in the `default` profile. Selecting profile `Snapshots` (the menu app reads any profile created within RsyncOSX) activates any scheduled tasks in profile. Only scheduled tasks in selected profile is activated.
![](screenshots/master/menuapp/sched4.png)
![](screenshots/master/menuapp/sched5.png)
The status light is green indicating there is an active task waiting for execution.
![](screenshots/master/menuapp/sched6.png)

There is a minimal logging in menu app. The log is not saved to disk, it lives only during lifetime of menu app. The menu app logs the major actions within the menu app.
![](screenshots/master/menuapp/log1.png)
![](screenshots/master/menuapp/log2.png)
