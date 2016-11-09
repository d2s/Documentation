<h2>How to use RsyncOSX</h2>

This page is how to use RsyncOSX. It starts with the main view and is a walkthrough of adding a configuration and how to use it. <b>This pages are under construction.</b> It will be under construction for some time. 

<h2>Important notes about rsync and RsyncOSX</h2>

RsyncOSX is a GUI for the rsync command-line tool. The main uses are:
<ul>
<li>backup (and restore) local files on Mac to remote servers connected to Internet or local network</li>
<ul>
<li>the above is why I wrote RsyncOSX to use myself</li>
</ul>
<li>backup (and restore) local files on Mac to local storage (attached disks)</li>
<ul>
<li>if this is <i>the only use</i> there might be <i>other tools</i> more useful than RsyncOSX</li>
</ul>
</ul>
<div>
<i>source</i>: the local volume to be copied</br>
<i>destination</i>: the remote location where source files and catalogs are copied</br>
</br>

<b>Warning</b>: default parameters for rsync is to <b>synchronize</b> the <b>source</b> and <b>destination</b>. A "restore" will <b>delete</b> all files in the source which are not in the destination. The main objective to RsyncOSX is to keep the <b>source</b> directory and <b>destination </b>(backup) directory <b>in sync</b>. When a source directory is backed up, the destination is 100% in sync with source in the moment the backup task is completed. There are <b>no revisions</b> of files in the backup in <b>default RsyncOSX</b>. Old files in the backup are either replaced with new ones or deleted if so is true in source.</br>
</br>

But dont panic? What about<b> revisions and deleted</b> files? In the <a href="https://github.com/rsyncOSX/Documentation/blob/master/Docs/Parameters.md" target="_blank">parameters to rsync</a> there is presented a solution to save changed and deleted files in a selected backup location.

<h2>Where does RsyncOSX save configuration files?</h2>

RsyncOSX configuration file, log file, scheduled tasks file and userconfiguration are plain XML-files (<a href="https://en.wikipedia.org/wiki/Property_list" target="_blank">property list files</a>).  Configuration files (backup and restore task configurations and schedule data) are saved in:</br>
</br>

<ul>
<li><code>~/Documents/Rsync/MacID/configRsync.plist</code></li>
<ul>
<li><code><b>~/</b></code> is user home directory</li>
<li><code>MacID</code> is the Mac Serial Number and is automatically created by RsyncOSX</li>
</ul>
</ul>
<div>
When <i>profile</i> is used:</div>
<ul>
<li><code>~/Documents/Rsync/MacID/profile/configRsync.plist</code></li>
<ul>
<li><code>profile</code> is the profile identification</li>
</ul>
</ul>

<h2>Why use RsyncOSX?</h2>

There is only one simple answer to the question and it is <a href="https://en.wikipedia.org/wiki/Rsync" target="_blank">rsync command line tool</a>. Rsync is a rock solid, well proven, secure, fast, reliable and wide accessibility across platforms command line tool. RsyncOSX is just a GUI for executing  rsync commands. Rsync is a command line tool with tons of parameters. Choosing the right parameter and to get the predicted result from rsync might be a challenge. RsyncOSX does the job for you. RsyncOSX also stores configurations in profiles and makes it easy to use different configurations.

The following features are implemented in RsyncOSX:</br>
</br>

<ul>
<li>execute <b>single</b> tasks</li>
<ul>
<li>estimation run is required before the real task is executed</li>
<li>by pressing the Execute button <b>after</b> the estimation progress indicator has stopped executes the real task</li>
<li>if another row (task) is selected after estimation is done a new estimation run is required</li>
</ul>
<li>execute <b>batch</b> tasks</li>
<ul>
<li>batch tasks are executed automatically until all completed</li>
<li>if you want tasks to be executed in one go mark them for batch</li>
</ul>
<li>adding <b>new tasks</b>  either by drag and drop (for local volumes) or by GUI</li>
<li><b>user configuration</b> </li>
<ul>
<li>the user can select another version of rsync</li>
</ul>
<li><b>abort</b> single- and batch tasks</li>
<li><b>rsync parameters</b></li>
<ul>
<li>the user can add parameters to rsync</li>
</ul>
<li><b>enable</b> saving backups of changed or deleted files (in rsync parameters)</li>
<ul></ul>
<li><b>delete</b> and <b>edit</b> configurations</li>
<li>store configurations in <b>profiles</b></li>
<li><b>copy of single files or volumes</b> from remote storage</li>
<li><b>scheduling of tasks</b></li>
<li><b>detailed logging</b></li>
<ul>
<li>switch on/off</li>
</ul>
</ul>

