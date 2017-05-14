
## The main opening view

All configurations to execute are listed in table. From this screen all actions (edit configurations, adding parameters to rsync, delete configurations) regarding configurations are executed.

There are two labels on top of table : **Profile** and **Double click: YES**. Configurations can be saved in user selected profiles. The profile in use is shown in label `Profile : name`. `Double click:YES` (or NO) either allow or don't allow executing single tasks by double click on row. Disable or enable in Configuration.

**Important**: Information about *new:* and *delete:* files and remote number of directories are only available if version 3.x of rsync is used.

![Main view](screenshots/master/main1.png)


### Profiles

RsyncOSX uses profiles. If not used all configurations are saved in the default profile. Which profile in use is labeled on left top of table.

**Double click** on a profile name to select a profile.

In the profiles menu there are two options:

- `New` profile. Name of new profile must be set in `New profile name` before `New` button is selected.
- `Delete` profile. Select profile to be deleted in list of profiles and select `Delete` button to delete.

Selecting the `Default` button selects the default profile.

![Main view](screenshots/master/profile.png)

### Logging

RsyncOSX is logging all tasks. The user can choose in user configuration, to disable or enable detailed logging. Detailed logging is on as default. In log view all tasks with date, number of files and size transferred is logged. In the main view date and time for last execution is set.

![Main view](screenshots/master/log.png)

## RsyncOSX configuration files

RsyncOSX configuration file, log file, scheduled tasks file and user configuration are plain XML-files ([property list files](https://en.wikipedia.org/wiki/Property_list)). Configuration files (backup and restore task configurations and schedule data) are saved in:

- `~/Documents/Rsync/MacID/configRsync.plist`
  - `~/` is user home directory
  - `MacID` is the Mac serial number and is automatically set by RsyncOSX

If _profile_ is used:

- `~/Documents/Rsync/MacID/profile/configRsync.plist`
  - `profile` is the profile identification

## Rsync errors

Sometimes rsync throws errors. RsyncOSX does a simple check in output if there are any occurrence of the prashe `rsync error:`. If found RsyncOSX resets the work queue. This is *not* a advanced error handling.

![Main view](screenshots/master/error.png)
![Main view](screenshots/master/config.png)
