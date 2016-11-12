## Rsync parameters
 
Rsync has a ton of possible parameters. RsyncOSX implements standard parameters which are working fine for simple backup and restore tasks. The actual parameters used in tasks is depended upon executing rsync over network connection or not. Which parameters to use is computed during startup of application by reading the configuration file.

RsyncOSX does also facilitate user selected parameters. User selected parameters are stored by each task.
<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;"><tbody>
<tr><td style="text-align: center;"><a href="https://3.bp.blogspot.com/-srgKvwoP9I8/WBwsnVzdkKI/AAAAAAAAL78/mM567JKI5QoM6HJVGFxhJGatJ1EzMw2jQCLcB/s1600/Screen%2BShot%2B2016-11-04%2Bat%2B07.35.43.png" imageanchor="1" style="margin-left: auto; margin-right: auto;"><img border="0" height="336" src="https://3.bp.blogspot.com/-srgKvwoP9I8/WBwsnVzdkKI/AAAAAAAAL78/mM567JKI5QoM6HJVGFxhJGatJ1EzMw2jQCLcB/s640/Screen%2BShot%2B2016-11-04%2Bat%2B07.35.43.png" width="640" /></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">The menu for adding parameters to rsync (by task)</td></tr>
</tbody></table>

## Standard parameters all tasks

The following parameters is applied to all tasks (both backup and restore).

- <code>--archive</code>
	- ensures that all files are transferred with all attributes preserved
- <code>--verbose</code>
	- make rsync very outspoken, required for counting files in RsyncOSX
- <code>--delete</code>
	- delete all files at destination which is not in source

## Standard parameters network tasks only
The following parameters is for networked tasks only.

- <code>--compress</code>
	- compress files before transmitting
- <code>- e ssh</code>
	- to ensure rsync tunnels traffic through a ssh-tunnel
- <code>-e "ssh -p xxxx"</code>
	- choose another port if standard port 22 is not used
- enable by setting port number in parameters

## Details about the sample parameters

The website LibreByte has done an article about rsync and [14 Pratical examples of the rsync command] (http://www.librebyte.net/en/gnulinux/14-practical-examples-of-the-rsync-command/). One of the examples is instructing rsync to store backups of files in a backup folder and rename old files by a date suffix.

The first parameters (of five parameters) in figure are for excluding some files (the file <code>exclude-list.txt</code> is only one line with <code>*.pdf</code> which instructs rsync to omit all files with suffix pdf).
The parameters are (in the correct order to work and no (important) white spaces). The only white space is between date and + sign <code>$(date +...)</code> in third parameter.

- <code>--backup</code>
- <code>--backup-dir=../backup</code>
- <code>--suffix=_$(date +%Y-%m-%d.%H.%M)</code>

The three last parameters creates a new directory <code>../backup</code> relative to the destination directory (<code>~/Documents/backup</code>). Any updated documents in source instructs rsync to move the old document in destination to backup folder and add a date + time suffix to the file (<code>filename_2016-06-14.10.31</code>) before copying the updated document from source to destination.
