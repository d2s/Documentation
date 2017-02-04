# RsyncOSX

The following are documents about RsyncOSX. The _first_ document is how to get and install RsyncOSX. The _second_ document is some information what RsyncOSX is and how to use the application. Please read the _second_ document before using the application.

- Getting and installing (#1) [RsyncOSX](https://github.com/rsyncOSX/Documentation/blob/master/docs/RsyncOSX.md).
- Important (#2) [information](https://github.com/rsyncOSX/Documentation/blob/master/docs/HowtoUseRsyncOSX.md) about what RsyncOSX is.
- Information about using RsyncOSX
  - Adding [configurations](https://github.com/rsyncOSX/Documentation/blob/master/docs/AddConfigurations.md) (backup and restore).
  - Executing of [single tasks](https://github.com/rsyncOSX/Documentation/blob/master/docs/SingleTask.md) (configurations).
  - Executing of [batch tasks](https://github.com/rsyncOSX/Documentation/blob/master/docs/BatchTask.md).
  - Scheduling of [tasks](https://github.com/rsyncOSX/Documentation/blob/master/docs/ScheduleTasks.md).
  - Restore of [single files or catalogs](https://github.com/rsyncOSX/Documentation/blob/master/docs/CopySingleFiles.md).
  - [Logging](https://github.com/rsyncOSX/Documentation/blob/master/docs/Logging.md) execution of tasks.
  - Some info about [user configuration](https://github.com/rsyncOSX/Documentation/blob/master/docs/UserConfiguration.md).

### Other important information

There are a couple of other important information about using RsyncOSX (and rsync)

- How to enable [passwordless logins](https://github.com/rsyncOSX/Documentation/blob/master/docs/PasswordlessLogin.md) (required for using RsyncOSX with remote servers).
- Parameters to [rsync](https://github.com/rsyncOSX/Documentation/blob/master/docs/Parameters.md).
- Some more info about standard [parameters to rsync](https://github.com/rsyncOSX/Documentation/blob/master/docs/RsyncParameters.md).

## Changelog

The RsyncOSX [changelog](https://github.com/rsyncOSX/Documentation/blob/master/docs/Changelog.md).

## Issues

Any issues about RsyncOSX is listed [here](https://github.com/rsyncOSX/Version3.x/issues).

## Rsync

The default version of `rsync` in macOS is old (version 2.6.9, protocol version 29). Version [2.6.9](https://download.samba.org/pub/rsync/src/rsync-2.6.9-NEWS) was released in nov 2006. The current release of rsync is version [3.1.2](https://download.samba.org/pub/rsync/src/rsync-3.1.2-NEWS) protocol 31, released 21 Dec 2015. There are at least two options to get and install the current version of rsync for use in RsyncOSX:

- install Xcode and download the rsync [source](https://rsync.samba.org/) from rsync.samba.org
	- untar the source archive and use `make` to compile and install, rsync compiles without any issues on macOS
- install [homebrew](https://en.wikipedia.org/wiki/Homebrew_(package_management_software)) and then install rsync as part of homebrew

In RsyncOSX select [RsyncOSX configuration](https://github.com/rsyncOSX/Documentation/blob/master/docs/UserConfiguration.md) and set path for optional version of rsync.


## YouTube

I have uploaded a short (about 5 minutes) [YouTube demo of RsyncOSX](https://www.youtube.com/watch?v=ty1r7yvgExo) : "Downloading RsyncOSX, installing, first time configuration and using RsyncOSX for the first time. Backup (as demo) of about 120 MB of data and 4000 files to a VirtualBox FreeBSD machine."

## Other documents

There are a few other documents in context of RsyncOSX. To enable remote storage of backups please read how to [enable passwordless logins](https://github.com/rsyncOSX/Documentation/blob/master/docs/PasswordlessLogin.md). Rsync utilises parameters. RsyncOSX can send extra (set by user) parameters to rsync.


- My [DIY NAS](https://github.com/rsyncOSX/Documentation/blob/master/docs/DIYNAS.md).
- The [idea](https://github.com/rsyncOSX/Documentation/blob/master/docs/Idea.md) behind RsyncOSX.
