---
layout: post
title:  "Add configurations"
permalink: AddConfigurations
---
Adding configurations is easy. A configuration require minimum **Local catalog** and **Remote catalog**. And they should not be equal (obvious). After entering information about a configuration select the Add button to add it to RsyncOSX. Continue adding new configurations until completed and configurations are saved to permanent storage after each entry.

Select **Local catalog** either by *drag and drop* or by *enter text* directly. For **Remote catalogs** only drag and drop for local volumes. For remote server catalogs enter by text only.

If **Single file** is *on*, RsyncOSX adds backup of single file only. Use Copy files for search and restore.
![Execute view](/images/RsyncOSX/master/add/add1.png)

### Local and remote catalogs

Local catalog and Remote catalog (if not on remote server) is added either by using *drag and drop* from filemanager or *by text* only. If enter by text please remember to add the full path. Remote catalogs is entered either by full paths or use the `~` character to expand remote user home catalog. See sample configuration below.

### Sample configuration

The screen below is all information about my configuration for a virtual FreeBSD instance running on my Macbook Pro.

- **Local catalog**: `/Volumes/Home/thomas/Documents/` - my Documents catalog in my home catalog.
- **Remote catalog**: `~/Documents/` - the backup catalog for user thomas. The `~` is expanded as the home catalog with full path by the remote operating system. The remote catalog might also be added by full path, depends where the backup catalog is placed on remote server.
- **Remote username**: `thomas`, username remote server
- **Remote server**: `freenas.local` either name or IP-adress
- **ssh port**: if ssh communicates through other than standard `port 22` it must be set here
- **ID**: `informal tag` for the configuration
- **rsync daemon**: setting this puts a double colon `::` in address parameter to rsync. It forces rsync to use the rsync daemon remote which takes some more setup. I am not using it myself.
![Add configuration](/images/RsyncOSX/master/add/add3.png)

**Caution:** utilizing remote servers as backup destinations require to setup [passwordless logins](/ssh) by ssh-keys.

### The Add button

Select the `Add new` button when completed and configuration is added to RsyncOSX. RsyncOSX adds a trailing `/` character to both local and remote volume (if the `Single file` is not on). After selecting the Add button another configuration might be added. Any changes (edit or delete) to configurations are done from the Execute view (Execute tab).

If `Single file` is ticked on no trailing character `/` is added.
![Configurations added](/images/RsyncOSX/master/add/add4.png)
Go back to Execute tab and there are a new row. Additional parameters to rsync might be added utilizing the `Params` button.
![Backup and restore](/images/RsyncOSX/master/add/add5.png)
