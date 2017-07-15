## My DIY NAS

Index of [RsyncOSX documentation](https://rsyncosx.github.io/Documentation/).

This page is a short resume about my DIY (do it yourself) [NAS](https://en.wikipedia.org/wiki/Network-attached_storage). For some time I have wanted to upgrade the old NAS (from 2010). A server crash in October 2016 forced me to commence an upgrade of both the OS and HW platform. Upgrade of the hardware can quickly become a challenge if the OS does not support the hardware. And some of the OS I tried out did not support my HW.

I do not spend much time building or maintaining my NAS. The main purposes of my NAS are:

- storing backup of my files
- and share out disk (by SMB/CIFS and/or AFP)

My knowledge about computer hardware is very limited. The most important objective is to get hardware which is supported by the OS or NAS SW. The form factor of the motherboard also narrows the possibilities. I want a small NAS and decided to go for a [mini-ITX](https://en.wikipedia.org/wiki/Mini-ITX) motherboard.  

To choose the correct HW as NAS is not an easy task. I have spend some time googling, reading HW-guides and checking for availability of HW. My advise is use some time before buying HW. My local supplier used about four weeks to get the HW I ordered. And it seems like most HW pushers are more focused on desktop computers and MS Windows than dedicated server HW. Not much help to get in other words.


### Why backup

For me, backup is very important. Do backup to several locations and keep the backups in the different locations synchronized. Not loosing data is the obvious reason for doing backup. There are several ways to “loose” data. HW or disk crash is one. Highjacking by ransomware another. A **restore** of data is a cheap solution if either of the them occurs.

### Backup by using rsync

The rsync utility is available on most OS platforms. It has been around for some time and it is rock solid and very effective. See also [How to Use RsyncOSX](HowtoUseRsyncOSX.md) about rsync and RsyncOSX.

## Encrypt sensitive information

I am also observant of not storing personal and sensitive information not encrypted at remote locations. There are several solutions to encrypt data. One is creating a secure folder or volume. Almost all OS supports [encrypted file systems](https://en.wikipedia.org/wiki/Filesystem-level_encryption) today. Another solution is to encrypt files containing personal and sensitive information (as tax reports). I am encrypting files by using [GPG](https://en.wikipedia.org/wiki/GNU_Privacy_Guard). I also encrypt files containing sensitive information in case my MacBook is **compromised** (hopefully not likely to happen due to precautions).

I have **not** tested rsync on encrypted folders or volumes. I am sure it works, but I do not know how effective rsync is when there are changes within the encrypted folder or volume.

## Setup of NAS

Until October 2016 I have only used the trial version of Oracle Solaris 11.3 and [napp-it](https://www.napp-it.org/) as NAS. I have been using trial version of Solaris and napp-it for years. It was stable until a HW failure caused a breakdown of NAS. There is one major drawback by using trial version of Solaris. There are no updates and bug fixes. Receiving updates and bug fixes cost money.

### Opensourced based NAS

There are several options for installing NAS by using free and open sourced based solutions. That was the main reason for choosing other OS for my NAS. There are two options:

- either go for a special NAS SW (as NAS4Free, FreeNAS or Openmediavolt)
- or use stock OS (as FreeBSD 11 or Ubuntu 16.10).  

### FreeBSD 11 or Ubuntu 16.10 (or 17.04)

Before testing a dedicated NAS SW I tried out [FreeBSD 11](https://www.freebsd.org/). I played around about one day before dropping FreeBSD 11 as well. I dropped FreeBSD for one reason only. There were to much tweaking and installing of various FreeBSD ports to get it up and running as NAS and sharing out filesystems. Creating and mounting ZFS filesystems by command line using the correct parameters is a non trivial task. I also installed Samba (to test sharing [SMB](https://en.wikipedia.org/wiki/Server_Message_Block)). Even more tweaking and I managed to connect to a shared SMB filesystem. I am quite sure I would manage to get my NAS up and running by using FreeBSD 11. But there was to much time to set up and installing.

I also dropped testing of Ubuntu 16.10 due to reasons as for FreeBSD 11.

### Openmediavolt

[Openmediavolt](http://www.openmediavault.org/) is not an option for me due to no native support for ZFS. There is support for ZFS by installing a plugin.

### OmniOS and OpenIndiana

Other possible OS supporting ZFS are:

- [OmniOS](https://omnios.omniti.com/) (recommended by [napp-it.org](http://napp-it.org/))
- [OpenIndiana Hipster](http://www.openindiana.org/)

Both OS booted into single user mode (due to missing support of (old) HW). And that was an effective stop of further testing.

## FreeNAS (and NAS4Free)

I have the following requirements for my NAS:

- [ZFS](https://en.wikipedia.org/wiki/ZFS) which is a very robust filesystem
- minimal effort to setup and use
- stability
- ssh and rsync

The above narrows down two options:

- [NAS4free](http://www.nas4free.org/) or
- [FreeNAS](http://www.freenas.org/)

Both NAS4Free and FreeNAS 11 is built on FreeBSD 11.x. FreeNAS 11 was [released](https://forums.freenas.org/index.php?threads/freenas-11-0-released.55327/) in June 2017.

[ZFS](https://en.wikipedia.org/wiki/ZFS) is an important part of my NAS. ZFS was developed by Sun Microsystems as part of OpenSolaris. [OpenZFS](http://open-zfs.org/wiki/Main_Page) is now the main developer of the open source ZFS used in FreeBSD and Linux (and other OS as well).

For some time (about 6 months) I have used NAS4Free. Release 11.0.0.4.4040 of NAS4Free caused me some troubles. Ssh connections was broken and after upgrading I was not able to connect to the server by `ssh`. Without `ssh` RsyncOSX does not work. There is also an issue about ssh and NAS4Free. From time to time the NAS4Free server did not accept `ssh` connections. Ssh was not broken prior to release of 11.0.0.4.4040, and I did not manage to resolve the issues.    

### Time to test FreeNAS

Due to some issues regarding NAS4Free I decided to test FreeNAS.

My *FreeNAS* based NAS is now setup to do the following:

- Mounted a mirrored zpool used for backup by using RsyncOSX. To use RsyncOSX (or rsync) I enabled ssh and rsync on the server (by using the GUI). I added a user (thomas) and enabled [passwordless login](PasswordlessLogin.md).
- sharing out a SMB and AFP filesystem.
- Accepts rsync over ssh

## Setup of NAS - ZFS filesystem

The server has 3 Terabyte (TB) of storage. The storage is setup as a ZFS filesystem and all disks (four disks altogether, two disks of 2TB each and two disks of 1TB each) are all setup as a ZFS mirror. That is the two 2TB disks are mirroring each other as well as the two 1TB disks. If one disk fails ZFS is automatically restoring (by ZFS scrub) the failing disk. If one disk fails (by HW) and must be replaced ZFS has functionality for unmounting failed disk, mount a new one and put the new one into mirrored pool again.

It is easy and cheap to setup a backup server based on Linux or other server OS and rsync. There is an open source project [Netatalk](http://netatalk.sourceforge.net/) Apple Filing Protocol ([AFP](https://en.wikipedia.org/wiki/Apple_Filing_Protocol)) fileserver. Some years ago I tested Apple Time Machine and Netatalk on a Solaris 11 server. It worked for some time, but also failed. I don't know how stable Netatalk and Apple Time Machine is now. But for me rsync is the best solution. And for backups to remote servers outside my house (by Internet connection) rsync is most likely the best tool to use. By using rsync I backup all data on my Macs. A complete reinstallation of a MacBook is done by a fresh install of OS X and then restore all data by rsync. Safe and reliable.

![New configurations](screenshots/master/nas/nas1.jpeg)

## The NAS (HW)

**July 2017** New HW is installed in NAS.

New HW in NAS is based upon [recommendations](https://forums.freenas.org/index.php?resources/freenas%C2%AE-quick-hardware-guide.7/) by the FreeNAS team.

The **old** NAS HW which was running FreeNAS started dying after 2-3 days operation. No traces why, just dropped network connections and a reboot was the only way to get it up and running again. As I understand the HW in my NAS is not compliant to HW recommendations, kind of "dodgy" HW as a FreeNAS forum member commented.

### New HW for NAS.

June 2017 I ditched the old NAS HW and installed new HW components. My NAS is build by the following components. The components in NAS is server components and a bit more expensive than desktop components.

- [Fractal Design Node 304 Mini-ITX Black](http://www.fractal-design.com/home/product/cases/node-series/node-304-black) - compact chassis which max 6 3.5 inch HD drives
- Fractal Design [Integra M 450W PSU](http://www.fractal-design.com/home/product/power-supplies/integra-m/integra-m-450w)
- [ASRock E3C226D2I MB](http://www.asrockrack.com/general/productdetail.asp?Model=E3C226D2I#Specifications) - server motherboard
- [Intel® Pentium® Processor G3258](https://ark.intel.com/products/82723/Intel-Pentium-Processor-G3258-3M-Cache-3_20-GHz)
- [KVR16E11/8 ValueRAM for ASRock Server Board E3C226D2I](http://www.kingston.com/us/memory/search?devicetype=7&mfr=ASR&line=Server%20Board&model=86498) - ECC server memory
- Two WD Red 1TB NAS Hard drives (existing, discontinued)
- Two [WD Red 2TB](https://www.amazon.com/Red-2TB-Hard-Disk-Drive/dp/B008JJLZ7G) NAS Hard drives (buy new ones)

NAS is setup by using [ECC memory](https://en.wikipedia.org/wiki/ECC_memory). Total disk in NAS is 6 [Terabyte](https://en.wikipedia.org/wiki/Terabyte) setup as mirror, sharing out 3 TB.

[Nerd Monkey](http://www.nerd-monkey.com/test-6-nas__expert_for_up_to_6_drives_with_ecc_memory_aes_ni_and_ipmi) wrote an article utilizing the ASRock E3C226D2I MB and Kingston KVR16E11/8 ValueRAM, equal MB and memory as my new NAS HW.

[Here](https://blog.brianmoses.net/2017/07/my-thoughts-after-upgrading-to-freenas-11.html?mkt_tok=eyJpIjoiWm1FMU1tTTBNVEV4TlRrNSIsInQiOiJnT0pjVStjTSs2MnJGQzU3dnl2czh5NWV3QllLT1dGU0wwV1NEbm5DNUFvS2JNNFQxeWw3dWc3Z0ZTaTZpNnpMdWdheXBma3FsUWlGZ3RoeVlnT2F0TitrY2lweEhETDNTdDBQd20rdmg4bzlZdElZWWlaXC9OXC81ZDVRbk5ncHJxIn0%3D#disqus_thread) another interesting story about FreeNAS 11. 

### Old NAS

Old NAS was running FreeBSD 11. The HW in old NAS was not compatible with FreeNAS, but it ran without any problems for about 4 weeks with FreeBSD.  If you are setting up a NAS yourself choose the right HW. It might be some more expensive, but it saves you for troubles later on.

-  [MSI H110I](https://www.msi.com/Motherboard/H110I-PRO.html#hero-overview) Pro, Socket-1151 motherboard
-  [Intel Core i5-6400](http://ark.intel.com/products/88185/Intel-Core-i5-6400-Processor-6M-Cache-up-to-3_30-GHz), Socket-LGA1151 processor
-  Kingston ValueRAM DDR4 2133MHz 16GB
