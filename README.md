# RsyncOSX

Before installing and using RsyncOSX there are some important information to read and understand. The _first_ document is how to get and install RsyncOSX. The _second_ document is some information what RsyncOSX is and how to use the application. Please read the _second_ document before using the application.

> - Getting and installing (#1) [RsyncOSX](docs/RsyncOSX.md).
> - Important (#2) [information](docs/HowtoUseRsyncOSX.md) about what RsyncOSX is.

#### Changelog RsyncOSX

Please see the the [Changelog](docs/Changelog.md) for details about releases.

#### A new project RcloneOSX

I have commenced a **new project**, the new project [RcloneOSX](https://rsyncosx.github.io/rcloneosx/) is adapting RsyncOSX to utilize [rclone](https://rclone.org). The new project utilizes `rclone` command utililty for backup of files to cloud services as Dropbox and Micrsoft Onedrive. There is a short [intro](docs/RcloneOSX/Intro/Intro.md) to RcloneOSX. See also the [Changelog](docs/RcloneOSX/Changelog.md) for the project. 

### Using RsyncOSX

The following are documents about using RsyncOSX.

> - Short [intro](docs/Intro.md) to RsyncOSX
> - Adding [configurations](docs/AddConfigurations.md) (backup and restore).
> - Executing of [single tasks](docs/SingleTask.md) (configurations).
> - Executing of [batch tasks](docs/BatchTask.md).
> - Scheduling of [tasks](docs/ScheduleTasks.md).
> - Restore of [single files or catalogs](docs/CopySingleFiles.md).
> - [Logging](docs/Logging.md) execution of tasks.
> - Some info about [user configuration](docs/UserConfiguration.md).

### Passwordless logins

Using RsyncOSX for backup to remote servers requiere to setup ssh passwordless login. What is ssh passwordless login? By using ssh private and public keypair, login to remote servers without password is enabled.

> - How to enable [passwordless logins](docs/PasswordlessLogin.md).
> - Or use RsyncOSX to assist setting up [passwordless](docs/ssh.md) logins.

### Parameters to rsync

There are a couple of other important information about using RsyncOSX (and rsync):

> - Parameters to [rsync](docs/Parameters.md).
> - Some more info about standard [parameters to rsync](docs/RsyncParameters.md).

### Apple App Store

Why is RsyncOSX not on Apple App Store? Well, it has been. The App Store version of RsyncOSX was dropped because of restrictions executing RsyncOSX in [Apples sandbox technology](https://developer.apple.com/library/content/documentation/Security/Conceptual/AppSandboxDesignGuide/AboutAppSandbox/AboutAppSandbox.html). Executing applications in a sandbox environment restricts RsyncOSX (rsync) from using a ssh-tunnel. Ssh is not allowed reading certificates for passwordless logins when rsync is forked from RsyncOSX. There might be a solution for it, but I dont want to spend time investigating how.

## Documentation of source

I have commenced [documentation of source](docs/source/source.md).

## My NAS setup

I have setup up my own [NAS](docs/DIYNAS.md). I am doing backups by using RsyncOSX and sharing out disk by AFP and SMB.

## Rsync

In last release image (RsyncOSX.dmg) there is a `rsync-3.1.2.dmg` which includes a built version of latest version of rsync. To install this version of rsync please make a catalog on your mac (e.g. `/usr/local/bin`) and make RsyncOSX aware of using the new rsync in [userconfig](https://rsyncosx.github.io/Documentation/docs/UserConfiguration.html). A compiled version of rsync will be included in every coming release of RsyncOSX.

The default version of `rsync` in macOS is old (version 2.6.9, [protocol](https://rsync.samba.org/how-rsync-works.html) version 29). Version [2.6.9](https://download.samba.org/pub/rsync/src/rsync-2.6.9-NEWS) was released in nov 2006. The current release of rsync is version [3.1.2](https://download.samba.org/pub/rsync/src/rsync-3.1.2-NEWS) protocol 31 released 21 Dec 2015. There are at least three options to get and install the current version of rsync for use in RsyncOSX:

- use the `rsync-3.1.2.dmg` within `RsyncOSX.dmg`to install the latest version of rsync
- install Xcode and download the rsync [source](https://rsync.samba.org/) from rsync.samba.org
	- required tools are `gcc` and `make` which are part of Xcode command line tool (you might be able to install Xcode command line tool only by downloading the tools from [Apple Developer page](https://developer.apple.com/))
	- untar the source archive and use `make` to compile and install, rsync compiles without any issues on macOS
- install [homebrew](https://en.wikipedia.org/wiki/Homebrew_(package_management_software)) and then install rsync as part of homebrew

In RsyncOSX select [RsyncOSX configuration](https://github.com/rsyncOSX/Documentation/blob/master/docs/UserConfiguration.md) and set path for optional version of rsync.


## YouTube

I have uploaded a short (about 5 minutes) [YouTube demo of RsyncOSX](https://www.youtube.com/watch?v=ty1r7yvgExo) : "Downloading RsyncOSX, installing, first time configuration and using RsyncOSX for the first time. Backup (as demo) of about 120 MB of data and 4000 files to a VirtualBox FreeBSD machine."

## MacUpdate and Softpedia

RsyncOSX is also released on [MacUpdate](https://www.macupdate.com/app/mac/56516/rsyncosx) and linked for download on [Softpedia](http://mac.softpedia.com/get/Internet-Utilities/RsyncOSX.shtml) as well. The application is downloaded about 10,000 times from MacUpdate and 2650 times from Softpedia (all versions, Oct 2017). RsyncOSX does also inform users about new releases and link to download new version. To be honest, I have **no idea** how many users of RsyncOSX there are. But I am very happy if some users find it useful.

## Other documents

There are a few other documents in context of RsyncOSX. To enable remote storage of backups please read how to [enable passwordless logins](docs/PasswordlessLogin.md). Rsync utilises parameters. RsyncOSX can send extra (set by user) parameters to rsync.


> - My [DIY NAS](docs/DIYNAS.md).
> - The [idea](docs/Idea.md) behind RsyncOSX.
