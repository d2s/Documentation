<h2>Add configuration</h2>

Adding configurations is easy. One configuration require as minimum only "Local catalog" and "Remote catalog". And they cannot be equal. After entering information about a configuration selecting the Add button adds it to RsyncOSX. Continue adding new configurations until completed and configurations are saved to permanent store when choosing another tab (as Execute or other).

Select "Local catalog" either by "drag and drop", by enter text directly or by GUI (press the folder icon).  For "Remote catalogs" only drag and drop or GUI for local volumes. For remote server catalogs enter by text only.

<h3>Single file</h3>

If "Single file" is on, RsyncOSX adds backup of single file only. No restore part is added, use Copy files for search and restore.

<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;"><tbody>
<tr><td style="text-align: center;"><img border="0" height="336" src="https://1.bp.blogspot.com/-0qO_rSeuBKA/WAmhh79NoVI/AAAAAAAAL5E/eIDabOVSaWUSDf7GnvcgB79fdNpNNksZwCLcB/s640/Screen%2BShot%2B2016-10-20%2Bat%2B08.52.01.png" style="margin-left: auto; margin-right: auto;" width="640" /></td></tr>
<tr><td class="tr-caption" style="text-align: center;">The Add view - selecting Folder icon presents a GUI for local catalogs</td></tr>
</tbody></table>
<div class="separator" style="clear: both; text-align: center;">
<a href="https://1.bp.blogspot.com/-0qO_rSeuBKA/WAmhh79NoVI/AAAAAAAAL5E/eIDabOVSaWUSDf7GnvcgB79fdNpNNksZwCLcB/s1600/Screen%2BShot%2B2016-10-20%2Bat%2B08.52.01.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"></a><br /></div>
<h3>Local and remote catalogs</h3>
Local catalog and Remote catalog (if not on remote server) is added either by using "drag and drop" from filemanager or by GUI (select the icon) or by text only. If enter by text please rember to add the full path. Remote catalogs is entered either by full paths or use the "~" character to expand remote user home catalog (if remote backup catalog is in users home catalog somewhere). See sample configuration below.
<a href="https://1.bp.blogspot.com/-0qO_rSeuBKA/WAmhh79NoVI/AAAAAAAAL5E/eIDabOVSaWUSDf7GnvcgB79fdNpNNksZwCLcB/s1600/Screen%2BShot%2B2016-10-20%2Bat%2B08.52.01.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"></a>
<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;"><tbody>
<tr><td style="text-align: center;"><a href="https://3.bp.blogspot.com/-c2w2h5xX9ag/WAmhh0ImdxI/AAAAAAAAL5I/oMN2h-FxbQU6cQbQVj3O4VERrnnpfqeLgCLcB/s1600/Screen%2BShot%2B2016-10-20%2Bat%2B08.52.31.png" imageanchor="1" style="margin-left: auto; margin-right: auto;"><img border="0" height="366" src="https://3.bp.blogspot.com/-c2w2h5xX9ag/WAmhh0ImdxI/AAAAAAAAL5I/oMN2h-FxbQU6cQbQVj3O4VERrnnpfqeLgCLcB/s640/Screen%2BShot%2B2016-10-20%2Bat%2B08.52.31.png" width="640" /></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">Adding local catalogs by GUI</td></tr>
</tbody></table>
<h3>Sample configuration</h3>
The screen below is all information about my configuration for a virtual FreeBSD instance running on my Macbook Pro.
<ul>
<li><b>Local catalog</b>: - path for my RsyncOSX src (as an example)</li>
<li><b>Remote catalog</b>: - ~/src/RsyncOSX is the home catalog for user thomas (the ~ is expanded as the home catalog with full path by the remote operating system), the remote catalog might also be added by full path (/home/thomas/src/RsyncOSX)</li>
<li><b>Remote username</b>: - thomas</li>
<li><b>Remote server</b>: - either name or IP-adress, 127.0.0.1 is the IP-adress for the virtual FreeBSD instance</li>
<li><b>ssh port</b>: - if ssh communicates through other than standard port 22 it must be set here. In Virtualbox I have set up a port forwarding through port 3022 -&gt; Virtualbox port 22.</li>
<li><b>rsync daemon</b>: - setting this puts a double colon :: in address parameter to rsync. It forces rsync to use the rsync daemon remote which takes some more setup. I am not using it myself.</li>
</ul>
<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;"><tbody>
<tr><td style="text-align: center;"><a href="https://2.bp.blogspot.com/-gi2FYh-_LBY/WAmhiEf5ZrI/AAAAAAAAL5M/q592yuxR-QIxu9c2ES9RctnCHQClwlowgCLcB/s1600/Screen%2BShot%2B2016-10-20%2Bat%2B09.16.23.png" imageanchor="1" style="margin-left: auto; margin-right: auto;"><img border="0" height="336" src="https://2.bp.blogspot.com/-gi2FYh-_LBY/WAmhiEf5ZrI/AAAAAAAAL5M/q592yuxR-QIxu9c2ES9RctnCHQClwlowgCLcB/s640/Screen%2BShot%2B2016-10-20%2Bat%2B09.16.23.png" width="640" /></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">Information about configuration for a Virtual machine</td></tr>
</tbody></table>
<h3>The Add button</h3>
Select the Add button when completed and configurations are added to RsyncOSX.  RsyncOSX adds the "/" character to both local and remote volume. Both the <b>backup</b> and <b>restore</b> part is added when saving new configurations. After selecting the Add button another configuration might be added. Any changes (edit or delete) to configurations are done from the main view (Execute tab).

<div class="separator" style="clear: both; text-align: center;">
<a href="https://4.bp.blogspot.com/-EeBIBxlJE0s/WAmhiWeeGDI/AAAAAAAAL5Q/__WJIgbs2bYVcqqLby79vgC4niFvkGy2gCLcB/s1600/Screen%2BShot%2B2016-10-20%2Bat%2B09.16.46.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="336" src="https://4.bp.blogspot.com/-EeBIBxlJE0s/WAmhiWeeGDI/AAAAAAAAL5Q/__WJIgbs2bYVcqqLby79vgC4niFvkGy2gCLcB/s640/Screen%2BShot%2B2016-10-20%2Bat%2B09.16.46.png" width="640" /></a></div>
