<h2> Changelog </h2>
 
The main objective now is to get the application as stable as possible. Clean up of code and bugfixes are always an issue. I am using the application on a daily basis and it evolves during my own use. Any suggestions for new features, changed features and bug reports are more than welcome.

<h2> Source code </h2>
Why release the code? Why not? The code is NOT example of neither writing decent Swift code, OO-development or applying the MVC-pattern. It all started as a project to learn Swift and I am still learning, every day. Coding is an art and to be really good at coding requires years of experience. My experience of coding is far from that ;-) But I am happy to share the code with anyone interested. Sharing of code is in my opinion the best way to get quality.</div>
<div>
<ul>
<li><a href="https://github.com/rsyncOSX/Version3.x/tree/master" target="_blank">master</a> for released version on github</li>
</ul>

<h2>Comments about use of RsyncOSX</h2>
RsyncOSX is downloaded about 5,000 times from Macupdate and probably some times directly from this blog. I have no clue about how many uses RsyncOSX on a regularly basis and information about bugs discovered by users (I expect other users discovers bugs as well). There are no request for adding features, removing features as well.

I would very much appreciate any comments from users about whatever regarding use of RsyncOSX, e-mails about bugs and suggestion for new features. Please drop me an e-mail on
<ul>
<li>thomas.tilbakemelding@gmail.com </li>
<li>or add a comment on this page (will not be published)</li>
</ul>
The e-mail is for reading only. I will NOT share any e-mails nor e-mail adresses sent to this address. And I will NOT spam, only read. Any feedback will be a motivation for me to continue develop RsyncOSX.

<h2>Version 3.5.5</h2>
<ul>
<li>new image updated <b>5 November 2016</b> : if selecting new profile before background check for connection is completed RsyncOSX might crash, fix is done and new image is uploaded. Background check is executed when main view loads and remote servers not responding is marked red.</li>
<li>released 3 November 2016</li>
<li>fixed a couple of bugs in automatic dismiss of popup views (when scheduled backups are running and in main view a popup informs of backup)</li>
<li>some minor refactor of code</li>
</ul>

