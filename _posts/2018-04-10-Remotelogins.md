---
layout: post
title:  "Passwordless logins to remote servers"
permalink: Remotelogins
---

By utilizing rsync and ssh (the `-e ssh` parameter to rsync) enables **passwordless** logins to **remote servers** by ssh private and public key-pair.

Using [ssh-keys](https://wiki.archlinux.org/index.php/SSH_keys) is in general considered more safe than standard password solutions (single factor authentication). Ssh-keys is based upon [public-key cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography).

- RsyncOSX can assist you [in setting up passwordless logins](/ssh)
- or you can [enable passwordless logins manually](/PasswordlessLogin)

There is also possible to setup RsyncOSX utilizing a **rsync daemon** setup for synchronizing files to remote servers.

- this is a special setup and require some [tweaking](/Rsyncdaemon)

Rsync is reading a local file with password information when connecting to the server side rsync daemon.
