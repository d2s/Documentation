<h3>Rsync parameters</h3>
 
Rsync has a ton of possible parameters. RsyncOSX implements standard parameters which are working fine for simple backup and restore tasks. The actual parameters used in tasks is depended upon executing rsync over network connection or not. Which parameters to use is computed during startup of application by reading the configuration file.<br />
<br />
<br />
RsyncOSX does also facilitate user selected parameters. User selected parameters are stored by each task.<br />
<br />
<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;"><tbody>
<tr><td style="text-align: center;"><a href="https://3.bp.blogspot.com/-srgKvwoP9I8/WBwsnVzdkKI/AAAAAAAAL78/mM567JKI5QoM6HJVGFxhJGatJ1EzMw2jQCLcB/s1600/Screen%2BShot%2B2016-11-04%2Bat%2B07.35.43.png" imageanchor="1" style="margin-left: auto; margin-right: auto;"><img border="0" height="336" src="https://3.bp.blogspot.com/-srgKvwoP9I8/WBwsnVzdkKI/AAAAAAAAL78/mM567JKI5QoM6HJVGFxhJGatJ1EzMw2jQCLcB/s640/Screen%2BShot%2B2016-11-04%2Bat%2B07.35.43.png" width="640" /></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">The menu for adding parameters to rsync (by task)</td></tr>
</tbody></table>
<br />
<div class="separator" style="clear: both; text-align: center;">
</div>
<br />
<h3>
Standard parameters all tasks</h3>
<div>
<br /></div>
<div>
The following parameters is applied to all tasks (both backup and restore).</div>
<div>
<ul>
<li><code>--archive</code></li>
<ul>
<li>ensures that all files are transferred with all attributes preserved</li>
</ul>
<li><code>--verbose</code></li>
<ul>
<li>make rsync very outspoken, required for counting files in RsyncOSX</li>
</ul>
<li><code>--delete</code></li>
<ul>
<li>delete all files at destination which is not in source</li>
</ul>
</ul>
<div>
<br /></div>
<div>
<h3>
Standard parameters network tasks only</h3>
</div>
<div>
<br /></div>
<div>
<br /></div>
<div>
The following parameters is for networked tasks only.</div>
<div>
<ul>
<li><code>--compress</code></li>
<ul>
<li>compress files before transmitting</li>
</ul>
<li><code>- e ssh</code></li>
<ul>
<li>to ensure rsync tunnels traffic through a ssh-tunnel</li>
</ul>
<li><code>-e "ssh -p xxxx"</code></li>
<ul>
<li>choose another port if standard port 22 is not used</li>
<li>enable by setting port number in parameters</li>
</ul>
</ul>
<div>
<br />
<h3>
Details about the sample parameters</h3>
</div>
</div>
</div>
<div>
<br /></div>
<div>
The website LibreByte&nbsp;has done an article about rsync and "<a href="http://www.librebyte.net/en/gnulinux/14-practical-examples-of-the-rsync-command/" target="_blank">14 Pratical examples of the rsync command</a>". One of the examples is instructing rsync to store backups of files in a backup folder and rename old files by a date suffix.<br />
<br />
The first parameters (of five parameters) in figure are for excluding some files (the file&nbsp;<code>exclude-list.txt</code>&nbsp;is only one line with&nbsp;<code>*.pdf</code>&nbsp;which instructs rsync to omit all files with suffix pdf).</div>
<div>
<br /></div>
<div>
The parameters are (in the correct order to work and no (important) white spaces). The only white space is between date and + sign <code>$(date +...)</code> in third parameter.</div>
<div>
<ul>
<li><code>--backup</code></li>
<li><code>--backup-dir=../backup</code></li>
<li><code>--suffix=_$(date +%Y-%m-%d.%H.%M)</code></li>
</ul>
The three last parameters creates a new directory <code>../backup</code> relative to the destination directory (<code>~/Documents/backup</code>). Any updated documents in source instructs rsync to move the old document in destination to backup folder and add a date + time suffix to the file (<code>filename_2016-06-14.10.31</code>) before copying the updated document from source to destination.
