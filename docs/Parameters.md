## Parameters to rsync

The parameters in picture (below) instructs rsync to save changed files in catalog `../backup` (relativ to destination catalog) and **suffix** the backup file with timestamps. The above is enabled or disabled by select the `backup` button. The user might change the backup catalog. The backup catalog can either be absolute path or relative path. Default backup catalog is `../backup`.

See also the [standard parameters](https://github.com/rsyncOSX/Documentation/blob/master/docs/RsyncParameters.md) to rsync.

Rsync utilises a ton of parameters. RsyncOSX has only presented a few. Parameters are normally constructed as:

- `--parameter=value` 
	- sample `--exclude-from=/Volumes/Users/thomas/Pictures/exclude-list.txt`
- `--parameter` 
	- sample `--stats`, `--dry-run`

I am using RsyncOSX to backup my Pictures catalog - about 100GB of raw picture files. I am also using Adobe Lightroom for organising my Pictures. Adobe Lightroom creates preview of pictures in `Lightroom/Lightroom Catalog Previews.lrdata` catalog. I do not want to backup any previews, only the picture files, Lightroom settings and Lightroom library catalog. 

- create a .txt file with the following line `Lightroom/Lightroom Catalog Previews.lrdata`, save the file with name `exclude-list.txt` in the `Pictures` catalog
- pass the following parameter `--exclude-from=/Volumes/Users/thomas/Pictures/exclude-list.txt` to rsync from the parameter view within RsyncOSX

And that is it. Rsync excludes whatever found in the `--exclude-from` file (including file patterns).

### RsyncOSX passing parameters to rsync

The user can set own parameters by using `user` in dropdown menu. Preset parameters are:

- `user` - _user selected_ parameter
	- RsyncOSX passes whatever set by user to rsync, parameters must be either `--parameter=value` or `--parameter`
- `--stats` - produces some more statistics
	- parameter is forced on in dry-ryn to collect info about run
- `--backup` - instructs rsync to backup changed files
- `--backup-dir` - where to store changed or deleted files before rsync syncronise source and destination
- `--exclude-from` - path to file which stores file patterns to **exclude** from rsync backup
- `--include-from` - path to file which store file patterns to **include** from rsync backup 
- `--files-from` - path to file which store what to backup
- `--max-size` - set max size of files to backup
	- sample `--max-size=5MB` 
- `--suffix` - set suffix on files
	- sample <code>--suffix= _\`date +'%Y-%m-%d.%H.%M'`</code> see last picture for result
		- I have experienced some variations regarding the suffix. Some OS will not set the correct suffix using the above. If so is true use `--suffix= _$(date +%Y-%m-%d.%H.%M)` instead.
- `delete` - delete the parameter
	- deletes the parameter when `OK` button is selected
	- or just delete the `value` string

<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;"><tbody>
<tr><td style="text-align: center;"><a href="https://1.bp.blogspot.com/-mFUGksTyUAA/WAmhilxPsnI/AAAAAAAAL5Y/s9lXbqBNRnkCTS1WPyjHmafFJAyNYF8qACLcB/s1600/Screen%2BShot%2B2016-10-20%2Bat%2B09.17.32.png" imageanchor="1" style="margin-left: auto; margin-right: auto;"><img border="0" height="336" src="https://1.bp.blogspot.com/-mFUGksTyUAA/WAmhilxPsnI/AAAAAAAAL5Y/s9lXbqBNRnkCTS1WPyjHmafFJAyNYF8qACLcB/s640/Screen%2BShot%2B2016-10-20%2Bat%2B09.17.32.png" width="640" /></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">Either set preselected parameters or your own parameters</td></tr>
</tbody></table>

If the backup directory is not created rsync automatically creates it. The `../backup` is a catalog relative to the destination catalog. The user can specify any catalog as backup catalog.

<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;"><tbody>
<tr><td style="text-align: center;"><a href="https://1.bp.blogspot.com/-rAioO-XrAm4/WAmhjC1UD6I/AAAAAAAAL5c/hx8vydOMgTY1dppLCd2SCQyspBca7HgsgCLcB/s1600/Screen%2BShot%2B2016-10-20%2Bat%2B09.18.09.png" imageanchor="1" style="margin-left: auto; margin-right: auto;"><img border="0" height="336" src="https://1.bp.blogspot.com/-rAioO-XrAm4/WAmhjC1UD6I/AAAAAAAAL5c/hx8vydOMgTY1dppLCd2SCQyspBca7HgsgCLcB/s640/Screen%2BShot%2B2016-10-20%2Bat%2B09.18.09.png" width="640" /></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">After selecting the "backup" parameter three new parameters are added to rsync task</td></tr>
</tbody></table>

The screen below is a listing of some of files moved to the backup directory and renamed before new files are transferred from source to destination.<br />

<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;"><tbody>
<tr><td style="text-align: center;"><a href="https://2.bp.blogspot.com/-3PGnAGBlXlU/WAmhlm9ispI/AAAAAAAAL6Y/6tGAo1yevaM9uGCgMUGSCq3-J-0xyZqYACEw/s1600/Screen%2BShot%2B2016-10-20%2Bat%2B10.29.41.png" imageanchor="1" style="margin-left: auto; margin-right: auto;"><img border="0" height="448" src="https://2.bp.blogspot.com/-3PGnAGBlXlU/WAmhlm9ispI/AAAAAAAAL6Y/6tGAo1yevaM9uGCgMUGSCq3-J-0xyZqYACEw/s640/Screen%2BShot%2B2016-10-20%2Bat%2B10.29.41.png" width="640" /></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">Changed files are moved to backup catalog and renamed with date and time as suffix</td></tr>
</tbody></table>
