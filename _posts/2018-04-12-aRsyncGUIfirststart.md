---
layout: post
title:  "First time start aRsyncGUI"
permalink: aRsyncGUIfirststart
---
This page is a short guide what to do when first start of aRsyncGUI. For more details about the various functions of aRsyncGUI please see the [documentation](/AboutaRsyncGUI) (RsyncOSX) about each function. Also be sure you understand  [the basics](/HowtoUseaRsyncGUI) (RsyncOSX) about how rsync works before using aRsyncGUI and rsync.

This guide is primary for executing synchronizing tasks to remote servers. This version does not yet support snapshot tasks. If you want to utilize [snapshot tasks](/Snapshots) please use RsyncOSX instead.

### Firs steps setting up passwordless logins for rsync

See [manual setup of passwordless logins](/PasswordlessLogin) for info. Setting up passwordless logins is not required if this works before using aRsyncGUI. It is required that ssh certificates is utilizing the `.ssh` catalog in the users root catalog.

### Create private and public ssh certificates

If you plan utilizing aRsyncGUI with remote servers it is required to setup passwordless logins. Ssh saves by default, private ssh-keys in `.ssh` catalog on root. You need to assist aRsyncGUI a little bit. Open a terminal and `cd` to root and `mkdir .ssh` to create the catalog.

![](/images/RsyncOSX/master/aRsyncGUIfirststart/main0.png)

If you don´t do the above creating the ssh keypair by utiling the ssh assistent in aRsyncGUI will not work.

![](/images/RsyncOSX/master/aRsyncGUIfirststart/main1.png)

After creating the `.ssh` catalog (before starting aRsyncGUI) the app asks for permission to access the root catalog. Before choosing `Allow` select the root catalog.

![](/images/RsyncOSX/master/aRsyncGUIfirststart/main2.png)

Select the `Ssh` tab and create both keys.

![](/images/RsyncOSX/master/aRsyncGUIfirststart/main3.png)
![](/images/RsyncOSX/master/aRsyncGUIfirststart/main4.png)

### Adding a synchronizing task

Then it is time to add a synchronizing task with a remote destination.

![](/images/RsyncOSX/master/aRsyncGUIfirststart/main5.png)

### Transferring public ssh certificates

After the synchronizing task is entered go back to the `Ssh` tab and let aRsyncGUI assist you in transferring the public ssh-keys to the remote server.

![](/images/RsyncOSX/master/aRsyncGUIfirststart/main6.png)

Select the `Remote` button and choose the correct remote server. Choose `Terminal.app` to open a terminal and copy and paste the three lines in that order into the terminal.

The last action to do is select the `Check rsa` and `Check dsa` to verify and set correct permissions on the remote `.ssh` catalog and public ssh-keys.

![](/images/RsyncOSX/master/aRsyncGUIfirststart/main7.png)
![](/images/RsyncOSX/master/aRsyncGUIfirststart/main8.png)
![](/images/RsyncOSX/master/aRsyncGUIfirststart/main9.png)

### Ready for first synchronizing tasks

Now you can do your first synchronizing task.

![](/images/RsyncOSX/master/aRsyncGUIfirststart/main10.png)
