
<h2>My DIY NAS</h2>

This page is just a short resume about my DIY (do it yourself) <a href="https://en.wikipedia.org/wiki/Network-attached_storage" target="_blank">NAS</a>. I do not spend much time building or maintaining my NAS. The main purpose of my NAS is:
<ul>
<li>for storing backup of my files</li>
<li>and share out disk (by SMB/CIFS and AFP)</li>
</ul>
My knowledge about computer hardware is very limited. The actual hardware in the NAS is more or less selected by advices from the supplier of hardware. The most important objective was to get hardware which was supported by the OS. And the form factor of the cabinet also narrows the possibilities. The hardware in my NAS is probably not the best solution. But it works and that is for me the most important. For me, backup is very important. And backup to several locations.

<h2>Encrypt sensitive information</h2>

I am also aware of not storing personal and sensitive information at remote locations. There are several solutions for that problem. One is creating a secure folder or volume. Any OS supports this today. A second solution is to encrypt files containing personal and sensitive information (as tax reports). I am encrypting files by using <a href="https://en.wikipedia.org/wiki/GNU_Privacy_Guard" target="_blank">GPG</a>. I also encrypts files containing sensitive information in case my MacBook is compromized (which is not likly to happen due to precautions). 

I have not tested rsync on encrypted folders or volumes. I am quite sure it works, but I do not know how effective rsync is when there are changes within the encrypted folder or volume. 


<h2>Replace Oracle Solaris as NAS SW?</h2>

I have only used the trial version of Oracle Solaris 11.3. There are no updates and bugfixes for the trial version. Receiving updates and bugfixes cost money. That is the main reason for choosing other OS for my NAS. There are two options : either go for a special NAS SW ( as NAS4Free or FreeNAS) or use stock OS (as FreeBSD 11 or Ubuntu 16.10).

After some testing of <a href="https://www.freebsd.org/" target="_blank">FreeBSD 11</a>, <a href="http://www.nas4free.org/" target="_blank">NAS4free</a> and <a href="http://www.freenas.org/" target="_blank">FreeNAS</a> I have decided to go for NAS4free. I did not try Ubuntu 16.10. The decision to go for NAS4free is not scientific. I have two requirements for my NAS : ZFS and minimal effort to setup and use. And of course stability. There are also other NAS solutions but they are not built around ZFS.

<h2>So, why NAS4free?</h2>

ZFS was developed by Sun Microsystems as part of OpenSolaris. <a href="http://open-zfs.org/wiki/Main_Page" target="_blank">OpenZFS</a> is now the main developer of the open source ZFS used in FreeBSD and Linux.

I downloaded FreeNAS nightly build. FreeNAS did not boot properly on my hardware. I have read a lot of positive reviews of FreeNAS. Sorry it did not boot properly on my NAS and I dropped any further tests.

FreeBSD 11 was installed and booted fine. I played around about one day before dropping FreeBSD 11 as well. I dropped FreeBSD for one reason only. There was to much tweaking and installing of various ports to get it up and running as NAS and sharing out filesystems. Creating and mounting zpools by command line using the correct parameters is not easy. I also installed Samba (to test sharing <a href="https://en.wikipedia.org/wiki/Server_Message_Block" target="_blank">SMB</a>). Even more tweaking and I managed to connect to a shared SMB filesystem. I am quite sure I would manage to get my NAS up and running by using FreeBSD 11. But there was to much time to set up and installing.

I dropped testing of Ubuntu 16.10 due to reasons as for FreeBSD 11.

I installed NAS4free and imported zpools created in FreeBSD. After installation I used about 1 hour to get it up and running. The GUI in NAS4free is easy, intuitive and nice to use. The current stable version of NAS4Free is based upon FreeBSD 10.3 and last release of NAS4Free was Oct 2016.

I have installed the latest beta of NAS4free (Beta 11.0.0.3.3110) which is based on FreeBSD 11 (11.0-RELEASE-p3).

My NAS4Free based NAS is now setup to do the following:
<ul>
<li>Mounted a mirrored zpool used for backup by using RsyncOSX. To use RsyncOSX (or rsync) I enabled ssh and rsync on the server (by using the GUI). I added a user (thomas) and enabled <a href="https://github.com/rsyncOSX/Documentation/blob/master/PasswordlessLogin.md" target="_blank">passwordless login</a>. </li>
<li>Shared out a SMB filesystem.</li>
</ul>

<h2>The NAS</h2>

I have replaced my old NAS with new hardware. The only piece from my old NAS to keep is a Intel RAID controller. All other HW is replaced (not the storage). My old NAS from 2010 was installed in an old and heavy server cabinet. Both cabinet and hardware were ready for an upgrade. My old NAS worked well and I hesitated before I decided to upgrade. An upgrade of the hardware can quickly become a challenge if the OS does not include drivers for new hardware.

Why keep the RAID controller? First of all it is supported by Oracle Solaris and NAS4Free (FreeBSD). The motherboard has only four SATA ports. I have (including the boot disk) seven SATA disks. The RAID controller has 8-ports and all disks except the boot disk, is connected to the RAID controller. The controller is discontinued but it stills works.

<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;"><tbody>
<tr><td style="text-align: center;"><a href="https://3.bp.blogspot.com/-BWVk5GOBXiU/V4Cv0O6GoVI/AAAAAAAALqk/I233yb6_lPIYsPK2BjX1ajNSupJLAvfQQCLcB/s1600/Small%2B%25281%2Bof%2B12%2529.jpg" imageanchor="1" style="margin-left: auto; margin-right: auto;"><img border="0" height="267" src="https://3.bp.blogspot.com/-BWVk5GOBXiU/V4Cv0O6GoVI/AAAAAAAALqk/I233yb6_lPIYsPK2BjX1ajNSupJLAvfQQCLcB/s320/Small%2B%25281%2Bof%2B12%2529.jpg" width="320" /></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">Fractal Design Cabinet</td></tr>
</tbody></table>

