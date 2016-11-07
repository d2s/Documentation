
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
Please read the "<a href="https://github.com/rsyncOSX/Documentation/blob/master/HowtoUseRsyncOSX.md" target="_blank">How to use RsyncOSX</a>" for RsyncOSX and important information about using RsyncOSX. Rsync is a very powerful tool. If not used properly, files and directories might be deleted.

<h3>Download link and install</h3>

RsyncOSX is released in version 3.5.5.
<ul>
<li><a href="https://dl.dropboxusercontent.com/u/52503631/RsyncOSX.dmg" target="_blank">download</a> latest version of RsyncOSX</li>
<ul>
<li>shasum :58b85d69c62592f0f91f1995904b3ed9ae9e6464</li>
<li>see <a href="https://github.com/rsyncOSX/Documentation/blob/master/Changelog.md" target="_blank">revision history</a> for comments</li>
</ul>
<li><code>/usr/bin/shasum ~/PathToDownload/RsyncOSX.dmg</code> to verify hash</li>
<ul>
</ul>
</ul>
To install the application copy it to Desktop or any other folder in your home catalog. The application is installed and used at your own risk and developer accepts no responsibility for any errors, omissions or loss of data by using the application.
<br />
The application is signed with my Apple Developer ID certificate.<br />

<h3>Set up password-less logins</h3>

Backup to remote servers require ssh password-less logins (by ssh-keygen and ssh public and private key). RsyncOSX uses configuration files specific for each Mac desktop.

Here is how to <a href="https://github.com/rsyncOSX/Documentation/blob/master/PasswordlessLogin.md" target="_blank">setup</a> password-less logins.

<h3>My DIY NAS of 2016</h3>
This is my <a href="https://github.com/rsyncOSX/Documentation/blob/master/DIYNAS.md" target="_blank">DIY NAS built in 2016</a>.

<h3>Idea behind RsyncOSX</h3>
I have two Macbooks, one is used primarily at work and the other is my private. Data is backed up to server at home and to one offsite servers. Both Macbooks and all backup locations are kept in sync. I am using my private Macbook for Pictures (I have about 100 GB of raw picture files). Whenever I have added new picture files or done some work on pictures, changes are backup up on all servers and then restored on my Macbook used at work.

Some more details about the <a href="https://github.com/rsyncOSX/Documentation/blob/master/Idea.md" target="_blank">idea</a> for RsyncOSX.