---
layout: post
title:  "Add configurations"
permalink: AddConfigurations
---
Adding configurations are easy. A configuration require minimum **Local catalog** and **Remote catalog**. And they should not be equal. After entering information about a configuration select the Add button to add it to RsyncOSX. Continue adding new configurations until completed and configurations are saved to permanent storage after each entry.

Select **Local catalog** either by *drag and drop* or by *enter text* directly. For **Remote catalogs** only drag and drop for local volumes. For remote server catalogs enter by text only.

There are three types of tasks, `synchronize` which is standard, `snapshots` and `single file`. For [snapshots](/Snapshots) see documentation.

![Execute view](/images/RsyncOSX/master/add/add1.png)

### Sample configuration

Local catalog and Remote catalog are added either by using *drag and drop* from filemanager or *by text* only. If enter by text please remember to add the full path. Remote catalogs is entered either by full paths or use the `~` character to expand remote user home catalog. See sample configuration.

![Execute view](/images/RsyncOSX/master/add/add2.png)

- **Local catalog**: `/Users/thomas/Documents/`
  - my Documents catalog in my home catalog
  - required field
- **Remote catalog**: `~/Documents/`
  - the backup catalog for user thomas. The `~` is expanded as the home catalog with full path by the remote operating system. The remote catalog might also be added by full path, depends where the backup catalog is placed on remote server
  - the backup catalog might also be a local catalog on a local attached disk
  - required field
- **Remote username**: `thomas`
  - username for login to remote server
- **Remote server**: `10.0.0.57`
  - either server name or IP-adress for remote server
- **ssh port**:
  - if ssh communicates through other than standard port it must be set here, port 22 is default port for ssh and not require to set
- **ID**:
  - informal tag for the configuration
- **rsync daemon**:
  - setting this puts a double colon `::` in address parameter to rsync. It forces rsync to use the rsync daemon remote which takes some more setup. I am not using it myself.
- **Type**:
  - There are three types of tasks, `synchronize` which is standard, `snapshots` and `single file`.

About remote servers.

```
Utilizing remote servers as backup destinations
require to setup passwordless logins by ssh-keys.
```
See [passwordless logins](/ssh).

Select the `Add` button when completed and configuration is added to RsyncOSX. RsyncOSX adds a trailing `/` character to both local and remote volume. After selecting the Add button another configuration might be added. Any changes (edit or delete) to configurations are done from the Execute view. Additional parameters to rsync might be added utilizing the `Params` button.
