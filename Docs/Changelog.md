## Changelog

The main objective now is to get the application as stable as possible. Clean up of code and bug fixes are always an issue. I am using the application on a daily basis and it evolves during my own use. Any suggestions for new features, changed features and bug reports are more than welcome.


## Source code

Why release the code? Why not? The code is **not** example of neither writing decent Swift code, OO-development or applying the MVC-pattern. It all started as a project to learn Swift and I am still learning, every day. Coding is an art and to be really good at coding requires years of experience. My experience of coding is far from that ;-) But I am happy to share the code with anyone interested. Sharing of code is in my opinion the best way to get quality.

- [master](https://github.com/rsyncOSX/Version3.x/tree/master) for released version on GitHub


## Comments about use of RsyncOSX

RsyncOSX is downloaded more than 5,500 times from Macupdate and probably some times directly from this blog. I have no clue about how many uses RsyncOSX on a regularly basis and information about bugs discovered by users (I expect other users discovers bugs as well). There are no request for adding features, removing features as well. I would very much appreciate any comments from users about whatever regarding use of RsyncOSX, e-mails about bugs and suggestion for new features. Please drop me an e-mail on

- thomas.tilbakemelding@gmail.com
- or add an [Issue](https://github.com/rsyncOSX/Version3.x/issues)

The e-mail is for reading only. I will **not share** nor **spam** any e-mails or e-mail addresses sent to this address.

## Version 3.6.5 release candidate
- release candidate (is updated now and then when bugs are discovered)
- updated **20 November 2016**
- new About view (links to docs, changelog and check for new versions)
- fixed a bug in Edit configurations (reset values when new configuration is loaded)
- some minor cleanup of code
- download [release candidate](https://github.com/rsyncOSX/Version3.x/releases)

## Version 3.6.1

- released 15 November 2016
- [logs part](https://github.com/rsyncOSX/Documentation/blob/master/Docs/Logging.md) is changed, text search for **remote server**, **local catalog** or **executed date/time**
- there is a bug in deleting ssh-port - **fixed**
- there is a bug in enabling Profiles menu when RsyncOSX is started on a Mac for the first time (Profiles menu is not enabled) - **fixed**
- sometimes output from rsync is set to **nil** (in RsyncOSX), doing an unwrap of nil value causes RsyncOSX to crash - **fixed**


## Version 3.5.5

- new image updated **10 November 2016** : some minor GUI tweaks and automatic dismiss after 10 seconds in some of the views
- new image updated **5 November 2016** : if selecting new profile before background check for connection is completed RsyncOSX might crash, fix is done and new image is uploaded. Background check is executed when main view loads and remote servers not responding is marked red.
- released 3 November 2016
- fixed a couple of bugs in automatic dismiss of popup views (when scheduled backups are running and in main view a popup informs of backup)
- some minor refactor of code


## Version 3.5.1

- new image updated **2 November 2016** : added check for optional version and path of rsync
- new image updated **1 November 2016** : "moved" GUI updates in background (Scheduled operations) to main thread - making RsyncOSX unstable if not - throwing "CoreAnimation: warning, deleted thread with uncommitted CATransaction" if not
- **caution** : a bug in Scheduled jobs caused version 3.5.1 released 30 October 2016 to crash - a new image of version 3.5.1 uploaded late 30 October 2016.
- released 30 October 2016
- fixed a bug in version 3.5.0 deleting/stopping schedules causing a nil pointer exception and crash
  - bug was "introduced" when compiling RsyncOSX with latest release version 8.1 of Xcode
- notify new versions of RsyncOSX by delegate
- mainly a maintenance release, some bigger internal changes and some GUI tweaks
- RsyncOSX is more stable than ever
  - replaced states by work queue (using states get complex even with a few states)
  - I am learning Swift every day and [refactor code](https://en.wikipedia.org/wiki/Code_refactoring) is important
- code ([master](https://github.com/rsyncOSX/Version3.x/tree/master)) at Github is updated with last commits
- added double click for executing single task and select profile
  - double click first time executes a dry run, another double click after dryrun executes the real task
  - enable/disable double click in user configuration


## Version 3.4.1

- released 20 October 2016
- copy and paste was by mistake not in 3.4.0 - now it is...
- there was an issue with Copy files (search and copy single files or catalogs) - if you experience any problems with copy files in version 3.4.1 please update to last image of version 3.4.1


## Version 3.4.0

- released 19 October 2016
- added profiles - select profiles from the File meny, profiles is just new catalogs for storing configurations and schedules files.
- backup of single files in Add view, only backup part is added for single files, use Copy Files to search and restore single files
- some minor internal cleanup and fixes, adjusted Copy Files view
- added abort in Copy Files (terminates search process)
- in logs view selecting row selects logs for selected remote server
- removed test mode in RsyncOSX - replaced by profiles
- user configuration available from Main tab, Add tab and Schedule tab
- in main tab when rsync is changed in user configuration, if row is selected rsync command in view is updated
- counting of files and directories from rsync output is more robust, only version 3.x of rsync counting directories remote


## Version 3.3.0

- released 6 October 2016
- capture of more precise info about files, tested on both stock version on rsync and 3.1.2 of rsync (only version 3.x counts directories)
- fixed a bug not saving path for other version of rsync
- added backup in rsync parameters
  - changed files are moved to backup location (default ../backup) and appended a timestamp before updated files are transferred from source to destination
  - useful when saving versions of e.g. documents
- fixed a memory leak in scheduling of tasks
  - after the last release 4 Oct 2016 it seems that there are no memory leaks (at least the graphic memory debugger in Xcode reports no leaks as well as the Xcode instrument Memory Leaks)


## Version 3.1.5

- released 24 Sept 2016
  - image is updated 26 Sept 2016 (fixed a few minor glitches)
- added detailed logging
  - logging switch on/off in Configuration
- hopefully no more releases for some time after this release


## Version 3.1.0

- updated 22 Sept (released 20 Sept 2016)
- scheduling of tasks
- added (22 Sept 2016) adding local volumes by graphical window or drag and drop from Finder
- a few minor bug fixes (22 Sept 2016)


## Version 3.0.5

- updated 15 Sept 2016
- copy of single files or catalogs from remote storage
  - doing a restore require to press the Estimate button twice, once for a -- dry-run (estimate) and the the real run (execute)
- some visual enhancements
- Scheduling of tasks is **not yet** included in this version (will be in version 3.1.0)
  - tasks might be scheduled in version 3.0.5 but not executed


## Version 3.0.0

- built on macOS 10.12 GM by Xcode 8 GM (GM = "gold master")
- supports macOS 10.11 and macOS 10.12

What is **NOT** implemented in version 3.0

- no execution of Scheduled task, but scheduled task may be added, stopped and deleted
  - the code for execution of scheduled tas has to be revised and tested
  - will come in version 3.1.0
- no copy of single files or catalogs from remote servers
  - will come in version 3.1.0
- no detailed logging
  - will come in version 3.1.0


## Changelog prior version 3.0.0

Changelog prior to version 3.0.0 is deleted. The initial release was 14 March 2016 and code is rewritten since the initial release.


## Version 0.5 beta

- initial listing 14 March 2016, released on MacUpdate as well
