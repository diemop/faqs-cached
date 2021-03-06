<h1>SickRage - Installation and Configuration</h1>

        
<strong>Please note!</strong> Though this software runs in nearly all cases without problems, Feral cannot provide much support for its use or help should anything go wrong. Please make sure you&#x27;ve read this FAQ fully as help on the problem may be covered already.<br>
<br>
This notice absolutely does not prevent you from raising a ticket should anything go wrong but please bear in mind staff may not be able to assist beyond basic troubleshooting (for example restarting, clarifying error messages and so on).<br>
<br>
<h2>Preparation</h2>You&#x27;ll need to execute some commands via SSH (secure shell). If you&#x27;ve never used SSH commands the idea of using a terminal window may seem daunting. There is a guide on simply getting connected to your slot through SSH <a href="https://www.feralhosting.com/faq/view?question=12">here</a>. Commands are kept as simple as possible and in most cases will simply need to be copied and pasted into the terminal window (then executed by pressing the <code>Enter</code> key).<br>
<br>
<br>
<h2>Installation - using the automated bash script</h2>Features of the bash script:<br>
<br>
&nbsp; 1.&nbsp; Installs Sick Beard or SickRage from GitHub (this guide only covers SickRage - for Sick Beard please see <a href="https://www.feralhosting.com/faq/view?question=332">this guide</a>)<br>
&nbsp; 2. Configures the proxypass to provide an https URL<br>
&nbsp; 3. Can to choose to update the software and&#x2F;or install only the proxypass<br>
<br>
To use the script just use this command:<br>
<br>
<pre><code>wget -qO ~&#x2F;install.sick <a href="http://git.io/vfGch">http:&#x2F;&#x2F;git.io&#x2F;vfGch</a> &amp;&amp; bash ~&#x2F;install.sick</code></pre><br>
<br>
<h2>Installation - manual</h2>Manual installation allows a greater degree of control but the automated script should be sufficient for the majority of use cases.<br>
<br>
<br>
<h3>Clone SickRage from GitHub</h3>First you need to download SickRage by cloning the repository onto your slot. To do that, copy-paste the following:<br>
<br>
<pre><code>git clone <a href="https://github.com/SickRage/SickRage">https:&#x2F;&#x2F;github.com&#x2F;SickRage&#x2F;SickRage</a> ~&#x2F;.sickrage</code></pre><br>
There&#x27;s another repo you could use (SiCKRAGETV) if you wanted. To clone that the command would be:<br>
<br>
<pre><code>git clone <a href="https://github.com/SiCKRAGETV/SickRage">https:&#x2F;&#x2F;github.com&#x2F;SiCKRAGETV&#x2F;SickRage</a> ~&#x2F;.sickrage</code></pre><br>
<br>
<h3>Start up SickRage</h3>To start up SickRage we need to pick a port for it to run on. In the command below replace <em>port</em> with a number between <strong>10001</strong> and <strong>49999</strong><br>
<br>
<pre><code>python ~&#x2F;.sickrage&#x2F;SickBeard.py -d -p <em>port</em> --pidfile=&quot;$HOME&#x2F;.sickrage&#x2F;sickrage.pid&quot;</code></pre><br>
If nothing happens or there is an error it could be that the port you picked is in use. Simply try with a different number.<br>
<br>
Once started up you can visit SickRage by visiting <code><a href="http://">http:&#x2F;&#x2F;</a><em>server</em>.feralhosting.com:<em>port</em></code> where <em>server</em> is the name of your server and <em>port</em> is the port you picked earlier.<br>
<br>
Within the SickRage UI, click the Config icon (the two gears at the top) and then click General. Next, click the Interface tab. Near the bottom of the fields you&#x27;ll be able to set a username and password for the web UI. Whilst it&#x27;s not mandatory you do this, it is a sensible thing to do.<br>
<br>
<br>
<h3>Configure the proxypass</h3>The bash script in the first Installation section can set up the proxypass for you without installing SickRage, so even if you wish to use a different repository you can still make use of the script for this purpose.<br>
<br>
<br>
<h2>Configuring</h2>This section covers connecting SickRage to the three torrent clients currently supported by Feral: rTorrent, Deluge and Transmission. In SickRage&#x27;s user interface click the Config icon (the two gears at the top) and then click Search Settings. Next, click the Torrent Search tab. You can choose the torrent client you want to configure from the menu.<br>
 <br>