The server OS in old NAS was Oracle Solaris 11.3 and I was tempted to try <a href="https://omnios.omniti.com/" target="_blank">OmniOS</a> (recommended by <a href="http://napp-it.org/">napp-it.org</a>). New hardware was installed and NAS was booted with the latest stable OmniOS release from a USB stick. Boot sequence ended in single user mode and no possibility to install the OS. I also tried <a href="http://www.openindiana.org/" target="_blank">OpenIndiana Hipster</a> branch. Boot sequence stopped in single user mode. I goggled the errors but no solution. I pretty quickly decided to stay with Oracle Solaris and downloaded the USB version of Oracle Solaris 11.3. <a href="http://napp-it.org/" target="_blank">Napp-it.org</a> is a GUI for administrating NAS. There are both a free and licensed version of the GUI. I am using the free version and manage the NAS from a web-browser on my Mac.<br />

The above was before the server crash 15 October 2016.

Now the NAS OS is NAS4Free. I am quite pleased to replace Oracle Solaris as OS with NAS4Free. NAS4Free is free software and it is under continuously development. The WebGUI is intuitive, nice and easy to use. It took med just a couple of minutes to format two drives, create a new mirrored zpool, create a new user and mount 1 TB of disk to use as backup for RsyncOSX.

Total disk in NAS is 6 <a href="https://en.wikipedia.org/wiki/Terabyte" target="_blank">Terrabyte</a> setup as mirror. My NAS is sharing out 3 TB.

The hardware of my 2016 NAS are:
<ol>
<li>Fractal Design Node <a href="http://www.fractal-design.com/home/product/cases/node-series/node-304-black" target="_blank">304 Mini-ITX Black</a></li>
<li>Fractal Design Integra M 450W PSU</li>
<li><a href="http://www.newegg.com/Product/Product.aspx?Item=N82E16816117157" target="_blank">Intel RAID Controller SASUC8I 8P, SAS/SATA</a> RAID 0/1/1E/10E, PCIe x8 (2x int. mini-SAS SFF-8087) (the 8-port controller is from 2011 and still working)</li>
<li><a href="https://www.msi.com/Motherboard/H110I-PRO.html#hero-overview" target="_blank">MSI H110I</a> Pro, Socket-1151 motherboard</li>
<li><a href="http://ark.intel.com/products/88185/Intel-Core-i5-6400-Processor-6M-Cache-up-to-3_30-GHz" target="_blank">Intel Core i5-6400</a>, Socket-LGA1151 processor</li>
<ul>
<li>using the Intel Core i5 as CPU in NAS is probably a overkill</li>
</ul>
<li>Kingston ValueRAM DDR4 2133MHz 16GB</li>
<li>Two WD Red 1TB NAS Harddrive, SATA 6Gb/s (SATA 3.0), 64MB, 3.5", 24x7 reliability, IntelliPower (bought in 2014)</li>
<li>Two WD Desktop Green 2TB SATA 6Gb/s, (SATA 3.0), IntelliPower, 64MB, 3.5" (bought in 2012) - one disk HW failed and replaced in 2013 without any loss of data</li>
</ol>

<h2> Setup of NAS - ZFS filesystem</h2>

The server has 3 Terrabyte (TB) of storage. The storage is setup as a ZFS filesystem and all disks (four disks altogether, two disks of 2TB each and two disks of 1TB each) are all setup as a ZFS mirror. That is the two 2TB disks are mirroring each other as well as the two 1TB disks. If one disk fails ZFS is automatically restoring (by ZFS scrub) the failing disk. If one disk fails (by HW) and must be replaced ZFS has functionality for unmounting failed disk, mount a new one and put the new one into mirrored pool again.

ZFS is a very cool and robust filesystem. You can manage ZFS filesystems by command-line, but there are some very good GUI around for that as well. I have for some years used the free version of <a href="http://napp-it.org/" target="_blank">napp-it</a>. After replacing Oracle Solaris as OS I cannot use napp-it. NAS4free includes its own webbased GUI.

So it is easy and cheap to setup a backup server based on Linux or other server OS and rsync. There is an open source project <a href="http://netatalk.sourceforge.net/" target="_blank">Netatalk</a> Apple Filing Protocol (<a href="https://en.wikipedia.org/wiki/Apple_Filing_Protocol" target="_blank">AFP</a>) fileserver. Some years ago I testet Apple Time Machine and Netatalk on a Solaris 11 server. It worked for some time, but also failed. I dont know stable Netatalk and Apple Time Machine is now. But for me rsync is the best solution. And for backups to remote servers outside my house (by Internet connection) rsync is most likely the best tool to use. By using rsync I backup all data on my Macs. A complete reinstallation of a Macbook is done by a fresh install of OS X and then restore all data by rsync. Safe and reliable.

<div class="separator" style="clear: both; text-align: center;">
<a href="https://1.bp.blogspot.com/-HXJd4gxFSv4/V5296rU5ogI/AAAAAAAALwA/bcWuJ8nnipISjDrFeuCLCI7Xoo9EguS2gCLcB/s1600/WhatIsRsyncOSX.001.jpeg" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="480" src="https://1.bp.blogspot.com/-HXJd4gxFSv4/V5296rU5ogI/AAAAAAAALwA/bcWuJ8nnipISjDrFeuCLCI7Xoo9EguS2gCLcB/s640/WhatIsRsyncOSX.001.jpeg" width="640" /></a>
