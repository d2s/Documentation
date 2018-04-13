---
layout: post
title:  "Copy single files or catalogs"
permalink: CopySingleFiles
---
Index of [RsyncOSX documentation](/AboutRsyncOSX).

Copy file and volume enables the user to select single file or catalogs for restore to a selected local storage. The _source_ for copy is either _selected row in Execute view_ or if selecting `Select` button drop down list of all backup locations.

* button is labeled `Select` if no location is selected in main view, pressing select pops up a list of backup locations
* button is labeled `Get files` if location is selected, either in main view or by drop down list (information about source is filled in)
* if `Reset` button is selected button is labeled `Get source`, if selected list of source is listed in drop list

The temporary path for restoring single file or directory can be set in Configuration. The path can be set to any directory or changed to a other directory for one session only.
![Main view](/images/screenshots/master/userconfig.png)
Pressing `Get files` button starts the job to collect list of files and catalogs stored on remote server. Or job to get files is started by double click on row in list of sources.
![Schedule](/images/screenshots/master/restore/source.png)
![Schedule](/images/screenshots/master/restore/source1.png)
![Schedule](/images/screenshots/master/restore/source3.png)
All backup locations are presented including backups to local volumes. For local volumes it might be better to use Finder in macOS. But it works for local volumes as well.

Double click on row gets list of files from backup location. If single click select `Get files`.
![Schedule](/images/screenshots/master/restore/copy1.png)
List of files and folders stored at remote server.

To restore file or directory to a temporary local directory either `doubleclick` on row or select `estimate`. A doubleclick executes the restore action in one go.

The views below are from a previous version of RsyncOSX. The size of each row is not available in the current version.
![Schedule](/images/screenshots/master/restore/copy2.png)
If `estimate` button is selected a restore is a two step task, first a --dry-run and then the real run.
