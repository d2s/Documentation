## How to use RsyncOSX

This page is how to use RsyncOSX. It starts with the main view and is a walkthrough of adding a configuration and how to use it. **This pages are under construction.** It will be under construction for some time.


## Important notes about rsync and RsyncOSX

RsyncOSX is a GUI for the rsync command-line tool. The main uses are:

- backup (and restore) local files on Mac to remote servers connected to Internet or local network
  - the above is why I wrote RsyncOSX to use myself
- backup (and restore) local files on Mac to local storage (attached disks)
  - if this is _the only use_ there might be _other tools_ more useful than RsyncOSX

**Warning**: default parameters for rsync is to **synchronise** the **source** and **destination**. A "restore" will **delete** all files in the source which are not in the destination. The main objective to RsyncOSX is to keep the **source** directory and **destination** (backup) directory **in sync**. When a source directory is backed up, the destination is 100% in sync with source in the moment the backup task is completed. There are **no revisions** of files in the backup in **default RsyncOSX**. Old files in the backup are either replaced with new ones or deleted if so is true in source.

- _source_: the local volume to be copied
- _destination_: the remote location where source files and catalogs are copied

What about **revisions and deleted** files? In the [parameters to rsync](https://github.com/rsyncOSX/Documentation/blob/master/Docs/Parameters.md) there is presented a solution by parameters to rsync, to save changed and deleted files in a selected backup location.


## Where does RsyncOSX save configuration files?

RsyncOSX configuration file, log file, scheduled tasks file and user configuration are plain XML-files ([property list files](https://en.wikipedia.org/wiki/Property_list)). Configuration files (backup and restore task configurations and schedule data) are saved in:

- `~/Documents/Rsync/MacID/configRsync.plist`
  - `~/` is user home directory
  - `MacID` is the Mac Serial Number and is automatically set by RsyncOSX

When _profile_ is used:

- `~/Documents/Rsync/MacID/profile/configRsync.plist`
  - `profile` is the profile identification


## Why use RsyncOSX?

There is only one simple answer to the question and the answer is "[rsync](https://en.wikipedia.org/wiki/Rsync)". Rsync is a _rock solid_, _well proven_, _secure_, _fast_, _reliable_ and _wide accessibility_ across platforms command line tool. RsyncOSX is just a GUI for executing rsync commands. Rsync is a command line tool with tons of parameters. Choosing the right parameter and to get the predicted result from rsync might be a challenge. RsyncOSX does the job for you. RsyncOSX also stores configurations in profiles and makes it easy to use different configurations.

The following features are implemented in RsyncOSX:

- execute **single** tasks
  - estimation run is required before the real task is executed
  - by pressing the Execute button **after** the estimation progress indicator has stopped executes the real task
  - if another row (task) is selected after estimation is done a new estimation run is required
- execute **batch** tasks
  - batch tasks are executed automatically until all completed
  - if you want tasks to be executed in one go mark them for batch
- adding **new tasks** either by drag and drop (for local volumes) or by GUI
- **user configuration**
  - the user can select another version of rsync
- **abort** single- and batch tasks
- **rsync parameters**
  - the user can add parameters to rsync
- **enable** saving backups of changed or deleted files (in rsync parameters)
- **delete** and **edit** configurations
- store configurations in **profiles**
- **copy of single files or volumes** from remote storage
- **scheduling of tasks**
- **detailed logging**
  - switch on/off


## RsyncOSX is not suitable to all users

The primary objective for me to write and use RsyncOSX is for storing backup of local volumes to _low cost remote server_ and assist me to keep my _two MacBook desktops in sync_. The remote servers might be running either Linux, Solaris, OpenSolaris, FreeBSD or other BSD based server OS. To set up and use all the functionality of RsyncOSX require some computer skills as login to a remote server (from terminal) and set up private/public key based ssh password-less logins. Some basic understanding of the command-line tool rsync is also recommended.

Any user just looking for an easy to use backup tool is advised to use other and probably more suitable tools than RsyncOSX. To fully understand and use RsyncOSX I recommend the following:

- you have some understanding of the command-line tool rsync
- you have some knowledge about running either Linux, Solaris, OpenSolaris, FreeBSD or other BSD based server OS
- you are able to [setup a ssh password-less login](https://github.com/rsyncOSX/Documentation/blob/master/Docs/PasswordlessLogin.md) between the Mac and remote server


## The main opening view

The main opening screen is below. All configurations to execute are listed in table. From this screen all actions regarding configurations is executed. The documentation is presented in sequence of how to add and use new configurations into RsyncOSX.

There are two labels on top of table : Profile and Double click: YES. Configurations can be saved in user selected profiles. The profile in use is shown in label. Double click:YES (or NO) either allow or dont allow executing single tasks by double click on row. Disable/enable in Configuration.

<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;"><tbody>
<tr><td style="text-align: center;"><a href="https://3.bp.blogspot.com/-9e82zjXi_q4/WBQnQ425ysI/AAAAAAAAL7E/t--57C8ZzPMIgcRn02YTnrWx8jAv35oXgCLcB/s1600/Screen%2BShot%2B2016-10-29%2Bat%2B06.35.31.png" imageanchor="1" style="margin-left: auto; margin-right: auto;"><img border="0" height="336" src="https://3.bp.blogspot.com/-9e82zjXi_q4/WBQnQ425ysI/AAAAAAAAL7E/t--57C8ZzPMIgcRn02YTnrWx8jAv35oXgCLcB/s640/Screen%2BShot%2B2016-10-29%2Bat%2B06.35.31.png" width="640" /></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">The main view of RsyncOSX</td></tr>
</tbody></table>


### Profiles

RsyncOSX uses profiles. If not used all configurations are saved in the default profile. Which profile in use is labeled on left top of table.In the profiles menu there are two options:

- new profile (name of new profile must be set in "New profile name:")
- delete profile

Selecting the "Default" button selects the default profile. Double click on a profile name selects the profile.

<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;"><tbody>
<tr><td style="text-align: center;"><a href="https://1.bp.blogspot.com/-ZI3Wb7tQd5o/WBQnQ-ibGHI/AAAAAAAAL7A/XG1Du4gcLi8Pi3dlZNzzSCJOEFoMiZ_KQCLcB/s1600/Screen%2BShot%2B2016-10-29%2Bat%2B06.35.46.png" imageanchor="1" style="margin-left: auto; margin-right: auto;"><img border="0" height="336" src="https://1.bp.blogspot.com/-ZI3Wb7tQd5o/WBQnQ-ibGHI/AAAAAAAAL7A/XG1Du4gcLi8Pi3dlZNzzSCJOEFoMiZ_KQCLcB/s640/Screen%2BShot%2B2016-10-29%2Bat%2B06.35.46.png" width="640" /></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">Selecting profile</td></tr>
</tbody></table>