<h2>Version 3.5.1</h2>
</div>
<div>
<ul>
<li>new image updated <b>2 November 2016</b> : added check for optional version and path of rsync</li>
<li>new image updated <b>1 November 2016</b> : "moved" GUI updates in background (Scheduled operations) to main thread - making RsyncOSX unstable if not - throwing "CoreAnimation: warning, deleted thread with uncommitted CATransaction" if not</li>
<li><b>caution</b> : a bug in Scheduled jobs caused version 3.5.1 released 30 October 2016 to crash - a new image of version 3.5.1 uploaded late 30 October 2016.</li>
<li>relased 30 October 2016</li>
<li>fixed a bug in version 3.5.0 deleting/stopping schedules causing a nil pointer exeption and crash</li>
<ul>
<li>bug was "introduced" when compiling RsyncOSX with latest release version 8.1 of Xcode </li>
</ul>
<li>notify new versions of RsyncOSX by delegate</li>
<li>mainly a maintenance release, some bigger internal changes and some GUI tweaks</li>
<li>RsyncOSX is more stable than ever </li>
<ul>
<li>replaced states by work queu (using states get complex even with a few states)</li>
<li>I am learning Swift every day and <a href="https://en.wikipedia.org/wiki/Code_refactoring" target="_blank">refactor code</a> is important</li>
<ul>
</ul>
</ul>
<li>code (<a href="https://github.com/rsyncOSX/Version3.x/tree/master" target="_blank">master</a>) at Github is updated with last commits</li>
<li>added double click for executing single task and select profile</li>
<ul>
<li>double click first time executes a dry run, another double click after dryrun executes the real task</li>
<li>enable/disable double click in userconfiguration</li>
</ul>
<ul>
<ul>
</ul>
</ul>
</ul>
</div>
<h2>
Version 3.4.1</h2>
<div>
<ul>
<li>released 20 October 2016</li>
<li>copy and paste was by mistake not in 3.4.0 - now it is...</li>
<li>there was an issue with Copy files (search and copy single files or catalogs) - if you experience any problems with copy files in version 3.4.1 please update to last image of version 3.4.1</li>
</ul>
</div>
<h2>
Version 3.4.0</h2>
<div>
<ul>
<li>released 19 October 2016</li>
<li>added profiles - select profiles from the File meny, profiles is just new catalogs for storing configurations and schedules files. </li>
<li>backup of single files in Add view, only backup part is added for single files, use Copy Files to search and restore single files</li>
<li>some minor internal cleanup and fixes, adjusted Copy Files view</li>
<li>added abort in Copy Files (terminates search process)</li>
<li>in logs view selecting row selects logs for selected remote server</li>
<li>removed testmode in RsyncOSX  - replaced by profiles</li>
<li>userconfiguration available from Main tab, Add tab and Schedule tab</li>
<li>in main tab when rsync is changed in userconfiguration, if row is selected rsync command in view is updated</li>
<li>counting of files and directories from rsync output is more robust, only version 3.x of rsync counting directories remote</li>
</ul>
</div>
<h2>
Version 3.3.0</h2>
<div>
<ul>
<li>released 6 October 2016</li>
<li>capture of more precise info about files, tested on both stock version on rsync and 3.1.2 of rsync (only version 3.x counts directories)</li>
<li>fixed a bug not saving path for other version of rsync</li>
<li>added backup in rsync parameters</li>
<ul>
<li>changed files are moved to backup location (default ../backup) and appended a timestamp before updated files are transferred from source to destination</li>
<li>usefull when saving versions of e.g. documents</li>
</ul>
<li>fixed a memory leak in scheduling of tasks</li>
<ul>
<li>after the last release 4 Oct 2016 it seems that there are no memory leaks (at  least the graphic memory debugger in Xcode reports no leaks as well as the Xcode instrument Memory Leaks)</li>
</ul>
</ul>
</div>
</div>
<div>
<ul><ul>
</ul>
</ul>
<div class="separator" style="clear: both; text-align: center;">
</div>
<div>
<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;"><tbody>
<tr><td style="text-align: center;"><a href="https://1.bp.blogspot.com/-s1F4DN2g4SY/V_PwNUJvG0I/AAAAAAAAL3Y/1Y2cP7uQYSM2b8FcPlpwC9b7DN2AEr3BACLcB/s1600/Screen%2BShot%2B2016-10-04%2Bat%2B20.07.39.png" imageanchor="1" style="margin-left: auto; margin-right: auto;"><img border="0" height="211" src="https://1.bp.blogspot.com/-s1F4DN2g4SY/V_PwNUJvG0I/AAAAAAAAL3Y/1Y2cP7uQYSM2b8FcPlpwC9b7DN2AEr3BACLcB/s400/Screen%2BShot%2B2016-10-04%2Bat%2B20.07.39.png" width="400" /></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">Toggle backup, add or delete three last parameters</td></tr>
</tbody></table>
</div>
</div>
<div class="separator" style="clear: both; text-align: center;">
</div>
<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;"><tbody>
<tr><td style="text-align: center;"><a href="https://2.bp.blogspot.com/-ESL1yI-5nNA/V_Z8MtMg6ZI/AAAAAAAAL4M/HoIgUu6KK8YOFCgU3RebnpjHMMMKNt4EwCLcB/s1600/Screen%2BShot%2B2016-10-06%2Bat%2B18.06.18.png" imageanchor="1" style="margin-left: auto; margin-right: auto;"><img border="0" height="211" src="https://2.bp.blogspot.com/-ESL1yI-5nNA/V_Z8MtMg6ZI/AAAAAAAAL4M/HoIgUu6KK8YOFCgU3RebnpjHMMMKNt4EwCLcB/s400/Screen%2BShot%2B2016-10-06%2Bat%2B18.06.18.png" width="400" /></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">Capture info from rsync (info fields in left bottom of view)</td></tr>
</tbody></table>
<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;"><tbody>
<tr><td style="text-align: center;"><a href="https://4.bp.blogspot.com/-P6KWaFQGCns/V_Z8MjvGEFI/AAAAAAAAL4I/HxBTpHyngBg84ezOO31EIRqx7K9w8cl_QCLcB/s1600/Screen%2BShot%2B2016-10-06%2Bat%2B18.09.34.png" imageanchor="1" style="margin-left: auto; margin-right: auto;"><img border="0" height="210" src="https://4.bp.blogspot.com/-P6KWaFQGCns/V_Z8MjvGEFI/AAAAAAAAL4I/HxBTpHyngBg84ezOO31EIRqx7K9w8cl_QCLcB/s400/Screen%2BShot%2B2016-10-06%2Bat%2B18.09.34.png" width="400" /></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">Logs from both stock version of rsync and version 3.2.1 of rsync</td></tr>
</tbody></table>
<br />
<h2>
Version 3.1.5</h2>
<div>
<ul>
<li>please see the <a href="https://rsyncosx.blogspot.no/2016/08/rsyncosx-version-3-alfa.html" target="_blank">notes</a> about version 3.1.5</li>
<li>released 24 Sept 2016</li>
<ul>
<li>image is updated 26 Sept 2016 (fixed a few minor glitches)</li>
</ul>
<li>added detailed logging</li>
<ul>
<li>logging switch on/off in Configuration</li>
</ul>
<li>hopefully no more releases for some time after this release</li>
</ul>
</div>
<h2>
Version 3.1.0</h2>
<div>
<ul>
<li>updated 22 Sept (released 20 Sept 2016)</li>
<li>scheduling of tasks</li>
<li>added (22 Sept 2016) adding local volumes by graphical window or drag and drop from Finder</li>
<li>a few minor bugfixes (22 Sept 2016)</li>
</ul>
</div>
<div>
<h2>
Version 3.0.5</h2>
<div>
<ul>
<li>updated 15 Sept 2016</li>
<li>copy of single files or catalogs from remote storage</li>
<ul>
<li>doing a restore requiere to press the Estimate button twice, once for a --dry-run (estimate) and the the real run (execute)</li>
</ul>
<li>some visual enhancements</li>
<li>Scheduling of tasks is <b>not yet</b> included in this version (will be in version 3.1.0)</li>
<ul>
<li>tasks might be scheduled in version 3.0.5 but not executed</li>
</ul>
</ul>
<div>
<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;"><tbody>
<tr><td style="text-align: center;"><a href="https://3.bp.blogspot.com/-RhBKjjUNw1Y/V9ljGQ0RdbI/AAAAAAAAL1U/wAWgmwftWaUKDcMOoz_LVRuriPJ5TAEywCLcB/s1600/Screen%2BShot%2B2016-09-14%2Bat%2B16.42.20.png" imageanchor="1" style="margin-left: auto; margin-right: auto;"><img border="0" height="210" src="https://3.bp.blogspot.com/-RhBKjjUNw1Y/V9ljGQ0RdbI/AAAAAAAAL1U/wAWgmwftWaUKDcMOoz_LVRuriPJ5TAEywCLcB/s400/Screen%2BShot%2B2016-09-14%2Bat%2B16.42.20.png" width="400" /></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">Copy file or catalog from remote server to user selected local catalog</td></tr>
</tbody></table>
</div>
</div>
<h2>
Version 3.0 </h2>
<ul>
<li>built on macOS 10.12 GM by Xcode 8 GM (GM = "gold master")</li>
<li>supports macOS 10.11 and macOS 10.12</li>
</ul>
<div>
<br /></div>
<div>
What is <b>NOT</b> implemented in version 3.0</div>
<br />
<ul>
<li>no execution of Scheduled task, but scheduled task may be added, stopped and deleted</li>
<ul>
<li>the code for execution of scheduled tas has to be revised and tested</li>
<li>will come in version 3.1.0</li>
</ul>
<ul>
</ul>
<li>no copy of single files or catalogs from remote servers</li>
<ul>
<li>will come in version 3.1.0</li>
</ul>
<li>no detailed logging</li>
<ul>
<li>will come in version 3.1.0</li>
</ul>
</ul>
<h2>
Version 2.0.0 (French)</h2>
</div>
<div>
<div>
<ul>
<li>released 10 Sept 2016 for:</li>
<ul>
<li>macOS El Capitan (OS X 10.11) and macOS Sierra (OS X 10.12)</li>
</ul>
<li>French version only</li>
<ul>
<li>the French version is translated by Hervé Turri (tweeter @hturri) from Lyon, France</li>
</ul>
<li>converted to Swift 3.0  and built by Xcode 8 GM</li>
<ul>
</ul>
</ul>
<h2>
Version 1.7.0</h2>
<div>
<ul>
<li>released 28 July 2016</li>
<li>a rewrite (interal details) of how Scheduled backups are working (see <a href="https://rsyncosx.blogspot.no/2016/04/issues.html" target="_blank">Issue</a> page)</li>
<ul>
<li>new code for Scheduled backups are more robust and reliable</li>
</ul>
<li>some optimizing of code (and cleanup)</li>
<li>and some bugfixes as well</li>
</ul>
</div>
<div>
<h2>
Version 1.5.0</h2>
<div>
<ul>
<li>released 9 July 2016</li>
<li>primarily a maintenance release (and last release this summer)</li>
<li>cleanup of code (by this also fixed some bugs) and bugfixes</li>
<li>added new Configuration</li>
<li>added more info about tasks in some windows</li>
<li>a version for OSX 10.10 is available for <a href="https://rsyncosx.blogspot.no/2016/05/version-for-testing.html" target="_blank">test</a> (if would be happy if anyone testing the 10.10 compiled version can verify its working or not)</li>
</ul>
</div>
<br />
<div class="separator" style="clear: both; text-align: center;">
<a href="https://3.bp.blogspot.com/-ZI3hgGlLhBI/V4C8p4rXO3I/AAAAAAAALq0/7JPf2XMBXyEGSwbMwCCY07uf6Wdo_irbACLcB/s1600/Screen%2BShot%2B2016-07-09%2Bat%2B10.42.00.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="532" src="https://3.bp.blogspot.com/-ZI3hgGlLhBI/V4C8p4rXO3I/AAAAAAAALq0/7JPf2XMBXyEGSwbMwCCY07uf6Wdo_irbACLcB/s640/Screen%2BShot%2B2016-07-09%2Bat%2B10.42.00.png" width="640" /></a></div>
<br />
<div class="separator" style="clear: both; text-align: center;">
<a href="https://4.bp.blogspot.com/-Bm1Dq482XQo/V4C8p_XVyMI/AAAAAAAALq4/JVMajdINkE8bGRDg4CA6PWUp1066y72gACLcB/s1600/Screen%2BShot%2B2016-07-09%2Bat%2B10.44.56.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="348" src="https://4.bp.blogspot.com/-Bm1Dq482XQo/V4C8p_XVyMI/AAAAAAAALq4/JVMajdINkE8bGRDg4CA6PWUp1066y72gACLcB/s640/Screen%2BShot%2B2016-07-09%2Bat%2B10.44.56.png" width="640" /></a></div>
<br />
<div class="separator" style="clear: both; text-align: center;">
<a href="https://4.bp.blogspot.com/-ed5s0CiFJyM/V4C8qAXixYI/AAAAAAAALq8/Wvi1CG8HHdUBJMRKhuUE1dZQCJS-tOLLwCLcB/s1600/Screen%2BShot%2B2016-07-09%2Bat%2B10.46.40.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="348" src="https://4.bp.blogspot.com/-ed5s0CiFJyM/V4C8qAXixYI/AAAAAAAALq8/Wvi1CG8HHdUBJMRKhuUE1dZQCJS-tOLLwCLcB/s640/Screen%2BShot%2B2016-07-09%2Bat%2B10.46.40.png" width="640" /></a></div>
<h2>
Version 1.3.5</h2>
<div>
<ul>
<li>released 1 July 2016</li>
<li>minor bugfixes</li>
<li>added abort button in single file and directory restore (in Files menu)</li>
<li>new application icon</li>
<li>set level of logging results of tasks (detailed logging on/off) in Configuration menu</li>
<li>set optional versions of rsync and optional paths in Configuration menu</li>
<li>cleaned up code </li>
</ul>
</div>
<h2>
Version 1.3.0</h2>
</div>
</div>
<div>
<ul>
<li>released 23 June 2016</li>
<li>search and restore single files or directories from remote storage to local disk</li>
<li>minor bugfixes</li>
</ul>
</div>
<h2>
Version 1.2.5</h2>
<div class="p1">
</div>
<ul>
<li>released 12 June 2015 (minor update to the 11 June version of 1.25 in communicate RsyncOSX in testmode or not)</li>
<li>when a <b>remote server</b> is not available (no TCP connections) the row is marked <span style="color: red;">red text</span></li>
<ul>
<li>the check is done every time the main window is loaded</li>
<li>the batch task is already aborting if a remote server is offline (when the batch reaches the task)</li>
</ul>
<li>when there is a <b>future schedule</b> on a task, task is marked with <b>number</b> of future schedules</li>
<li>reimplemented how <b>user added parameters</b> to rsync works</li>
<ul>
<li>in later version (after 1.2.5) will include user can add parameters to include in dropdown menu (user added parameters will be stored to permanent store and loaded during startup)</li>
</ul>
<li>more tooltips (some tooltips are in version 1.2.1 already)</li>
<li>always bugfixes... </li>
</ul>
<br />
<a href="https://4.bp.blogspot.com/-6fLvLnWFFe8/V1pn5LLdPTI/AAAAAAAALeM/8L7XEM86pswagojAOpigVvI8glxI0AIigCLcB/s1600/Screen%2BShot%2B2016-06-09%2Bat%2B19.39.15.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="316" src="https://4.bp.blogspot.com/-6fLvLnWFFe8/V1pn5LLdPTI/AAAAAAAALeM/8L7XEM86pswagojAOpigVvI8glxI0AIigCLcB/s640/Screen%2BShot%2B2016-06-09%2Bat%2B19.39.15.png" width="640" /></a></div>
<br />
<div class="separator" style="clear: both; text-align: center;">
<a href="https://2.bp.blogspot.com/-XSy5ROGdOb8/V1pn5GpYGJI/AAAAAAAALeI/byev9W2h6_YmIw9sXulkhagRGEgrtoMRgCLcB/s1600/Screen%2BShot%2B2016-06-09%2Bat%2B19.41.46.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="336" src="https://2.bp.blogspot.com/-XSy5ROGdOb8/V1pn5GpYGJI/AAAAAAAALeI/byev9W2h6_YmIw9sXulkhagRGEgrtoMRgCLcB/s640/Screen%2BShot%2B2016-06-09%2Bat%2B19.41.46.png" width="640" /></a></div>
<br />
<div>
<ul>
</ul>
<div class="separator" style="clear: both; text-align: center;">
</div>
<br />
<div class="separator" style="clear: both; text-align: center;">
</div>
<h2>
</h2>
<h2>
</h2>
<h2>
Version 1.2.1</h2>
<div>
<ul>
<li>version 1.2.1 released 3 June 2016</li>
<li>fixed a critical bug adding new configurations (New button)</li>
<ul>
<li>bug may cause existing configurations to be erased</li>
</ul>
</ul>
</div>
<h2>
Version 1.2.0</h2>
<div>
<ul>
<li>version 1.2.0 image was updated 29 May 2016</li>
<li>the counter for starting scheduled jobs is now starting when new schedule is added</li>
<ul>
<li>in previous image of version 1.2.0 the main execute window had to be closed and opened before timer starts</li>
</ul>
</ul>
</div>
<h2>
Version 1.2.0</h2>
<div>
<ul>
<li>version 1.2.0 released 28 May 2016</li>
<li>rewrite of internals, less readings from persistent store and more from memory, performance</li>
<li>preventing change of schedules or configurations when a scheduled task is running</li>
<li>bugfixes (always)</li>
<li>counter in main view next scheduled task</li>
</ul>
</div>
<div>
<h2>
Version 1.1.2</h2>
</div>
<div>
<ul>
<li>version 1.1.2 was updated 27 May 2016</li>
<ul>
<li>added functionality for preventing change of schedule or configuration when a scheduled task is running</li>
</ul>
<li>version 1.1.2 released 25 May 2016</li>
<li>notification (in main window)  when scheduled task is running</li>
<li>fixed bug with hidden key</li>
<li>and as always fighting bugs...</li>
</ul>
</div>
<div>
<h2>
Version 1.1.1</h2>
</div>
<div>
<ul>
<li>version 1.1.1 released 23 May 2016</li>
<li>fixed some bugs in schedule tasks</li>
</ul>
</div>
<div>
<div>
<h2>
Version 1.1.0 </h2>
</div>
<div>
<ul>
<li>version 1.1.0 is released 22 May 2016</li>
<li>implemented scheduled backups</li>
<li>more logging about executed tasks </li>
<li>more bugfixing</li>
</ul>
</div>
</div>
<div>
<h2>
Version 1.0.21</h2>
</div>
<div>
<ul>
<li>version 1.0.21 is released 28 April 2016</li>
<li>leaving beta</li>
<li>fixed some minor bugs</li>
</ul>
</div>
<div>
<h2>
Version 1.0.19 beta</h2>
</div>
<div>
<ul>
<li>version 1.0.19 beta is released 27 April 2016</li>
<li>fixed bug which caused application to hang</li>
</ul>
</div>
<div>
<h2>
Version 1.0.18 beta</h2>
</div>
</div>
<div>
<ul>
<li>version 1.0.18 beta is released 26 April 2016</li>
<li>if new ssh-port in parameters to rsync (other than standard port 22), new port is also required in startup of application (forgot it)</li>
</ul>
</div>
<div>
<h2>
Version 1.0.17 beta</h2>
</div>
<div>
<ul>
<li>version 1.0.17 beta is released 26 April 2016</li>
<li>more bugfixes</li>
<li>fixed the kill task (by <code>⌘+k</code>)</li>
<li>application checks if there is a new version released</li>
</ul>
</div>
<div>
<h2>
Version 1.0.16 beta</h2>
<div>
<ul>
<li>version 1.0.16 beta is released 24 April 2016</li>
<li>fixed a bug reading timestamps on server after copy from remote server</li>
</ul>
</div>
<h2>
Version 1.0.15 beta</h2>
<div>
<ul>
<li>version 1.0.15 beta is released 23 April 2016</li>
<li>kill task (by <code>⌘+k</code>)</li>
<li>bug fixes</li>
</ul>
</div>
<h2>
Version 1.0.14 beta</h2>
<div>
<ul>
<li>version 1.0.14 beta is released 19 April 2016</li>
<li>change ssh port (standard is port 22)</li>
<ul>
<li>changes parameter <code>-e ssh</code> to <code>-e "ssh -port xxxx"</code></li>
</ul>
<li>enable rsync daemon</li>
<ul>
<li>if parameter <code>--password-file=FILE</code> is used rsync daemon must be enabled</li>
</ul>
<li>user selected parameters are implemented, probably still needs some more work to choose from a set of advanced parameters - for the moment the user can add any parameters</li>
<li>even more cleanup of views and bugfixes (as always)</li>
<li>better informal view when batch tasks are executing</li>
<li>by selecting the Verify button a --dry-run task is executed, the buttons title changes to Show when task is completed and result of task is ready</li>
<li>any added user params will be shown in the main view for executing tasks</li>
</ul>
</div>
<h2>
Version 0.7 and 0.75 beta</h2>
<ul>
<li>version 0.7 beta released 1 April 2016 (and updated 12 April 2016 - bugfixes)</li>
<li>new functionality to verify/check that local files needs to be "restored" before commencing any work on local Mac. This functionality is helpful when working on several Mac desktops. </li>
<li>more cleanup and bugfixes from version 0.7 to 0.75</li>
<li>more "precise" calculation (informal only) of files to be transferred (dont calculate directories)</li>
<ul>
<li>this feature is informal only, rsync keeps tracks of all the details and diffs between source and destination</li>
</ul>
</ul>
<div>
<h2>
</h2>
<h2>
Version 0.65 beta</h2>
<div>
<ul>
<li>released 18 March 2016</li>
<li>cleaned up view for adding tasks to RsyncOSX</li>
<li>new tasks added before saving configuration to permanent store</li>
<li>user can select/deselect which tasks to be saved to permanent store</li>
<li>cleaning of code and general bugfixes</li>
</ul>
</div>
</div>
<div class="separator" style="clear: both; text-align: center;">
</div>
<h2>
</h2>
<h2>
Version 0.6 beta</h2>
<h2>
<ul style="font-size: medium; font-weight: normal;">
<li>released 16 March 2016</li>
<li>changed functionality for adding/deleting tasks for batch run</li>
<li>cleaning of code and general bugfixes</li>
</ul>
</h2>
<div>
<div class="separator" style="clear: both; text-align: center;">
</div>
<ul>
</ul>
</div>
<div>
<h2>
</h2>
<h2>
Version 0.5 beta</h2>
<ul>
<li>initial listing 14 March 2016, released on MacUpdate as well</li>
</ul>
</div>
</div>