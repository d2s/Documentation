---
layout: post
title:  "aRsyncGUI Changelog"
permalink: aRsyncGUIChangelog
---
aRsyncGUI is compiled with support for macOS Sierra version 10.12 - macOS Mojave version 10.14. The application is implemented in Swift 4 by using Xcode 10.

Rsync is a file-based synchronization and backup tool. There is no custom solution for the backup archive. You can quit utilizing aRsyncGUI (and rsync) at any time and still have access to all synchronized files.

### Apple App Sandboxing technology

Apple has the [App Sandboxing technology](https://developer.apple.com/app-sandboxing/) for protecting the user for malicious software. To release a macOS app on Apple Mac App Store require the app to execute inside a sandbox. This repository is a fork of RsyncOSX to enable aRsyncGUI to execute inside a sandbox and to be released on the Mac App Store.

The name of the app is due to Apple naming conventions for apps released on the Mac App Store.

The app is working but there are still work to do regarding how the user to enable access of files outside the sandbox. Much of the work is based upon this [Sandbox code](https://github.com/regexident/Sandbox). The user has to allow the app to read all catalogs and if remote servers is utilized rsync must be allowed to read the private ssh certificates.

## Version 2.0.0

Released for distribution on Mac App Store 14 January 2019.

aRsyncGUI is a sandboxed version of RsyncOSX. There are a few limitations compared to RsyncOSX. Due to limitations within the Sandbox technology executing third party command line utilities is not allowed.

The default version of `rsync` in macOS is old (version 2.6.9, [protocol](https://rsync.samba.org/how-rsync-works.html) version 29). Version [2.6.9](https://download.samba.org/pub/rsync/src/rsync-2.6.9-NEWS) was released in nov 2006. The current release of rsync is version [3.1.3](https://download.samba.org/pub/rsync/src/rsync-3.1.3-NEWS) protocol 31 released 28 January 2018.

Utilizing **snapshots** in aRsyncGUI is for the moment **not possible** due to bugs in default version of rsync version 2.6.9. It is not allowed due to the sandbox to execute an updated version of rsync in e.g /usr/local/bin.
