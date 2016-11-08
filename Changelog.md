<h2> ChangeLog </h2>
 
The main objective now is to get the application as stable as possible. Clean up of code and bugfixes are always an issue. I am using the application on a daily basis and it evolves during my own use. Any suggestions for new features, changed features and bug reports are more than welcome.

<h2> Source code </h2>
Why release the code? Why not? The code is NOT example of neither writing decent Swift code, OO-development or applying the MVC-pattern. It all started as a project to learn Swift and I am still learning, every day. Coding is an art and to be really good at coding requires years of experience. My experience of coding is far from that ;-) But I am happy to share the code with anyone interested. Sharing of code is in my opinion the best way to get quality.</div>
<div>
<ul>
<li><a href="https://github.com/rsyncOSX/Version3.x/tree/master" target="_blank">master</a> for released version on github</li>
</ul>

<h2>Comments about use of RsyncOSX</h2>
RsyncOSX is downloaded about 5,000 times from Macupdate and probably some times directly from this blog. I have no clue about how many uses RsyncOSX on a regularly basis and information about bugs discovered by users (I expect other users discovers bugs as well). There are no request for adding features, removing features as well.

I would very much appreciate any comments from users about whatever regarding use of RsyncOSX, e-mails about bugs and suggestion for new features. Please drop me an e-mail on </br>

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
</ul>
</div>

<h2>Version 3.4.1</h2>

<ul>
<li>released 20 October 2016</li>
<li>copy and paste was by mistake not in 3.4.0 - now it is...</li>
<li>there was an issue with Copy files (search and copy single files or catalogs) - if you experience any problems with copy files in version 3.4.1 please update to last image of version 3.4.1</li>
</ul>
<h2> Version 3.4.0</h2>
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
<h2>Version 3.3.0</h2>

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

<h2>Version 3.1.5</h2>

<ul>
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

<h2>Version 3.1.0</h2>

<ul>
<li>updated 22 Sept (released 20 Sept 2016)</li>
<li>scheduling of tasks</li>
<li>added (22 Sept 2016) adding local volumes by graphical window or drag and drop from Finder</li>
<li>a few minor bugfixes (22 Sept 2016)</li>
</ul>

<h2>Version 3.0.5</h2>

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

<h2>Version 3.0.0 </h2>
<ul>
<li>built on macOS 10.12 GM by Xcode 8 GM (GM = "gold master")</li>
<li>supports macOS 10.11 and macOS 10.12</li>
</ul>
What is <b>NOT</b> implemented in version 3.0
<ul>
<li>no execution of Scheduled task, but scheduled task may be added, stopped and deleted</li>
<ul>
<li>the code for execution of scheduled tas has to be revised and tested</li>
<li>will come in version 3.1.0</li>
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

<h2>Changelog before version 3.0.0</h2>
Changelog prior to version 3.0.0 is deleted. The inital release was 14 March 2016 and code is rewritten since the initial release. 

<h2>Version 0.5 beta</h2>
<ul>
<li>initial listing 14 March 2016, released on MacUpdate as well</li>
</ul>