<h2>RsyncOSX is not suitable to all users</h2>

The primary objective for me to write and use RsyncOSX is for storing backup of local volumes to <i>low cost remote server</i> and assist me to keep my <i>two Macbook desktops in sync</i>. The remote servers might be running either Linux, Solaris, OpenSolaris, FreeBSD or other BSD based server OS. To set up and use all the functionality of RsyncOSX require some computer skills as login to a remote server (from terminal) and set up private/public key based ssh password-less logins. Some basic understanding of the command-line tool rsync is also recommended.

Any user just looking for an easy to use backup tool is advised to use other and probably more suitable tools than RsyncOSX. To fully understand and use RsyncOSX I recommend the following:</br>
</br>


<ul>
<li>you have some understanding of the command-line tool rsync</li>
<li>you have some knowledge about running either Linux, Solaris, OpenSolaris, FreeBSD or other BSD based server OS</li>
<li>you are able to <a href="https://github.com/rsyncOSX/Documentation/blob/master/Docs/PasswordlessLogin.md" target="_blank">setup a ssh password-less login</a> between the Mac and remote server</li>
</ul>

<h2>The main opening view</h2>

The main opening screen is below. All configurations to execute are listed in table. From this screen all actions regarding configurations is executed. The documentation is presented in sequence of how to add and use new configurations into RsyncOSX.

There are two labels on top of table : Profile and Double click: YES. Configurations can be saved in user selected profiles. The profile in use is shown in label. Double click:YES (or NO) either allow or dont allow executing single tasks by double click on row. Disable/enable in Configuration.

<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;"><tbody>
<tr><td style="text-align: center;"><a href="https://3.bp.blogspot.com/-9e82zjXi_q4/WBQnQ425ysI/AAAAAAAAL7E/t--57C8ZzPMIgcRn02YTnrWx8jAv35oXgCLcB/s1600/Screen%2BShot%2B2016-10-29%2Bat%2B06.35.31.png" imageanchor="1" style="margin-left: auto; margin-right: auto;"><img border="0" height="336" src="https://3.bp.blogspot.com/-9e82zjXi_q4/WBQnQ425ysI/AAAAAAAAL7E/t--57C8ZzPMIgcRn02YTnrWx8jAv35oXgCLcB/s640/Screen%2BShot%2B2016-10-29%2Bat%2B06.35.31.png" width="640" /></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">The main view of RsyncOSX</td></tr>
</tbody></table>

<h3>Profiles</h3>

RsyncOSX uses profiles. If not used all configurations are saved in the default profile. Which profile in use is labeled on left top of table.In the profiles menu there are two options:
<ul>
<li>new profile (name of new profile must be set in "New profile name:")</li>
<li>delete profile</li>
</ul>
Selecting the "Default" button selects the default profile.  Double click on a profile name selects the profile.
<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;"><tbody>
<tr><td style="text-align: center;"><a href="https://1.bp.blogspot.com/-ZI3Wb7tQd5o/WBQnQ-ibGHI/AAAAAAAAL7A/XG1Du4gcLi8Pi3dlZNzzSCJOEFoMiZ_KQCLcB/s1600/Screen%2BShot%2B2016-10-29%2Bat%2B06.35.46.png" imageanchor="1" style="margin-left: auto; margin-right: auto;"><img border="0" height="336" src="https://1.bp.blogspot.com/-ZI3Wb7tQd5o/WBQnQ-ibGHI/AAAAAAAAL7A/XG1Du4gcLi8Pi3dlZNzzSCJOEFoMiZ_KQCLcB/s640/Screen%2BShot%2B2016-10-29%2Bat%2B06.35.46.png" width="640" /></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">Selecting profile</td></tr>
</tbody></table>






