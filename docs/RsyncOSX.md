
## Install RsyncOSX

Index of [RsyncOSX documentation](https://rsyncosx.github.io/Documentation/).

See important info about how to use [RsyncOSX and rsync](HowtoUseRsyncOSX.md). There is also a short [intro](Intro.md) to RsyncOSX.

## Download link and install

RsyncOSX is released in version 5.1.1 (27 February 2018). There are two methods for install, either (1) copy the apps from dmg files into a selected folder or use the (2) installer files to install in `/Application`folder.

- (1) [download zip archive](https://github.com/rsyncOSX/RsyncOSX/releases/download/v5.1.1/RsyncOSX.zip)
	- unzip `RsyncOSX.zip` , open the two dmg´s and copy the `RsyncOSX.app` and `RsyncOSXsched.app` to a local directory
	- shasum zip archive: 1ae9b3bbd3fdc01c77b63f407ac77415f6171991
	- `/usr/bin/shasum ~/PathToDownload/RsyncOSX.zip` to verify hash
- (2) [download zip pkg archive](https://github.com/rsyncOSX/RsyncOSX/releases/download/v5.1.1/RsyncOSXpkg.zip)
	- unzip `RsyncOSXpkg.zip` and start installer for both apps, the installer copy the apps to the `/Application` folder
	- shasum zip pkg archive: dd803eac298fb479a6cbbef5addc4af469c91cc6
	- `/usr/bin/shasum ~/PathToDownload/RsyncOSXpkg.zip` to verify hash
- see the [Changelog](Changelog.md) for info

The application is installed and used at your own risk and developer accepts no responsibility for any errors, omissions or loss of data by using the application. The application is signed with my Apple Developer ID certificate.

## Passwordless logins and remote servers

Backup to *remote servers* require *ssh passwordless* logins by utilizing ssh-keygen to create a ssh private and public key pair. RsyncOSX can assist in setting up [passwordless](ssh.md) logins or use the instructions in [setup passwordless logins](PasswordlessLogin.md).

## YouTube video

The YouTube video of RsyncOSX is an old version. There has been several updates to RsyncOSX since then. But the core functionality of RsyncOSX is demonstrated.

I have uploaded a short (about 5 minutes) [YouTube demo of RsyncOSX](https://www.youtube.com/watch?v=ty1r7yvgExo) : "Downloading RsyncOSX, installing, first time configuration and using RsyncOSX for the first time. Backup (as demo) of about 120 MB of data and 4000 files to a VirtualBox FreeBSD machine."

## Idea behind RsyncOSX

I have two MacBooks, one is used primarily at work and the other is my private. Data is backed up to server (NAS) at home and to one offsite servers. Both MacBooks and all backup locations are kept in sync. I am using my private MacBook for Pictures (I have about 100 GB of raw picture files). Whenever I have added new picture files or done some work on pictures, changes are backup up on all servers and then restored on my MacBook used at work. The rsync command-line tool is one of the best tools around for backup and synchronizing storage. A GUI on top of rsync might hide all the details about parameters to rsync and make rsync execute the correct actions.

Some more details about the [idea](Idea.md) for RsyncOSX.
