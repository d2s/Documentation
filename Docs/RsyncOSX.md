
## RsyncOSX

RsyncOSX is a GUI for the rsync command-line tool. The main uses are:

- backup (and restore) local files on Mac to remote servers connected to Internet or local network
	- the above is why I wrote RsyncOSX to use myself
- backup (and restore) local files on Mac to local storage (attached disks)
	- if this is <i>the only use</i> there might be <i>other tools</i> more useful than RsyncOSX

## Download link and install

RsyncOSX is released in version 3.5.5 (updated 10 November 2016).

- [download](https://dl.dropboxusercontent.com/u/52503631/RsyncOSX.dmg) latest version of RsyncOSX
- shasum :129c82b81cf6c7a601ff26988a25969bd8dccaaf
- see the [Changelog](https://github.com/rsyncOSX/Documentation/blob/master/Docs/Changelog.md) for info

<code>/usr/bin/shasum ~/PathToDownload/RsyncOSX.dmg</code> to verify hash

To install the application copy it to Desktop or any other folder in your home catalog. The application is installed and used at your own risk and developer accepts no responsibility for any errors, omissions or loss of data by using the application.

The application is signed with my Apple Developer ID certificate.

## Password-less logins

Backup to remote servers require ssh password-less logins (by ssh-keygen and ssh public and private key). Here is how to [setup password-less](https://github.com/rsyncOSX/Documentation/blob/master/Docs/PasswordlessLogin.md) logins.

## Idea behind RsyncOSX

I have two Macbooks, one is used primarily at work and the other is my private. Data is backed up to server at home and to one offsite servers. Both Macbooks and all backup locations are kept in sync. I am using my private Macbook for Pictures (I have about 100 GB of raw picture files). Whenever I have added new picture files or done some work on pictures, changes are backup up on all servers and then restored on my Macbook used at work.

Some more details about the [idea](https://github.com/rsyncOSX/Documentation/blob/master/Docs/Idea.md) for RsyncOSX.