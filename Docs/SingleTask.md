<h2>Executing configurations</h2>

In main view (which is the opening view) tasks can be executed as <b>single</b>- and/or <b>batch</b> tasks. Execute single tasks requires selecting the Execute button twice : one for <b>estimation</b> run and the second for <b>executing</b> the real task. If the Information is on a view of output from rsync is presented after each click.

There are three options for editing after selecting a task in row :
<ul>
<li><b>Edit task</b></li>
<li><b>Parameters</b> (to rsync)</li>
<li><b>Delete task</b></li>
</ul>

For Parameters see below. After selecting a row choosing one of the above pops up a new view according to selection. Selecting Edit task for editing basic information about task. Selecting Delete task deletes the selected row (task).

There are some status fields in the view :
<ul>
<li><b>Estimate</b> - text is either "Estimate" or "Execute" - valid for single tasks only</li>
<ul>
<li>"Estimate" - selecting Execute does a --dry-run</li>
<li>"Execute" - selecting Execute does the real job (backup or restore)</li>
</ul>
<li><b>Scheduled job</b> - a progress bar shows when a scheduled job is executing</li>
<li><b>Information</b> - if checked a drop down view is presented after each run - valid for single tasks only</li>
<li><b>Estimating</b> - a progress bar shows when a --dry-run (or estimate) is executing </li>
</ul>

<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;"><tbody>
<tr><td style="text-align: center;"><a href="https://2.bp.blogspot.com/-PslDJNhqRdc/WAmhihscUDI/AAAAAAAAL5U/CXCxco5tfPQNYCWgZUQfp5odxVLGe_wpQCLcB/s1600/Screen%2BShot%2B2016-10-20%2Bat%2B09.17.14.png" imageanchor="1" style="margin-left: auto; margin-right: auto;"><img border="0" height="336" src="https://2.bp.blogspot.com/-PslDJNhqRdc/WAmhihscUDI/AAAAAAAAL5U/CXCxco5tfPQNYCWgZUQfp5odxVLGe_wpQCLcB/s640/Screen%2BShot%2B2016-10-20%2Bat%2B09.17.14.png" width="640" /></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">Selecting a configuration for actions </td></tr>
</tbody></table>
<span style="font-weight: normal;">Both "backup" and "restore" path is set when saving configuration.</span>

<h2>Execute single tasks</h2>

Execute single tasks is a <b>two step</b> operation, one for <b>estimation</b> (dry-run) and one for the <b>real task</b>. If the Information button is ticked on a popup view is automatically presented after both tasks.Single tasks can be executed either by selecting the Execute button or (if enabled) double click on the selected task. Both methods is a two step operation.<br />
<div class="separator" style="clear: both; text-align: center;">
</div>
<br /></div>
<div class="separator" style="clear: both; text-align: center;">
<a href="https://2.bp.blogspot.com/-LTOFBw_xhOE/WAmhj5hGMVI/AAAAAAAAL6Y/xXWeO9_fF9QKvWEcTfntmIbYRS_ONI-bwCEw/s1600/Screen%2BShot%2B2016-10-20%2Bat%2B09.22.32.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="336" src="https://2.bp.blogspot.com/-LTOFBw_xhOE/WAmhj5hGMVI/AAAAAAAAL6Y/xXWeO9_fF9QKvWEcTfntmIbYRS_ONI-bwCEw/s640/Screen%2BShot%2B2016-10-20%2Bat%2B09.22.32.png" width="640" /></a></div>
<div>
The process info is updated when either a estimation task is executing or if a scheduled task is executing. There are five numbers in bottom page. Only version 3.x counts the number of remote directories. The numbers are files to be transferred and remote numbers. </div>

<h3>Estimating</h3>

The actual rsync command to be executed is shown below right corner in view. It is only the estimation command which is shown. You might copy the command and paste it into a terminal for execution. You have to delete the --dry-run parameter to execute the real task.

If you dont want to do a two step task chose Execute batch task (se below).</div>
<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;"><tbody>
<tr><td style="text-align: center;"><a href="https://3.bp.blogspot.com/-IpJOm7XOh5U/WAmhjNPsE2I/AAAAAAAAL5k/8-9ECrKp_hsopC-a1ToXQhhpGHS28QpIwCLcB/s1600/Screen%2BShot%2B2016-10-20%2Bat%2B09.21.54.png" imageanchor="1" style="margin-left: auto; margin-right: auto;"><img border="0" height="336" src="https://3.bp.blogspot.com/-IpJOm7XOh5U/WAmhjNPsE2I/AAAAAAAAL5k/8-9ECrKp_hsopC-a1ToXQhhpGHS28QpIwCLcB/s640/Screen%2BShot%2B2016-10-20%2Bat%2B09.21.54.png" width="640" /></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">Result of estimation run</td></tr>
</tbody></table>
Next task shows what the next task is. It shows three status : Estimate, Execute or Abort. If Abort is pressed any executing task is aborted.<br />

<h3>Executing</h3>

After estimate run is completed and result is checked, a real run is executed by selecting the Execute button again. If you select another row after estimation a new estimation run must be completed. </div>
<div class="separator" style="clear: both; text-align: center;">
<a href="https://4.bp.blogspot.com/-UxuIHn1pinM/WAmhjiJG6vI/AAAAAAAAL5o/285zrZW9RW0G_5Pg8odaL6ekIiKLeavNQCLcB/s1600/Screen%2BShot%2B2016-10-20%2Bat%2B09.22.14.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="336" src="https://4.bp.blogspot.com/-UxuIHn1pinM/WAmhjiJG6vI/AAAAAAAAL5o/285zrZW9RW0G_5Pg8odaL6ekIiKLeavNQCLcB/s640/Screen%2BShot%2B2016-10-20%2Bat%2B09.22.14.png" width="640" /></a></div>
