## User configuration

There are only a few parameters to choose in user configuration. The three parameters are:
 
 - another version of rsync
 	- any version of rsync should work, but only _rsync  version 3.1.2  protocol version 31_ and _rsync  version 2.6.9  protocol version 29_ is tested and verified. 
 - detailed logging on or off 
 	- if detailed logging is **on** all _backup_ tasks are logged, if **off** only last date for task is updated in Execute view
 - allow double click to execute single tasks
 	- if **on** any single task might be executed by double click on a row
 
If the user selectes another version of rsync, RsyncOSX does check if there is a rsync in path set by user. If there is no rsync in path RsyncOSX will not execute any tasks. The red _configurations_ (rows in table) is only because I have not started my VirtualBox FreeBSD instance and RsyncOSX does not receive any answer (check is done automatically)

<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;">
<tbody>
<tr><td style="text-align: center;">
<a href="https://2.bp.blogspot.com/-h7b8RpZ9lc4/WBQqLxmCMyI/AAAAAAAAL7U/mhef5atFxcITHPg0Z1OnNmU7bmXuzfbigCLcB/s1600/Screen%2BShot%2B2016-10-29%2Bat%2B06.48.11.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="336" src="https://2.bp.blogspot.com/-h7b8RpZ9lc4/WBQqLxmCMyI/AAAAAAAAL7U/mhef5atFxcITHPg0Z1OnNmU7bmXuzfbigCLcB/s640/Screen%2BShot%2B2016-10-29%2Bat%2B06.48.11.png" width="640" /></a></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">User selected parameters.</td></tr>
</tbody>
</table>

### No rsync i path

The views below is what happens if a not valid rsync path is set. First of a error is presented in bottom of user configuration.

<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;">
<tbody>
<tr><td style="text-align: center;">
<a href="https://1.bp.blogspot.com/-hygkB2SLc_M/WCdKYhJOhBI/AAAAAAAAL94/Uhv_Q-EhgVE_qbYwFHWwcF1ij5azzypkgCLcB/s1600/Screen%2BShot%2B2016-11-12%2Bat%2B17.56.56.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="336" src="https://1.bp.blogspot.com/-hygkB2SLc_M/WCdKYhJOhBI/AAAAAAAAL94/Uhv_Q-EhgVE_qbYwFHWwcF1ij5azzypkgCLcB/s640/Screen%2BShot%2B2016-11-12%2Bat%2B17.56.56.png" width="640" /></a></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">Error - missing a rsync in path.</td></tr>
</tbody>
</table>
If there is a missing rsync in optional path no execution of tasks is allowed (it gives no meaning of executing a task wihout a rsync).
<table align="center" cellpadding="0" cellspacing="0" class="tr-caption-container" style="margin-left: auto; margin-right: auto; text-align: center;">
<tbody>
<tr><td style="text-align: center;">
<a href="https://4.bp.blogspot.com/-iELDYlqrkIg/WCdKYN4iCNI/AAAAAAAAL90/zihVBpuGrqgk_FMXs7jQowuIK6TtfLuewCLcB/s1600/Screen%2BShot%2B2016-11-12%2Bat%2B17.57.11.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="318" src="https://4.bp.blogspot.com/-iELDYlqrkIg/WCdKYN4iCNI/AAAAAAAAL90/zihVBpuGrqgk_FMXs7jQowuIK6TtfLuewCLcB/s640/Screen%2BShot%2B2016-11-12%2Bat%2B17.57.11.png" width="640" /></a></a></td></tr>
<tr><td class="tr-caption" style="text-align: center;">No joy.</td></tr>
</tbody>
</table>
