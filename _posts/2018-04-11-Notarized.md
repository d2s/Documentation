---
layout: post
title:  "Signing and notarize the apps"
permalink: Notarized
---
 RsyncOSX and RcloneOSX are signed with my Apple ID developer certificate and [notarized](https://support.apple.com/en-us/HT202491) by Apple. This means both apps are verified and checked for not containing malicious code. It ensures the users that the apps are clean and that they are working together with Apples Gatekeeper technology. A message from Apple is issued when opening either a new or updated application the first time.

## RsyncOSX

This is the message when opening a downloaded version.

![](/images/RsyncOSX/master/notarize/verifyRsyncOSX.png)

The message is in Norwegian: "Apple har sjekket programmet uten å finne ondsinnet programvare."  The english version of it is: "Apple checked it for malicious software and none was detected."

If you have Xcode developer tools installed executing the following command `xcrun stapler validate no.blogspot.RsyncOSX RsyncOSX.app` will verify RsyncOSX.
```
xcrun stapler validate no.blogspot.RsyncOSX RsyncOSX.app
Processing: /Volumes/Home/thomas/GitHub/RsyncOSX/Build/Products/Release/RsyncOSX.app
The validate action worked!
```

## RcloneOSX

This is the message when opening a downloaded version.

![](/images/RsyncOSX/master/notarize/verifyRcloneOSX.png)

The message is in Norwegian: "Apple har sjekket programmet uten å finne ondsinnet programvare."  The english version of it is: "Apple checked it for malicious software and none was detected."

If you have Xcode developer tools installed executing the following command `xcrun stapler validate no.blogspot.rcloneosx rcloneosx.app` will verify the the rcloneosx.app.
```
xcrun stapler validate no.blogspot.rcloneosx rcloneosx.app
Processing: /Volumes/Home/thomas/GitHub/RcloneOSX/Build/Products/Release/rcloneosx.app
The validate action worked!
```
