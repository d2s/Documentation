## Setup passwordless logins

Index of [RsyncOSX documentation](https://rsyncosx.github.io/Documentation/).

This `ssh` part of RsyncOSX is a kind of experimental. The objective is to assist setting up [passwordless](PasswordlessLogin.md) logins. Ssh does not provide any possibilities to pass password as parameter. Some actions therefore require a terminal window for copy/paste commands for password prompt and execution of task.

### Local ssh keys

Below is the main view. There are no local public ssh keys found and keys might be created. Either choose a `rsa` or `dsa` based private and public key pair or both (once a time).

* Rsa public key found (if file `~/.ssh/id_rsa.pub` exists)
* Dsa public key found (if file `~/.ssh/id_dsa.pub` exists)
* `Create keys`, either rsa or dsa based (by `ssh-keygen`)  

### Remote server

After local private and public ssh key pair is created choosing `Remote server` to select which remote server to setup. It is required to [add](AddConfigurations.md) configuration before setting up passwordless logins.

* `Ssh directory` - copy and paste command in Terminal.app to create remote `~/.ssh` catalog
* `Scp rsa` - copy and paste command in Terminal.app to secure copy public rsa key.
* `Scp dsa` - copy and paste command in Terminal.app to secure copy public dsa key


![ssh](screenshots/master/ssh/ssh.png)

### Create local ssh keys

Choosing a `rsa` based key and select `Create keys`. Local keys are created by `ssh-keygen` and saved in `.ssh` local catalog.

![ssh](screenshots/master/ssh/ssh2.png)

Next step is to manually create a remote `.ssh` catalog and `scp` (secure copy) the public key to remote host.

![ssh](screenshots/master/ssh/ssh3.png)
