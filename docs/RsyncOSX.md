
## Install RsyncOSX

Index of [RsyncOSX documentation](https://rsyncosx.github.io/Documentation/).

RsyncOSX is a GUI for the rsync command-line tool. The main use are:

- backup (and restore) local files on your Mac to remote servers connected to Internet or local network
- backup (and restore) local files on Mac to local storage (attached disks)

Be sure you understand the basics how rsync works before using RsyncOSX (and rsync).
```
Warning: default parameters for rsync is to synchronize the source and destination.
A "restore" will delete all files in the source which are not in the destination.
The main objective to RsyncOSX is to keep source directory and destination (backup)
directory synchronized. When a source directory is backed up, the destination is 100%
synchronized with the source in the moment the backup task is completed. There are
no revisions of files in the backup in default RsyncOSX. Old files in the backup are
either replaced with new ones or deleted if so is true in source.
```
- _source_: the local volume to be copied
- _destination_: the remote location where source files and catalogs are copied

What about **revisions and deleted** files? Either use the [snapshot feature](Snapshots.md) or by [backup parameters](Parameters.md) to rsync.

## YouTube video

The YouTube video of RsyncOSX is an old version. There has been several updates to RsyncOSX since then. But the core functionality of RsyncOSX is demonstrated.

I have uploaded a short (about 5 minutes) [YouTube demo of RsyncOSX](https://www.youtube.com/watch?v=ty1r7yvgExo) : "Downloading RsyncOSX, installing, first time configuration and using RsyncOSX for the first time. Backup (as demo) of about 120 MB of data and 4000 files to a VirtualBox FreeBSD machine."

## Download link and install

RsyncOSX is released in version 5.1.1 (27 February 2018). There are two methods for install, either copy the apps from dmg files into a selected folder or use the installer files to install in `/Application`folder.

- [download zip archive](https://github.com/rsyncOSX/RsyncOSX/releases/download/v5.1.1/RsyncOSX.zip)
	- unzip `RsyncOSX.zip` , open the two dmg´s and copy the `RsyncOSX.app` and `RsyncOSXsched.app` to a local directory
	- shasum zip archive: 1ae9b3bbd3fdc01c77b63f407ac77415f6171991
	- `/usr/bin/shasum ~/PathToDownload/RsyncOSX.zip` to verify hash
- [download zip pkg archive](https://github.com/rsyncOSX/RsyncOSX/releases/download/v5.1.1/RsyncOSXpkg.zip)
	- unzip `RsyncOSXpkg.zip` and start installer for both apps, the installer copy the apps to the `/Application` folder
	- shasum zip pkg archive: dd803eac298fb479a6cbbef5addc4af469c91cc6
	- `/usr/bin/shasum ~/PathToDownload/RsyncOSXpkg.zip` to verify hash
- see the [Changelog](Changelog.md) for info

The application is installed and used at your own risk and developer accepts no responsibility for any errors, omissions or loss of data by using the application. The application is signed with my Apple Developer ID certificate.

## Passwordless logins and remote servers

Backup to *remote servers* require *ssh passwordless* logins by utilizing ssh-keygen to create a ssh private and public key pair. RsyncOSX can assist in setting up [passwordless](ssh.md) logins or use the instructions in [setup passwordless logins](PasswordlessLogin.md).

## Idea behind RsyncOSX

I have two MacBooks, one is used primarily at work and the other is my private. Data is backed up to server (NAS) at home and to one offsite servers. Both MacBooks and all backup locations are kept in sync. I am using my private MacBook for Pictures (I have about 100 GB of raw picture files). Whenever I have added new picture files or done some work on pictures, changes are backup up on all servers and then restored on my MacBook used at work. The rsync command-line tool is one of the best tools around for backup and synchronizing storage. A GUI on top of rsync might hide all the details about parameters to rsync and make rsync execute the correct actions.

Some more details about the [idea](Idea.md) for RsyncOSX.
