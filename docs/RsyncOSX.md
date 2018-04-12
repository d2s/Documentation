
## Install RsyncOSX

Index of [RsyncOSX documentation](https://rsyncosx.github.io/Documentation/).

See important info about how to use [RsyncOSX and rsync](HowtoUseRsyncOSX.md). There is also a short [intro](Intro.md) to RsyncOSX.

## Download link and install

RsyncOSX is released in version 5.2.1 (28 March 2018). There are two methods for install, either (1) copy the apps from dmg files into a selected folder or use the (2) installer files to install in `/Application`folder. There are four archives, two pkg archives to install in /Application and two dmg files. The pkg files are not signed. It is NOT required to install the RsyncOSXsched.app. RsyncOSXsched.app is for scheduled backups only.

See [releases](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v5.2.1) for downloads.

#### Install RsyncOSX.dmg or  RsyncOSX-5.2.1.pkg

- shasum dmg archive: 0278210fc2b748ce503b953f3bb34190b219d321
- shasum pkg pkg archive: 0affdcf06f6a680c96e52fb293b39c32c35170fd

To install RsyncOSX open the downloaded `RsyncOSX.dmg` file, copy the RsyncOSX.app to a folder in your home catalog or any other catalog. The installer, `RsyncOSX-5.2.1.pkg`, copy the application files in the /Application folder. The installer require admin rights to install in /Application folder.

#### Install RsyncOSXsched.dmg or RsyncOSXsched-5.2.1.pkg

- shasum dmg archive: 97b9017c2f7b9ef0d24ca15a08a85a7b7590f84f
- shasum pkg pkg archive: e6567fdbfc25c50437b32f056a50de9fe8828e91

As above.

#### Version 3.1.3 of rsync

See readme.txt within dmg file for how to manually install version rsync 3.1.3.

The application is installed and used at your own risk and developer accepts no responsibility for any errors, omissions or loss of data by using the application. The application is signed with my Apple Developer ID certificate.

## Passwordless logins and remote servers

Backup to *remote servers* require *ssh passwordless* logins by utilizing ssh-keygen to create a ssh private and public key pair. RsyncOSX can assist in setting up [passwordless](ssh.md) logins or use the instructions in [setup passwordless logins](PasswordlessLogin.md).

## YouTube video

The YouTube video of RsyncOSX is an old version. There has been several updates to RsyncOSX since then. But the core functionality of RsyncOSX is demonstrated.

I have uploaded a short (about 5 minutes) [YouTube demo of RsyncOSX](https://www.youtube.com/watch?v=ty1r7yvgExo) : "Downloading RsyncOSX, installing, first time configuration and using RsyncOSX for the first time. Backup (as demo) of about 120 MB of data and 4000 files to a VirtualBox FreeBSD machine."

## Idea behind RsyncOSX

I have two MacBooks, one is used primarily at work and the other is my private. Data is backed up to server (NAS) at home and to one offsite servers. Both MacBooks and all backup locations are kept in sync. I am using my private MacBook for Pictures (I have about 100 GB of raw picture files). Whenever I have added new picture files or done some work on pictures, changes are backup up on all servers and then restored on my MacBook used at work. The rsync command-line tool is one of the best tools around for backup and synchronizing storage. A GUI on top of rsync might hide all the details about parameters to rsync and make rsync execute the correct actions.

Some more details about the [idea](Idea.md) for RsyncOSX.
