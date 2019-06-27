---
layout: post
title:  "RsyncGUI Changelog"
permalink: RsyncGUIChangelog
---
RsyncGUI is compiled with support for macOS El Capitan version 10.11 - macOS Mojave version 10.14. The application is implemented in Swift 5 by using Xcode 10.

Rsync is a file-based synchronization and backup tool. There is no custom solution for the backup archive. You can quit utilizing RsyncGUI (and rsync) at any time and still have access to all synchronized files.

The [App Sandboxing technology](https://developer.apple.com/app-sandboxing/) is a technology for protecting the user for malicious software. To release a macOS app on Apple Mac App Store require the app to execute inside a sandbox. RsyncGUI is an adapted version of [RsyncOSX](https://github.com/rsyncOSX/RsyncOSX) to execute inside a sandbox. There are a few limitations compared to RsyncOSX.

## Limitations

The default version of `rsync` in macOS is old (version 2.6.9, [protocol](https://rsync.samba.org/how-rsync-works.html) version 29). Version [2.6.9](https://download.samba.org/pub/rsync/src/rsync-2.6.9-NEWS) was released in nov 2006. The current release of rsync is version [3.1.3](https://download.samba.org/pub/rsync/src/rsync-3.1.3-NEWS) protocol 31 released 28 January 2018.

Utilizing **snapshots** in RsyncGUI is **not possible** due to bugs in default version version 2.6.9 of rsync in macOS. It is not allowed due to the sandbox to execute an updated and another version of rsync in e.g `/usr/local/bin`.

Utilizing **scheduled** task is not implemented in RsyncGUI.

If you need either of them please use [RsyncOSX](https://github.com/rsyncOSX/RsyncOSX).

## Version 1.5.0

This version is approved for release on Apple Mac Store 27 June 2019.

- fixed some memory leaks
- this is primary a maintenance release, fixed some bugs and cleanup in code

## Version 1.1.0

This version is approved for release on Apple Mac Store 4 April 2019.

![](/images/RsyncOSX/master/nextversion/nextversion.png)

- quit RsyncGUI by red button upper left main window
- RsyncGUI center itself in screen when started
- view all profiles and configurations by menu button (moved from tab view)
- backup now and automatic backup my be executed from any view (tab) by menu buttons or shortcuts
- clean up of code and some bugfixes
- configuration is available by shortcut `⌘,` (Preferences)
- built by last release of Xcode 10.2
- removed code for snapshots (due to stock version of rsync in macOS)

## Version 1.0.1

Version 1.0.1 is released 4 February 2019. Some minor bugfixes after initial release.

## Version 1.0.0

The app is [released](https://itunes.apple.com/us/app/rsyncgui/id1449707783?l=nb&ls=1&mt=12) on Apple Mac App Store 24 January 2019.
