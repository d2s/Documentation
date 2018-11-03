---
layout: post
title:  "Signing and notarize the apps"
permalink: Notarized
---
Both RsyncOSX and RcloneOSX are signed and [notarized](https://support.apple.com/en-us/HT202491) by Apple. Both apps are verified and checked for not containing malicious code and it ensures that the apps are working together with Apples Gatekeeper technology.

## RsyncOSX

The app is signed with my Apple ID developer certificate and [notarized](https://support.apple.com/en-us/HT202491) by Apple. If you have Xcode developer tools installed executing the following command will verify the the RsyncOSX.app.
```
xcrun stapler validate no.blogspot.RsyncOSX RsyncOSX.app
Processing: /Volumes/Home/thomas/GitHub/RsyncOSX/Build/Products/Release/RsyncOSX.app
The validate action worked!
```
This is the message when opening a downloaded version (from version > 5.5.5).

![](/images/RsyncOSX/master/notarize/verifyRsyncOSX.png)

The message is in Norwegian: "Apple har sjekket programmet uten å finne ondsinnet programvare."  

The english version of it is: "Apple checked it for malicious software and none was detected."

## RcloneOSX

The app is signed with my Apple ID developer certificate and [notarized](https://support.apple.com/en-us/HT202491) by Apple. If you have Xcode developer tools installed executing the following command will verify the the rcloneosx.app.
```
xcrun stapler validate no.blogspot.rcloneosx rcloneosx.app
Processing: /Volumes/Home/thomas/GitHub/RcloneOSX/Build/Products/Release/rcloneosx.app
The validate action worked!
```
This is the message when opening a downloaded version (from version 1.6.7).

![](/images/RsyncOSX/master/notarize/verifyRcloneOSX.png)

The message is in Norwegian: "Apple har sjekket programmet uten å finne ondsinnet programvare."  

The english version of it is: "Apple checked it for malicious software and none was detected."
