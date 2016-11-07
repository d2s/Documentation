
<h3>RsyncOSX</h3>
RsyncOSX is a GUI for the rsync command-line tool. The main uses are:

<ul>
<li>backup (and restore) local files on Mac to remote servers connected to Internet or local network</li>
<ul>
<li>the above is why I wrote RsyncOSX to use myself</li>
</ul>
<li>backup (and restore) local files on Mac to local storage (attached disks)</li>
<ul>
<li>if this is <i>the only use</i> there might be <i>other tools</i> more useful than RsyncOSX</li>
</ul>
</ul>

<h3>How to use RsyncOSX and important notes</h3>
Please read the "<a href="https://rsyncosx.blogspot.no/2016/08/how-to-use-rsyncosx.html" target="_blank">How to use RsyncOSX</a>" for RsyncOSX and important information about using RsyncOSX. Rsync is a very powerful tool. If not used properly, files and directories might be deleted.

<h3>Download link and install</h3>

RsyncOSX is released in version 3.5.5.
<ul>
<li><a href="https://dl.dropboxusercontent.com/u/52503631/RsyncOSX.dmg" target="_blank">download</a> latest version of RsyncOSX</li>
<ul>
<li>shasum :
<style type="text/css">
p.p1 {margin: 0.0px 0.0px 0.0px 0.0px; font: 11.0px Menlo; color: #000000; background-color: #ffffff}
span.s1 {font-variant-ligatures: no-common-ligatures}
</style>&nbsp; &nbsp;58b85d69c62592f0f91f1995904b3ed9ae9e6464</li>
<li>see <a href="https://rsyncosx.blogspot.no/2016/03/revision-history.html" target="_blank">revision history</a>&nbsp;for comments</li>
</ul>
<li><code>/usr/bin/shasum ~/path_to_download/RsyncOSX.dmg</code> to verify hash</li>
<li><a href="https://github.com/rsyncOSX/Version3.x" target="_blank">source code</a> is released on github</li>
<ul>
</ul>
</ul>
To install the application copy it to Desktop or any other folder in your home catalog. The application is installed and used at your own risk and developer accepts no responsibility for any errors, omissions or loss of data by using the application.
<br />
The application is signed with my Apple Developer ID certificate.<br />

<h3>Set up password-less logins</h3>

Backup to remote servers require ssh password-less logins (by ssh-keygen and ssh public and private key). RsyncOSX uses configuration files specific for each Mac desktop.

Here is how to <a href="http://rsyncosx.blogspot.no/2016/03/remote-servers-ssh-and-passwordless.html" target="_blank">setup</a>&nbsp;password-less logins.<br />

<h3>My DIY NAS of 2016</h3>
This is my <a href="https://rsyncosx.blogspot.no/2016/07/diy-nas.html" target="_blank">DIY NAS built in 2016</a>.<br />

<h3>
Idea behind RsyncOSX</h3>
I have two Macbooks, one is used primarily at work and the other is my private. Data is backed up to server at home and to one offsite servers. Both Macbooks and all backup locations are kept in sync. I am using my private Macbook for Pictures (I have about 100 GB of raw picture files). Whenever I have added new picture files or done some work on pictures, changes are backup up on all servers and then restored on my Macbook used at work.

Some more details about the&nbsp;<a href="http://rsyncosx.blogspot.no/2016/03/idea-behind-rsyncosx.html" target="_blank">idea</a>&nbsp;for RsyncOSX.</div>