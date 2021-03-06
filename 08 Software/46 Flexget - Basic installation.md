<h1>Flexget - Basic installation</h1>

        
<strong>Please note!</strong> Though this software runs in nearly all cases without problems, Feral cannot provide much support for its use or help should anything go wrong. Please make sure you&#x27;ve read this FAQ fully as help on the problem may be covered already.<br>
<br>
This notice absolutely does not prevent you from raising a ticket should anything go wrong but please bear in mind staff may not be able to assist beyond basic troubleshooting (for example restarting, clarifying error messages and so on).<br>
<br>
<h2>Preparation</h2>You&#x27;ll need to execute some commands via SSH (secure shell). If you&#x27;ve never used SSH commands the idea of using a terminal window may seem daunting. There is a guide on simply getting connected to your slot through SSH <a href="https://www.feralhosting.com/faq/view?question=12">here</a>. Commands are kept as simple as possible and in most cases will simply need to be copied and pasted into the terminal window (then executed by pressing the <code>Enter</code> key).<br>
<br>
<br>
<h2>Installation - using virtualenv</h2>Flexget suggests the use of a virtual environment in its installation guide. To install using this method please execute these commands:<br>
<br>
<pre><code>pip install --user --ignore-installed --no-use-wheel virtualenv
~&#x2F;.local&#x2F;bin&#x2F;virtualenv ~&#x2F;flexget&#x2F;
~&#x2F;flexget&#x2F;bin&#x2F;pip install flexget
touch ~&#x2F;config.yml
</code></pre><br>
The final command executed will create an empty file called config.yml on your slot (at home level). This is done because creating via virtualenv does not automatically create a config.yml file. The command will not overwrite the contents of config.yml if it already exists.<br>
<br>
<br>
<h2>Installation - using pip</h2>It&#x27;s also possible to install using pip. This might be necessary if you wish to use Flexget&#x27;s deluge plugin rather than simply passing it to Deluge&#x27;s watch directory.<br>
<br>
<pre><code>pip install --user --ignore-installed --no-use-wheel flexget
touch ~&#x2F;config.yml
</code></pre><br>
The final command executed will create an empty file called config.yml on your slot (at home level). This is done because creating via virtualenv does not automatically create a config.yml file. The command will not overwrite the contents of config.yml if it already exists.<br>
<br>
<br>
<h2>Configuring</h2>Configuring the config.yml to download series is not covered in this guide. The <a href="http://flexget.com/wiki/Configuration">Flexget website</a> has lots of resources and beginner guides to get you started. <strong>Please note:</strong> staff are not able to configure your config.yml for you.<br>
<br>
The only configuration covered in this guide is passing to the various torrent clients supported at Feral. This is only needed if you wish to pass additional options to the client. Otherwise, it should be fine to simply specify the watch directory and let the client manage the torrent.<br>
<br>
<br>
<h3>rTorrent</h3>First of all you need to obtain the path to the rTorrent socket. For this, simply execute this command:<br>
<pre><code>echo $(pwd)&#x2F;private&#x2F;rtorrent&#x2F;.socket</code></pre><br>
Here is an example of a dummy guide using variables instead of actual values:<br>
<br>
<pre><code>tasks:
&nbsp; task1:
&nbsp; &nbsp; rss: rss feed URL
&nbsp; &nbsp; series:
&nbsp; &nbsp; &nbsp; - series name
&nbsp; &nbsp; rtorrent:
&nbsp; &nbsp; &nbsp; uri: <em>path_to_socket</em>
</code></pre><br>
As you might imagine, replace <em>path_to_socket</em> with the path you got from the first command.<br>
<br>
<br>
<h3>Deluge</h3>If you install Flexget to virtualenv you&#x27;ll likely encounter an error stating that dependency `deluge` is missing. For this reason you&#x27;ll need to install via pip --user (please see the second installation guide near the top of this page).<br>
<br>
In preparation you need to obtain the port that deluge is listening on. To get this simply execute the following command:<br>
<br>
<pre><code>grep daemon_port ~&#x2F;.config&#x2F;deluge&#x2F;core.conf</code></pre><br>
Here is an example of a dummy guide showing the layout. It uses variables rather than proper port numbers.<br>
<br>
<pre><code>tasks:
&nbsp; task1:
&nbsp; &nbsp; rss: rss feed URL
&nbsp; &nbsp; series:
&nbsp; &nbsp; &nbsp; - series name
&nbsp; &nbsp; deluge:
&nbsp; &nbsp; &nbsp; port: <em>deluge_port</em>
</code></pre><br>
Simply replace <em>deluge_port</em> with the number you got from the command above. Only the port is needed - flexget should be able to read the auth file for a username and password from the default location, but if you don&#x27;t specify the port it will try to connect on port 58846.<br>
<br>
<br>
<h3>Transmission</h3><br>
To use directly with transmission you first need to install and configure transmissionrpc. This is done by executing these commands:<br>
<br>
<pre><code>pip install --user transmissionrpc
sed -i &quot;s|base_url + &#x27;&#x2F;t|base_url + &#x27;&#x2F;$(whoami)&#x2F;t|g&quot; ~&#x2F;.local&#x2F;lib&#x2F;python2.7&#x2F;site-packages&#x2F;transmissionrpc&#x2F;client.py
</code></pre><br>
Here is an example of a dummy guide showing the layout. It uses variables rather than proper port numbers.<br>
<br>
<pre><code>tasks:
&nbsp; task1:
&nbsp; &nbsp; rss: rss feed URL
&nbsp; &nbsp; series:
&nbsp; &nbsp; &nbsp; - series name
&nbsp; &nbsp; transmission:
&nbsp; &nbsp; &nbsp; host: <em>server</em>.feralhosting.com
&nbsp; &nbsp; &nbsp; port: 80
&nbsp; &nbsp; &nbsp; username: <em>username</em>
&nbsp; &nbsp; &nbsp; password: <em>password</em>
</code></pre><br>
Simply replace <em>server</em> with your server name, <em>username</em> with your username and <em>password</em> with your Transmission access password.<br>
<br>
<h2>Running flexget</h2>Running flexget directly from its location will depend on the method you used to install it. If you followed the official method of creating a virtualenv then you can call it directly by executing:<br>
<br>
<pre><code>~&#x2F;flexget&#x2F;bin&#x2F;flexget execute</code></pre><br>
If you installed it using pip you would need to call it by executing:<br>
<br>
<pre><code>~&#x2F;.local&#x2F;bin&#x2F;flexget execute</code></pre><br>
Note that both of these methods will download data if properly configured and a match is found. If you don&#x27;t want this to happen simply specify the --test option.<br>
<br>
<br>
<h2>Cron - running flexget automatically</h2>Cron is a method of running jobs at regular intervals or on special pre-defined occasions. To bring up the crontab editor use the following command:<br>
<br>
<pre><code>crontab -e</code></pre><br>
If this is your very first time you&#x27;ll be given a choice of editors. Nano is fine to use so unless you specifically want something else just press enter.<br>
<br>
There will already be some basic information on crontabs in the file - you can keep it if you like, or get rid of it if you prefer. The lines are commented out so are for information purposes only and don&#x27;t affect any cron jobs added.<br>
<br>
At a new line in the file copy-paste the following:<br>
<br>
<pre><code>*&#x2F;10 * * * * <em>flexget_path</em> --cron execute</code></pre><br>
You must replace <em>flexget_path</em> with the location of the flexget binary (that could be <code>~&#x2F;flexget&#x2F;bin&#x2F;flexget</code> or <code>~&#x2F;.local&#x2F;bin&#x2F;flexget</code>).<br>
<br>
The example cron job above will run Flexget every 10 minutes. You can reduce that if you like but it&#x27;s in your interest to respect the tracker rules on this. If you don&#x27;t know what they prefer it&#x27;s best to ask (Feral will not assist circumventing a tracker ban).<br>
<br>
<h2>Troubleshooting</h2><em>On executing Flexget I get a permission denied error on &#x2F;tmp&#x2F;safe-0.4.words.cache</em><br>
Somebody else is using Flexget and writing there, so your instance will not be able to. You&#x27;ll need to set the TMPDIR variable. You can export it each time ir set it as an alias for ease of use. To set it in .bashrc execute these commands:<br>
<br>
For installation via virtualenv<br>
<pre><code>mkdir ~&#x2F;tmp
echo &quot;alias flexget=&#x27;TMPDIR=$HOME&#x2F;tmp ~&#x2F;flexget&#x2F;bin&#x2F;flexget&#x27;&quot; &gt;&gt; ~&#x2F;.bash_aliases
source ~&#x2F;.bash_aliases
</code></pre><br>
For installation via pip<br>
<pre><code>mkdir ~&#x2F;tmp
echo &quot;alias flexget=&#x27;TMPDIR=$HOME&#x2F;tmp ~&#x2F;.local&#x2F;bin&#x2F;flexget&#x27;&quot; &gt;&gt; ~&#x2F;.bash_aliases
source ~&#x2F;.bash_aliases
</code></pre><br>
You can then just use flexget from your slot to run it (options such as --test will still work with the alias).<br>
<br>
<em>When I try to connect with deluge there&#x27;s a message that dependency `deluge` is missing</em><br>
This will either be because Deluge is not installed or because you&#x27;re using the virtualenv. Firstly, please consider whether or not you could simply specify the path to Deluge&#x27;s watch folder instead. If you need to use deluge plugin, please install using the pip --user method.<br>
<br>
<em>When trying to install Flexget using pip I get an error &quot;ImportError: cannot import name IncompleteRead&quot;</em><br>
Please try installing pip using these commands before trying to install Flexget again:<br>
<br>
<pre><code>easy_install --install-dir=~&#x2F;.local&#x2F;lib&#x2F;python2.7&#x2F;site-packages pip</code></pre><br>
<br>
