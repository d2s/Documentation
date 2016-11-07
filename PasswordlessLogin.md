<h3>Passwordless logins</h3>
 
 
Backup to offsite or remote backup locations (servers) requires some more setup. By using rsync from command-line it prompts for login ID and password. There is, as far as I know, no solution for passing login credentials to rsync command-line tool by parameter. &nbsp;But ssh has possibility to enable <b>passwordless</b> logins by using ssh generated&nbsp;private and public&nbsp;key-pair.<br />
<br />
Using <a href="https://wiki.archlinux.org/index.php/SSH_keys" target="_blank">ssh-keys</a> is in general considered more safe than standard password solutions. Ssh-keys is based upon <a href="https://en.wikipedia.org/wiki/Public-key_cryptography" target="_blank">public-key cryptography.</a><br />
<br />
To enable passwordless login by using ssh you must use ssh-keygen to create a private and public key-pair. For my second Macbook I also create a private and public key by ssh-keygen. The second public key is appended to both remote servers file authorized_keys. That is it.<br />
<br />
If the server is set up listening for ssh on other ports than standard port 22 use <code>ssh -p port</code> to use another port. In RsyncOSX there is in parameters setting possible to set another ssh port if required.<br />
<br />
<h3>
Step by step procedure</h3>
<div>
<br />
<b>Step 1</b> : create a ssh-keypair on your Mac (from the terminal window) and just press Enter every time ssh-keygen ask for input (three times).<br />
<br />
<code>Mac$ ssh-­keygen -­t rsa</code>
<br />
<br />
See <i><b>comment on ssh-keygen</b></i> below (about RSA or DSA based crypto).<br />
<b><br /></b>
<b>Step 2</b> : login to your server and create a .ssh directory in your home catalog. The instructions below are three commands, first login, then cd and then mkdir.<br />
<br />
<code>Mac$ ssh user@server.com; cd; mkdir .ssh; exit;</code>
<br />
<br />
<b>Step 3</b> : copy through ssh the public key from the Mac .ssh directory to the server.<br />
<br />
<code>Mac$ cat ~/.ssh/id_rsa.pub | ssh user@server.com "cat &gt;&gt; .ssh/authorized_keys"</code><br />
<br />
<b>Step 4</b> : login in to user@server.com and set the correct permissions for the .ssh catalog and authorized_keys file.<br />
<br />
<code>Mac$ ssh user@server.com; cd; chmod 700 .ssh;&nbsp;</code><span style="font-family: monospace;">chmod 600 .ssh/</span><span style="font-family: monospace;">authorized_keys; exit;</span><br />
<br />
<b>Step 5</b> : test login from Mac, password is not required.<br />
<br />
<code>Mac$ ssh user@server.com</code>
</div>
<div>
<div>
<h4>
</h4>
<br />
If you have two or more servers repeat <b>step 2 - step 5</b>. If you have two Macbooks and two servers (which I have) repeat step1 - step 5 for the second Macbook as well.<br />
<br />
<b><i>Comment on ssh-keygen</i></b> :<br />
<br />
My knowledge of crypto is very limited. The parameter <b>-t rsa</b> creates one key-pair based on <a href="https://en.wikipedia.org/wiki/RSA_(cryptosystem)" target="_blank">RSA</a>. It might be that your server require a key-pair based on <a href="https://en.wikipedia.org/wiki/Digital_Signature_Algorithm" target="_blank">DSA</a>. The following steps creates a key-pair based on DSA (parameter <b>-t dsa</b>):<br />
<br />
<b>Step 1</b>&nbsp;: create a ssh-keypair on your Mac (from the terminal window) and just press Enter every time ssh-keygen ask for input (three times).<br />
<br />
<code>Mac$ ssh-­keygen -­t dsa</code><br />
<b><br /></b><b>Step 2</b>&nbsp;: login to your server and create a .ssh directory in your home catalog. The instructions below are three commands, first login, then cd and then mkdir.<br />
<br />
<code>Mac$ ssh user@server.com; cd; mkdir .ssh; exit;</code><br />
<br />
<b>Step 3</b>&nbsp;: copy through ssh the public key from the Mac .ssh directory to the server.<br />
<br />
<code>Mac$ cat ~/.ssh/id_dsa.pub | ssh user@server.com "cat &gt;&gt; .ssh/authorized_keys2"</code><br />
<br />
<b>Step 4</b>&nbsp;: login in to user@server.com and set the correct permissions for the .ssh catalog and authorized_keys2 file.<br />
<br />
<code>Mac$ ssh user@server.com; cd; chmod 700 .ssh;</code><code>&nbsp;</code><span style="font-family: monospace;">chmod 600 .ssh/</span><span style="font-family: monospace;">authorized_keys2; exit;</span><br />
<br />
<b>Step 5</b>&nbsp;: test login from Mac, password is not required.<br />
<br />
<code>Mac$ ssh user@server.com</code><br />

