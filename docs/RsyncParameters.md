## Rsync parameters

Index of [RsyncOSX documentation](https://rsyncosx.github.io/Documentation/).
 
RsyncOSX implements standard parameters which are working fine for simple backup and restore tasks. The actual parameters used in tasks is depended upon executing rsync over _network connection_ or not. Which _standard_ parameters to use is computed during startup of application by reading the configuration file.

RsyncOSX does also facilitate user selected parameters. User selected parameters are stored by each task.

The parameters in picture are explained below.

![New configurations](screenshots/master/rsync/rsync4.png)


## Standard parameters all tasks

The following parameters are applied to all tasks.

- `--archive`
	- ensures that all files are transferred with all attributes preserved
- `--verbose`
	- make rsync very outspoken, required for counting files in RsyncOSX
- `--delete`
	- delete all files at _destination_ which is not in _source_

## Standard parameters networked tasks only

The following parameters are for _networked_ tasks only. A networked task is a task where destination is on a remote server, eiher on local LAN or on Internet.

- `--compress`
	- compress files before transmitting
- `- e ssh`
	- to ensure rsync tunnels traffic through a ssh-tunnel
- `-e "ssh -p xxxx"`
	- choose another port if standard port 22 is not used
- enable by setting port number in parameters

## Details about the sample parameters

The website LibreByte has written an article [14 Pratical examples of the rsync command](http://www.librebyte.net/en/gnulinux/14-practical-examples-of-the-rsync-command/). One of the examples is instructing rsync to store backups of files in a backup folder and rename old files by a date suffix.

The first parameters (of four parameters) in figure are for excluding some files (the file `exclude-list.txt` is only one line with `*.pdf` which instructs rsync to omit all files with suffix pdf).
The parameters are: 

- `--backup`
- `--backup-dir=../backup`
- <code>--suffix= _\`date +'%Y-%m-%d.%H.%M'`</code>
	- I have experienced some variations regarding the suffix. If you want to use suffix you might try an alternative suffix if the above is not working as expected. If so is true use `--suffix= _$(date +%Y-%m-%d.%H.%M)` instead. You just have to try and see what works

The three last parameters creates a new directory `../backup` relative to the destination directory (`~/Documents/backup`). Any updated documents in source instructs rsync to move the old document in destination to backup folder and add a date + time suffix to the file (`filename_2016-06-14.10.31`) before copying the updated document from source to destination.
