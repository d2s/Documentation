---
layout: post
title:  "Parameters to rsync"
permalink: Parameters
---
The website LibreByte has written an article [14 Practical examples of the rsync command](http://www.librebyte.net/en/gnulinux/14-practical-examples-of-the-rsync-command/). One of the examples is instructing rsync to store backups of files in a backup folder and rename old files by a date suffix.

Rsync utilizes a ton of parameters. RsyncOSX has only presented a few. Parameters are normally constructed as:

- `--parameter=value`
	- sample `--exclude-from=/Volumes/home/user/Documents/exclude-list.txt`
- `--parameter`
	- sample `--stats`, `--dry-run`

See also the [standard parameters](RsyncParameters.md) to rsync.

## Saving changed and deleted files in a backup catalog by parameter to rsync

You can instruct rsync to save changed and deleted files in a separate backup catalog ahead of the change. This feature is utilized by setting the following parameters:

- `--backup` parameter instructs rsync to save changed files
- `--backup-dir` parameter where to save changed or deleted files before rsync synchronize source and destination

RsyncOSX does suggest a value for the `--backup-dir` but you might set it to whatever you want.

### Setting suffix on saved files

Rsync can also set a time stamp as suffix on files. This might be useful if there are several revisions of files.

- `--suffix` parameter set suffix on files, suffix can be set on files together with the `--backup`parameter. One suffix might rename files which are either deleted or replaced newer files with a trailing date and time stamp.
	- sample suffix <code>--suffix= _\`date +'%Y-%m-%d.%H.%M'` </code> (works on FreeBSD)
	- sample suffix <code>--suffix= _$(date +%Y-%m-%d.%H.%M)`</code> (works on Linux)

I have experienced some variations regarding the suffix. If you want to use suffix you might try an alternative suffix if the above is not working as expected. If so is true use  instead. You just have to try and see what works

The parameters in picture (below) instructs rsync to save changed files in catalog `../backup_Directory` (relative to destination catalog) and `suffix` the backup file with timestamps. The above is enabled or disabled by select the `backup` button. The user might change the backup catalog. The backup catalog can either be absolute path or relative path. Default backup catalog is `../backup_Directory`.
![New configurations](/images/RsyncOSX/master/rsync/rsync4.png)

## RsyncOSX passing userselected parameters to rsync

The user can set own parameters by using `user` in dropdown menu. Preset parameters are:

- `user` - _user selected_ parameter
	- RsyncOSX passes whatever set by user to rsync, parameters must be either `--parameter=value` or `--parameter`
- `--stats` - produces some more statistics
	- parameter is forced on in dry-ryn to collect info about run
- `--backup` - instructs rsync to backup changed files
	- remember rsync is set to synchronize the source and destination folder (see [how to use RsyncOSX](HowtoUseRsyncOSX.md)), by setting this parameter instructs rsync to store changed files
- `--backup-dir` - where to store changed or deleted files before rsync synchronize source and destination
- `--exclude-from` - path to file which stores file patterns to **exclude** from rsync backup
- `--include-from` - path to file which store file patterns to **include** from rsync backup
- `--files-from` - path to file which store what to backup
- `--max-size` - set max size of files to backup
	- sample `--max-size=5MB` , files with size bigger than 5 megabyte (MB) are omitted
- `delete` - delete the parameter
	- deletes the parameter when `OK` button is selected
	- or just delete the `value` string
