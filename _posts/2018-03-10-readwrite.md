---
layout: post
title:  "Reading and writing data to permanent storage"
permalink: readwrite
---
The object [ReadWriteDictionary.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ReadWriteDictionary.swift) reads and writes to permanent storage. All data (configurations, schedules and log records, user config) is read from permanent storage utilizing the [NSDictionary](https://developer.apple.com/documentation/foundation/nsdictionary) foundation class.

RsyncOSX configuration file, scheduled tasks which also includes log records and user configuration are plain XML-files ([property list files](https://en.wikipedia.org/wiki/Property_list)). Files are saved in:

configurations
```
~/Documents/Rsync/MacID/configRsync.plist
```
- ~/ is user home directory
- MacID is the Mac serial number and is automatically set by RsyncOSX

log records and scheduled tasks
```
~/Documents/Rsync/MacID/scheduleRsync.plist
```
user config
```
~/Documents/Rsync/MacID/config.plist
```

If profile is used:

configurations
```
~/Documents/Rsync/MacID/profile/configRsync.plist
```
log records and scheduled tasks
```
~/Documents/Rsync/MacID/profile/scheduleRsync.plist
```
