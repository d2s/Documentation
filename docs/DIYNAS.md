## My DIY NAS

Index of [RsyncOSX documentation](https://rsyncosx.github.io/Documentation/).

This page is a short resume about my DIY (do it yourself) [NAS](https://en.wikipedia.org/wiki/Network-attached_storage). For some time I have wanted to upgrade the old NAS (from 2010). A server crash in October 2016 forced me to commence an upgrade of both the OS and HW platform. Upgrade of the hardware can quickly become a challenge if the OS does not support the hardware. And some of the OS I tried out did not support my HW.

I do not spend much time building or maintaining my NAS. The main purposes of my NAS are:

- storing backup of my files
- and share out disk (by SMB/CIFS and/or AFP)

My knowledge about computer hardware is very limited. The hardware in new NAS is more or less selected by advices from the computer store. The most important objective is to get hardware which is supported by the OS. The form factor of the motherboard also narrows the possibilities. I want a small NAS and decided to go for a [mini-ITX](https://en.wikipedia.org/wiki/Mini-ITX) motherboard.  The hardware in my NAS is probably not the best solution.

**May 2017: there has been some (probably) HW issues regarding my NAS. Please see last section in this page.**

### Why backup

For me, backup is very important. And do backup to several locations and keep the backups in the different locations synchronized. Not loosing data is the obvious reason for doing backup. There are several ways to "loose" data. Disk crash is one. Highjacking by ransomware another. A **restore** of data is a cheap solution if either of the them occurs.

### Backup by using rsync

The rsync utility is available on most OS platforms. It has been around for some time and it is rock solid and very effective. See also [How to Use RsyncOSX](HowtoUseRsyncOSX.md) about rsync and RsyncOSX.

## Encrypt sensitive information

I am also observant of not storing personal and sensitive information unsecured at off site locations. There are several solutions to encrypt data. One is creating a secure folder or volume. Almost all OS supports [encrypted file systems](https://en.wikipedia.org/wiki/Filesystem-level_encryption) today. Another solution is to encrypt files containing personal and sensitive information (as tax reports). I am encrypting files by using [GPG](https://en.wikipedia.org/wiki/GNU_Privacy_Guard). I also encrypt files containing sensitive information in case my MacBook is **compromised** (hopefully not likely to happen due to precautions).

I have **not** tested rsync on encrypted folders or volumes. I am sure it works, but I do not know how effective rsync is when there are changes within the encrypted folder or volume.


## Setup of NAS

Until October 2016 I have only used the trial version of Oracle Solaris 11.3 and [napp-it](https://www.napp-it.org/) as NAS. I have been using trial version of Solaris and napp-it for years. It was stable until a HW failure caused a breakdown of NAS. There is one major drawback by using trial version of Solaris. There are no updates and bug fixes. Receiving updates and bug fixes cost money.

### Opensourced based NAS

There are several options for installing NAS by using free and open sourced based solutions. That was the main reason for choosing other OS for my NAS. There are two options:

- either go for a special NAS SW (as NAS4Free, FreeNAS or Openmediavolt)
- or use stock OS (as FreeBSD 11 or Ubuntu 16.10).  

### FreeBSD 11 or Ubuntu 16.10 (or 17.04)

Before going testing a NAS SW I tried out [FreeBSD 11](https://www.freebsd.org/). FreeBSD was installed and booted fine on new hardware. I played around about one day before dropping FreeBSD 11 as well. I dropped FreeBSD for one reason only. There were to much tweaking and installing of various FreeBSD ports to get it up and running as NAS and sharing out filesystems. Creating and mounting zfs filesystems by command line using the correct parameters is a non trivial task. I also installed Samba (to test sharing [SMB](https://en.wikipedia.org/wiki/Server_Message_Block)). Even more tweaking and I managed to connect to a shared SMB filesystem. I am quite sure I would manage to get my NAS up and running by using FreeBSD 11. But there was to much time to set up and installing.

I also dropped testing of Ubuntu 16.10 due to reasons as for FreeBSD 11.

### Openmediavolt

[Openmediavolt](http://www.openmediavault.org/) is not an option for me due to no native support for ZFS. There is support for ZFS by installing a plugin.

### OmniOS and OpenIndiana

Other possible OS supporting ZFS are:

- [OmniOS](https://omnios.omniti.com/) (recommended by [napp-it.org](http://napp-it.org/))
- [OpenIndiana Hipster](http://www.openindiana.org/)

Both OS booted into single user mode (due to missing support of HW). And that was an effective stop of further testing.

## FreeNAS (and NAS4Free)

I have the following requirements for my NAS:

- [ZFS](https://en.wikipedia.org/wiki/ZFS), a very robust filesystem
- minimal effort to setup and use
- stability
- ssh and rsync

The above narrows down two options:

- [NAS4free](http://www.nas4free.org/) or
- [FreeNAS](http://www.freenas.org/)

NAS4Free on FreeBSD 11.x as well as FreeNAS11-RC1. I believe FreeNAS11 is due to be released in June 2017.

[ZFS](https://en.wikipedia.org/wiki/ZFS) is an important part of my NAS. ZFS was developed by Sun Microsystems as part of OpenSolaris. [OpenZFS](http://open-zfs.org/wiki/Main_Page) is now the main developer of the open source ZFS used in FreeBSD and Linux.

For some time (about 6 months) I have used NAS4Free. Release 11.0.0.4.4040 of NAS4Free caused me some troubles. Ssh connections was broken and after upgrading I was not able to connect to the server by `ssh`. Without `ssh` RsyncOSX does not work. There is also an issue about ssh and NAS4Free. From time to time the NAS4Free server did not accept `ssh` connections. Ssh was not broken prior to release of 11.0.0.4.4040, but there were some unresolved issues.    

Time to test FreeNAS.

My *FreeNAS* based NAS is now setup to do the following:

- Mounted a mirrored zpool used for backup by using RsyncOSX. To use RsyncOSX (or rsync) I enabled ssh and rsync on the server (by using the GUI). I added a user (thomas) and enabled [passwordless login](PasswordlessLogin.md).
- sharing out a SMB and AFP filesystem.
- Accepts rsync over ssh

## Setup of NAS - ZFS filesystem

The server has 3 Terabyte (TB) of storage. The storage is setup as a ZFS filesystem and all disks (four disks altogether, two disks of 2TB each and two disks of 1TB each) are all setup as a ZFS mirror. That is the two 2TB disks are mirroring each other as well as the two 1TB disks. If one disk fails ZFS is automatically restoring (by ZFS scrub) the failing disk. If one disk fails (by HW) and must be replaced ZFS has functionality for unmounting failed disk, mount a new one and put the new one into mirrored pool again.

It is easy and cheap to setup a backup server based on Linux or other server OS and rsync. There is an open source project [Netatalk](http://netatalk.sourceforge.net/) Apple Filing Protocol ([AFP](https://en.wikipedia.org/wiki/Apple_Filing_Protocol)) fileserver. Some years ago I tested Apple Time Machine and Netatalk on a Solaris 11 server. It worked for some time, but also failed. I don't know stable Netatalk and Apple Time Machine is now. But for me rsync is the best solution. And for backups to remote servers outside my house (by Internet connection) rsync is most likely the best tool to use. By using rsync I backup all data on my Macs. A complete reinstallation of a MacBook is done by a fresh install of OS X and then restore all data by rsync. Safe and reliable.

![New configurations](screenshots/master/nas/nas1.jpeg)

## The NAS (HW)

Important : May 2017, Please be advised that my NAS HW is under revision and to be replaced. I will update this pages after new HW is installed and up and running. New HW will be based upon [recommandations](https://forums.freenas.org/index.php?resources/freenas%C2%AE-quick-hardware-guide.7/) by the FreeNAS team. For the moment I am back on stock FreeBSD 11. Imported zpools created in FreeNAS.

My FreeNAS started dying after 2-3 days operation a couple of weeks ago. No traces why, just dropped network connections and a reboot was the only way to get it up and running again. As I understand the HW in my NAS is not compliant to HW [recommandations](https://forums.freenas.org/index.php?resources/freenas%C2%AE-quick-hardware-guide.7/). But, so far, stock FreeBSD 11 is running OK.  

The plan now is to spend some time to get the correct HW pieces for FreeNAS box. Until then I am only using mye FreeBSD 11 server as backup server (by using RsyncOSX).

### New HW for NAS.

I am will replace the HW in my [Fractal Design Node 304 Mini-ITX Black](http://www.fractal-design.com/home/product/cases/node-series/node-304-black). The following new pieces are ordered:

- [ASRock E3C226D2I MB](http://www.asrockrack.com/general/productdetail.asp?Model=E3C226D2I#Specifications)
- [Intel® Pentium® Processor G3258](https://ark.intel.com/products/82723/Intel-Pentium-Processor-G3258-3M-Cache-3_20-GHz)
- [ValueRAM for ASRock Server Board E3C226D2I](http://www.kingston.com/us/memory/search?devicetype=7&mfr=ASR&line=Server%20Board&model=86498)
- Two WD Red 1TB NAS Hard drives (existing, discontinued)
- Two [WD Red 2TB](https://www.amazon.com/Red-2TB-Hard-Disk-Drive/dp/B008JJLZ7G) NAS Hard drives (buy new ones)

NAS will be setup using [ECC memory](https://en.wikipedia.org/wiki/ECC_memory).

### Old NAS

NAS is now running FreeBSD 11 until HW is replaced.

Total disk in NAS is 2 [Terabyte](https://en.wikipedia.org/wiki/Terabyte) setup as mirror. My NAS is sharing out 1 TB.

-  Fractal Design Node [304 Mini-ITX Black](http://www.fractal-design.com/home/product/cases/node-series/node-304-black)
-  Fractal Design [Integra M 450W PSU](http://www.fractal-design.com/home/product/power-supplies/integra-m/integra-m-450w)
-  [MSI H110I](https://www.msi.com/Motherboard/H110I-PRO.html#hero-overview) Pro, Socket-1151 motherboard
-  [Intel Core i5-6400](http://ark.intel.com/products/88185/Intel-Core-i5-6400-Processor-6M-Cache-up-to-3_30-GHz), Socket-LGA1151 processor
-  Kingston ValueRAM DDR4 2133MHz 16GB
-  Two WD Red 1TB NAS Hard drive, SATA 6Gb/s (SATA 3.0), 64MB, 3.5", 24x7 reliability, IntelliPower (bought in 2014)
