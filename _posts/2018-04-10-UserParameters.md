---
layout: post
title:  "User selected rsync parameters"
permalink: userparameters
---
Rsync utilizes a ton of parameters. RsyncOSX has only presented a few. Parameters are normally constructed as:

- --parameter=value `--exclude-from=/Volumes/home/user/exclude-list.txt`
- --parameter `--stats`, `--dry-run`

For a full list of parameters to rsync please see the [rsync docs](https://download.samba.org/pub/rsync/rsync.html).

#### Backup catalog by parameter to rsync

You can instruct rsync to save changed and deleted files in a separate backup catalog ahead of the change. This feature is utilized by setting the following parameters:

- `--backup` parameter instructs rsync to save changed files
- `--backup-dir` parameter where to save changed or deleted files before rsync synchronize source and destination
	- RsyncOSX does suggest a value for the `--backup-dir` but you might set it to whatever you want

![](/images/RsyncOSX/master/rsync/rsync.png)

#### Suffix on changed and deleted files

Rsync can also set a time stamp as suffix on files. This might be useful if there are several revisions of files. The --suffix parameter set suffix on files, suffix can be set on files together with the --backup parameter. One suffix might rename files which are either deleted or replaced newer files with a trailing date and time stamp.

- sample suffix FreeBSD
```
--suffix=`date +'%Y-%m-%d.%H.%M'`
```
- sample suffix Linux
```
--suffix=_$(date +%Y-%m-%d.%H.%M)
```

I have experienced some variations regarding the suffix. If you want to use suffix you might try an alternative suffix if the above is not working as expected. If so is true use  instead. You just have to try and see what works

The parameters in picture (below) instructs rsync to save changed files in catalog ../backup_Directory (relative to destination catalog) and suffix the backup file with timestamps. The above is enabled or disabled by select the backup button. The user might change the backup catalog. The backup catalog can either be absolute path or relative path. Default backup catalog is ../backup_Directory.

#### Passing user selected parameters to rsync

The user can set own parameters by using user in dropdown menu. Preset parameters are:

- `user`  - user selected parameter

RsyncOSX passes whatever set by user to rsync, parameters must be either:
- `--parameter=value` or
- `--parameter`

`delete` - delete the parameterdeletes the parameter when OK button is selected
