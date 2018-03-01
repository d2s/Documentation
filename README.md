# RsyncOSX

Before installing and using RsyncOSX there are some important information to read and understand. The (1) document is how to get and install RsyncOSX. The (2) document is some information what RsyncOSX is and how to use the application. Please read the (2) document before using RsyncOSX.

 - (1) getting and installing [RsyncOSX](docs/RsyncOSX.md)
 - (2) important [information](docs/HowtoUseRsyncOSX.md) about what RsyncOSX is

Rsync is a file-based synchronization and backup tool. There is no custom solution for the backup archive. You can quit utilizing RsyncOSX (and rsync) at any time and still have access to all synchronized files. Be sure you understand the basics how rsync works before using RsyncOSX (and rsync).

#### Changelog RsyncOSX

Please see the the [Changelog](docs/Changelog.md) for details about releases.

#### A new project RcloneOSX

I have commenced a **new project**, the new project [RcloneOSX](https://github.com/rsyncOSX/rcloneosx) is adapting RsyncOSX to utilize [rclone](https://rclone.org). The new project utilizes `rclone` command utililty for backup of files to cloud services as Dropbox and Micrsoft Onedrive. There is a short [intro](docs/RcloneOSX/Intro/Intro.md) to RcloneOSX. See also the [Changelog](docs/RcloneOSX/Changelog.md) for the project.

### Using RsyncOSX

The following are documents about using RsyncOSX.

- short [intro](docs/Intro.md) to RsyncOSX
- adding [configurations](docs/AddConfigurations.md) (backup and restore)
- executing of [single tasks](docs/SingleTask.md) (configurations)
- executing of [batch tasks](docs/BatchTask.md)
- utilizing the [snapshot feature](docs/Snapshots.md)
- utilizing the [quick backup feature](docs/Quickbackup.md)
- scheduling of [tasks](docs/ScheduleTasks.md)
- restore of [single files or catalogs](docs/CopySingleFiles.md)
- [logging](docs/Logging.md) execution of tasks
- some info about [user configuration](docs/UserConfiguration.md)

### Passwordless logins

Using RsyncOSX for backup to remote servers require to setup ssh passwordless login. What is ssh passwordless login? By using ssh private and public pair of keys enables a more secure method to login to remote servers without password.

- how to use RsyncOSX to assist in setting up [passwordless](docs/ssh.md) logins
- or enable [passwordless logins](docs/PasswordlessLogin.md) manually

### Parameters to rsync

There are a couple of other important information about using RsyncOSX (and rsync):

- parameters to [rsync](docs/Parameters.md)
- some more info about standard [parameters to rsync](docs/RsyncParameters.md)

### Apple App Store

Why is RsyncOSX not on Apple App Store? Well, it has been. The App Store version of RsyncOSX was dropped because of restrictions executing RsyncOSX in [Apples sandbox technology](https://developer.apple.com/library/content/documentation/Security/Conceptual/AppSandboxDesignGuide/AboutAppSandbox/AboutAppSandbox.html). Executing applications in a sandbox environment restricts RsyncOSX (rsync) from using a ssh-tunnel. Ssh is not allowed reading certificates for passwordless logins when rsync is forked from RsyncOSX. There might be a solution for it, but I dont want to spend time investigating how.

## Documentation of source

I have commenced [documentation of source](docs/source/source.md).

## My NAS setup

I have setup up my own [NAS](docs/DIYNAS.md). I am doing backups by using RsyncOSX and sharing out disk by AFP and SMB.

## Rsync

In last release image (RsyncOSX.zip) there is a `rsync-3.1.3.dmg` which includes a built version of latest version of rsync. See the `readme.txt` and make RsyncOSX aware of using the new rsync in [userconfig](https://github.com/rsyncOSX/Documentation/blob/master/docs/UserConfiguration.md).

The default version of `rsync` in macOS is old (version 2.6.9, [protocol](https://rsync.samba.org/how-rsync-works.html) version 29). Version [2.6.9](https://download.samba.org/pub/rsync/src/rsync-2.6.9-NEWS) was released in nov 2006. The current release of rsync is version [3.1.3](https://download.samba.org/pub/rsync/src/rsync-3.1.3-NEWS) protocol 31 released 28 January 2018. There are at least three options to get and install the current version of rsync for use in RsyncOSX:

- use the `rsync-3.1.3.dmg` within `RsyncOSX.zip`to install the latest version of rsync (from version 5.0.0 of RsyncOSX)
- install Xcode and download the rsync [source](https://rsync.samba.org/) from rsync.samba.org
	- required tools are `gcc` and `make` which are part of Xcode command line tool (you might be able to install Xcode command line tool only by downloading the tools from [Apple Developer page](https://developer.apple.com/))
	- untar the source archive and use `make` to compile and install, rsync compiles without any issues on macOS
- install [homebrew](https://en.wikipedia.org/wiki/Homebrew_(package_management_software)) and then install rsync as part of homebrew

In RsyncOSX select [RsyncOSX configuration](https://github.com/rsyncOSX/Documentation/blob/master/docs/UserConfiguration.md) and set path for optional version of rsync.


## YouTube

The YouTube video of RsyncOSX is an old version. There has been several updates to RsyncOSX since then. But the core functionality of RsyncOSX is demonstrated.

I have uploaded a short (about 5 minutes) [YouTube demo of RsyncOSX](https://www.youtube.com/watch?v=ty1r7yvgExo) : "Downloading RsyncOSX, installing, first time configuration and using RsyncOSX for the first time. Backup (as demo) of about 120 MB of data and 4000 files to a VirtualBox FreeBSD machine."

## MacUpdate and Softpedia

RsyncOSX is also released on [MacUpdate](https://www.macupdate.com/app/mac/56516/rsyncosx) and linked for download on [Softpedia](http://mac.softpedia.com/get/Internet-Utilities/RsyncOSX.shtml) as well. The application is downloaded about 10,000 times from MacUpdate and 2650 times from Softpedia (all versions, Oct 2017). RsyncOSX does also inform users about new releases and link to download new version. To be honest, I have **no idea** how many users of RsyncOSX there are. But I am very happy if some users find it useful.

## Other documents

There are a few other documents in context of RsyncOSX. To enable remote storage of backups please read how to [enable passwordless logins](docs/PasswordlessLogin.md). Rsync utilises parameters. RsyncOSX can send extra (set by user) parameters to rsync.

- my [DIY NAS](docs/DIYNAS.md)
- the [idea](docs/Idea.md) behind RsyncOSX
