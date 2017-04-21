## Rsync standard parameters

Index of [RsyncOSX documentation](https://rsyncosx.github.io/Documentation/).
 
RsyncOSX implements standard parameters which are working fine for simple backup and restore tasks. The actual parameters used in tasks is depended upon executing rsync over _network connection_ or not. Which _standard_ parameters to use is computed during startup of application by reading the configuration file.

RsyncOSX does also facilitate user selected parameters. User selected parameters are stored by each task and set by user, see [user selected parameters](Parameters.md).

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


