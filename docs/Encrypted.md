## Encrypted backups

Index of [RsyncOSX documentation](https://rsyncosx.github.io/Documentation/).

RsyncOSX does not support encrypted backups. It is probably possible to do encrypted backups utilize filesystems as [encfs](https://github.com/vgough/encfs). I have found another solution which require two steps. Until now I have not backup up my Documents catalog on remote servers.

[Rclone](https://github.com/ncw/rclone) is "a rsync for cloud storage" command line tool. I have developed RcloneOSX which is a GUI utilizing rclone. RcloneOSX is a minor version of RsyncOSX, but for simple backups it works.

## Encrypted backups utilizing rclone

![Main view](screenshots/master/encrypted/rclone.png)
![Main view](screenshots/master/encrypted/rsyncosx.png)
