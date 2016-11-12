<h2>Idea behind RsyncOSX</h2> 
 
First of all I needed a project as a start for learning Swift and Xcode.

In some years I have used the <a href="https://en.wikipedia.org/wiki/Rsync" target="_blank">rsync</a> tool (included in every<a href="https://en.wikipedia.org/wiki/OS_X" target="_blank"> OS X</a> version, Linux distribution,<a href="https://en.wikipedia.org/wiki/Solaris_(operating_system)" target="_blank"> Solaris</a> and other Unix based operating systems) for backing up Documents and Pictures catalogs on my MacBooks. I have used rsync by copy and pasting the rsync command with required parameters in a terminal window to backup and restore data. It is easy to do mistakes. Forget an "/" character and rsync does not execute as expected. And change the order of parameter it is easy to do a restore and not a backup. And I have done it some times...

The rsync command-line tool is very effective and robust tool. Rsync is also available in any Linux, Unix, Solaris and Mac OSX OS. Rsync is developed to minimize network bandwith and can be tunneled through ssh for secure transport.


That said, I am also using Apples iCloud, but that is most for sharing files between my two MacBooks, iPad and iPhone. Rsync is used for backup my Documents catalog (about 1 GB of data) and Pictures catalog (about 94 GB of data - mostly raw picture files from last 10 years.

As mentioned rsync is available on most server operating systems. Tools like Apple Time Machine require Apple Airport (and maybe Apple Filing Transport protocol AFP) and is a proprietary backup solution. I am using two MacBooks and stores backups on two remote servers. Both MacBooks and servers are synchronized. When I have updated or created a new files on one MacBook, I have to update my two remote backup servers. After that update my second MacBook. If one remote server fails or I am doing something wrong most likely one remote server is always updated.

The challenge is to keep my two MacBooks and two backup locations updated and in sync. RsyncOSX does not automate the above, but it supports me doing it. And now I am able to either backup or restore by just a couple of mouse clicks.<br />

<a href="https://1.bp.blogspot.com/-HXJd4gxFSv4/V5296rU5ogI/AAAAAAAALwA/bcWuJ8nnipISjDrFeuCLCI7Xoo9EguS2gCLcB/s1600/WhatIsRsyncOSX.001.jpeg" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="480" src="https://1.bp.blogspot.com/-HXJd4gxFSv4/V5296rU5ogI/AAAAAAAALwA/bcWuJ8nnipISjDrFeuCLCI7Xoo9EguS2gCLcB/s640/WhatIsRsyncOSX.001.jpeg" width="640" /></a>

The figure above shows how I am keeping my two MacBooks and three backup locations in sync. After saving new pictures on my MacBook number 2, I do a backup (by using batchmode in RsyncOSX) to all three remote locations. 

From MacBook number 1, I do a restore from one of the remote locations.
