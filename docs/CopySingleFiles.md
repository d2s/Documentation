## Copy single files or catalogs

Copy file and volume enables the user to select single file or catalogs for restore to a selected local storage. The _source_ for copy is the _selected row in Execute view_. Pressing `select` button starts the job to collect list of files and catalogs stored on remote server.

List of files and folders stored at remote server.

![Schedule](screenshots/master/restore/copy1.png)

Remote file or catalog is selected and restore point is set.

![Schedule](screenshots/master/restore/copy2.png)

After selecting pressing the Estimate button instructs rsync to do a --dry-run.

![Schedule](screenshots/master/restore/copy3.png)

