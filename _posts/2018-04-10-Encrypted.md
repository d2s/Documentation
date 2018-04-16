---
layout: post
title:  "Encrypted backups"
permalink: Encrypted
---
`Rsync` does not support encrypted backups by itself. It is probably possible to do encrypted backups utilize filesystems as [encfs](https://github.com/vgough/encfs). [Rclone](https://github.com/ncw/rclone) is "a rsync for cloud storage" command line tool which also supports encrypted backups. By combining `rclone` and `rsync`, encrypted backups is enabled within RsyncOSX. If your primary object is saving encrypted backups on cloud storage services only there is no need for RsyncOSX. I am saving some personal data on remote servers (not cloud storage) and encrypts the data before synchronizing data.

## Encrypted backups utilizing RcloneOSX and RsyncOSX

The setup below is just an example of setup utilizing my demo of encrypted backups. RcloneOSX is port of and a minor version of RsyncOSX for synchronizing backups to cloud storages utilizing the `rclone` utility.

In rclone, add a [crypt](https://rclone.org/crypt/) remote. The remote encrypted catalog in `rclone config` is set to `/Volumes/Home/thomas/demoEncryptedrclone`. The cloudservice in `rclone config` is named `demoEncrypted`. In RcloneOSX add source and backup location utilizing the encrypted remote. I have set up rclone to encrypt files, filenames and catalogs by using maximum encryption key length. I have set up RcloneOSX to do encrypted backups of my `demoEncryptedorg` catalog to a locale catalog `demoEncryptedrclone` by utilizing the encryption functionality  within rclone.

### How does it work

RsyncOSX reads the configuration files for RcloneOSX. Within RsyncOSX connect the backup task with RcloneOSX configuration. After connection is set up the task is renamed `combined`. Execution of a `combined` task first executes the rclone command and then the rsync command. RsyncOSX reads the RcloneOSX config and computes the rclone parameters before executing the rclone command and then the rsync command.

Enable encrypted backups in RsyncOSX require three initial steps:

- setup encrypted backup in by `rclone config`
- setup encrypted backup in RcloneOSX utilizing the encrypted cloudservice setup in `rclone config`
- setup and connect the encrypted backup within RsyncOSX

After the above steps are done executing encrypted backups with RsyncOSX is enabled. It is advised to test a restore of the encrypted backup. The mapping in `rclone` can be verified by the following command `rclone ls demoEncrypted: --crypt-show-mapping` (the `demoEncrypted:` is the cloudservice name set up in `rclone`).

A restore of the local encrypted catalog can be verified with `/usr/local/bin/rclone sync demoEncrypted: /Volumes/Home/thomas/tmp --dry-run --verbose` or by RcloneOSX. The command restores whatever is saved within the encrypted catalog to my tmp catalog in home directory.

### Setup in RcloneOSX

The catalog `/Volumes/Home/thomas/demoEncryptedorg` is the not encrypted source catalog to be backed up. The catalog `/Volumes/Home/thomas/demoEncryptedrclone` is the catalog where rclone is by `rclone config`, setup to encrypt and store whatever is in the source catalog.
![Main view](/images/RsyncOSX/master/encrypted/rclone1.png)
After setup in RcloneOSX utlizing the cloudservice `demoEncrypted:`, a dry-run is executed to verify the task.
![Main view](/images/RsyncOSX/master/encrypted/rclone2.png)

### Setup in RsyncOSX and connection to RcloneOSX

A task in RsyncOSX is added to sync the encrypted catalog `/Volumes/Home/thomas/demoEncryptedrclone` and synchronize it to a catalog `/mnt/backup2/temp/demoEncryptedserver/` on my freenas.local server at home (as a demo).
![Main view](/images/RsyncOSX/master/encrypted/rsync1.png)
After adding the above backup task, a connection between the RsyncOSX task and RcloneOSX task is required.
![Main view](/images/RsyncOSX/master/encrypted/connect1.png)
A red row indicates that there is a connection. A combined task is marked `combined`.
![Main view](/images/RsyncOSX/master/encrypted/connect2.png)
Execution of a combined task is done by `⌘R` command after selecting the task.
![Main view](/images/RsyncOSX/master/encrypted/connect3.png)
The rsync part of task is logged.
![Main view](/images/RsyncOSX/master/encrypted/log.png)

### My encrypted Documents catalog
View of how my Documents catalog looks like encrypted.
![Main view](/images/RsyncOSX/master/encrypted/documents.png)