<br>
<h3>rTorrent</h3> First of all you need to configure the rTorrent RPC and this is done by switching from apache to nginx. That can be done by following <a href="https://www.feralhosting.com/faq/view?question=231">this guide</a>.<br>
<br>
Enter the details as follows:<br>
<br>
<code>Torrent host:port</code>: <a href="https://">https:&#x2F;&#x2F;</a><em>server</em>.feralhosting.com&#x2F;<em>username</em>&#x2F;rtorrent&#x2F;rpc&#x2F; (replace <em>server</em> with your server name and <em>username</em> with your username)<br>
&nbsp; &nbsp; <br>
<code>Http Authentication</code>: Basic<br>
&nbsp; &nbsp; <br>
<code>Client username</code>: <code>rutorrent</code> (the word rutorrent, <em>not</em> your ruTorrent username)<br>
<br>
<code>Client password</code>: The same password as you use to access ruTorrent<br>
<br>
<br>
<h3>Deluge (via webUI)</h3>Enter the details as follows:<br>
<br>
<code>Torrent host:port</code>: <a href="https://">https:&#x2F;&#x2F;</a><em>server</em>.feralhosting.com&#x2F;<em>username</em>&#x2F;deluge&#x2F; (replace <em>server</em> with your server name and <em>username</em> with your username)<br>
<br>
<code>Client password</code>: Your Deluge webUI password<br>
<br>
<code>Downloaded files location</code>: It might be set to rTorrent&#x27;s data directory - make sure it&#x27;s set to a location you&#x27;re happy with (or make sure it&#x27;s blank to use Deluge&#x27;s default).<br>
<br>
<br>
<h3>Deluge (via daemon)</h3>There are a couple of commands we need to run via SSH first to obtain the daemon port and password (the password is not the same as the webUI password).<br>
<br>
To find the port run this command:<br>
<br>
<pre><code>sed -rn &#x27;s&#x2F;(.*)&quot;daemon_port&quot;: (.*),&#x2F;\2&#x2F;p&#x27; ~&#x2F;.config&#x2F;deluge&#x2F;core.conf</code></pre><br>
To find the password run this command:<br>
<br>
<pre><code>sed -rn &quot;s&#x2F;$(whoami):(.*):(.*)&#x2F;\1&#x2F;p&quot; ~&#x2F;.config&#x2F;deluge&#x2F;auth</code></pre><br>
Armed with the port and password, enter the details as follows:<br>
<br>
<code>Torrent host:port</code>: <a href="https://">https:&#x2F;&#x2F;</a><em>server</em>.feralhosting.com:<em>port</em> (replace <em>server</em> with your server name and <em>port</em> with the results of the command above)<br>
<br>
<code>Client username</code>: Your Deluge daemon username (unless you&#x27;ve changed it, it&#x27;ll be your Feral username)<br>
&nbsp; &nbsp; <br>
<code>Client password</code>: Your Deluge daemon password<br>
<br>
<code>Downloaded files location</code>: Makke sure it&#x27;s set to a location you&#x27;re happy with (or make sure it&#x27;s blank to use Deluge&#x27;s default).<br>
<br>
<br>
<h3>Transmission</h3>Enter the details as follows:<br>
<br>
<code>Torrent host:port</code>: <a href="https://">https:&#x2F;&#x2F;</a><em>server</em>.feralhosting.com&#x2F;<em>username</em> (replace <em>server</em> with your server name and <em>username</em> with your username)<br>
<br>
<code>Transmission RPC URL</code>: <code>transmission&#x2F;rpc</code><br>
&nbsp; &nbsp; <br>
<code>Client username</code>: The username you use to access Transmission<br>
<br>
<code>Client password</code>: The same password as you use to access Transmission<br>
<br>
<br>
<h3>SABnzbd</h3>SickRage can also search for NZB files. This section covers connecting Sick Beard to <a href="https://www.feralhosting.com/faq/view?question=125">SABnzbd</a>.<br>
<br>
Enter the details as follows:<br>
<br>
<code>SABnzbd server URL</code>: <a href="https://">https:&#x2F;&#x2F;</a><em>server</em>.feralhosting.com:<em>port</em>&#x2F;sabnzbd&#x2F; (replace <em>server</em> with your server name and <em>port</em> with your HTTPS port for SABnzbd)<br>
<br>
<code>SABnzbd username</code>: The username you set for the SABnzbd UI<br>
<br>
<code>SABnzbd password</code>: The password you set for the SABnzbd UI<br>
<br>
<code>SABnzbd API key</code>: Find this in the General section of SABnzbd&#x27;s settings<br>
<br>
<br>
<h2>Starting and restarting</h2>In order to restart the software the existing process should be killed. If the check below does not display a process number please proceed to step 3. These steps are tailored towards processes started by this FAQ.<br>
<br>
1.&nbsp; &nbsp; Check:<br>
<pre><code>pgrep -fu &quot;$(whoami)&quot; &quot;python $HOME&#x2F;.sickrage&#x2F;SickBeard.py -d&quot;</code></pre>&nbsp; &nbsp; <br>
2.&nbsp; &nbsp; Kill:<br>
<pre><code>kill &quot;$(pgrep -fu &quot;$(whoami)&quot; &quot;python $HOME&#x2F;.sickrage&#x2F;SickBeard.py -d&quot;)&quot;</code></pre>&nbsp; &nbsp; <br>
3.&nbsp; &nbsp; Restart: <br>
<pre><code>python ~&#x2F;.sickrage&#x2F;SickBeard.py -d --pidfile=&quot;$HOME&#x2F;.sickrage&#x2F;sickrage.pid&quot;</code></pre><br>
<strong>Important note:</strong> You can repeat step 1 after attempting to kill to check if it&#x27;s been shut down. Give the program at least 10 seconds to shut down at step 2 before trying to restart. If it refuses to exit then you have to force it to quit using this command instead:<br>
<br>
<pre><code>kill -9 &quot;$(pgrep -fu &quot;$(whoami)&quot; &quot;python $HOME&#x2F;.sickrage&#x2F;SickBeard.py -d&quot;)&quot;</code></pre><br>
<br>
<h2>Cron - start up automatically if the server is rebooted</h2>Unfortunately sometimes the server needs to be rebooted. When this happens the system will start up a lot of the processes automatically on your slot. It will not however start up custom software. We need to manually set something up to make this happen.<br>
<br>
To bring up the crontab editor use the following command:<br>
<br>
<pre><code>crontab -e</code></pre><br>
If this is your very first time you&#x27;ll be given a choice of editors. Nano is fine to use so unless you specifically want something else just press enter.<br>
<br>
There will already be some basic information on crontabs in the file - you can keep it if you like, or get rid of it if you prefer. The lines are commented out so are for information purposes only and don&#x27;t affect any cron jobs added.<br>
<br>
At a new line in the file copy-paste the following:<br>
<br>
<pre><code>
@reboot rm -rf ~&#x2F;.sickrage&#x2F;sickrage.pid
@reboot python ~&#x2F;.sickrage&#x2F;SickBeard.py -d --pidfile=&quot;$HOME&#x2F;.sickrage&#x2F;sickrage.pid&quot;
</code></pre><br>
<br>
<h2>Troubleshooting</h2><em>When I click &quot;Test Connection&quot; I get the error &#x27;Error: Unable to connect to rTorrent&#x27;</em><br>
If rTorrent is running and you&#x27;ve <a href="https://www.feralhosting.com/faq/view?question=231">switched to nginx</a> this likely means some of the details you&#x27;ve entered are not correct. Please double-check that your username is <strong>rutorrent</strong> (as in the actual word, &quot;rutorrent&quot;, <em>not</em> the username you use to log in to ruTorrent). <br>
<br>
<em>I went to start up SickRage and received an error &#x27;...sickrage.pid already exists. Exiting.&#x27;</em><br>
Assuming you&#x27;re using the default locations please run the following command before trying the start up command again:<br>
<pre><code>rm ~&#x2F;.sickrage&#x2F;sickrage.pid</code></pre><br>
<br>
