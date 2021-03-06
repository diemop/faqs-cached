<h1>Using Your Account - Common Questions</h1>

        
All accounts currently come with these features:<br>
<br>
SSH (command-line access) - <a href="https://www.feralhosting.com/faq/view?question=12">SSH Guide - The Basics</a><br>
SFTP (secure file transfer) - <a href="https://www.feralhosting.com/faq/view?question=187">SFTP using Filezilla</a><br>
FTP (insecure file transfer) - <a href="https://www.feralhosting.com/faq/view?question=187">FTP using Filezilla</a><br>
HTTP &#x2F; PHP &#x2F; APACHE &#x2F; NGINX &#x2F; A Valid SSL Domain - <a href="https://www.feralhosting.com/faq/view?question=20">Putting Your WWW Folder to Use</a><br>
<br>
Available to install via the <code>Install Software</code> link in your <a href="https://www.feralhosting.com/manager/">Account Manager</a> - <a href="https://www.feralhosting.com/faq/view?question=6">more info</a><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/install_software_link.png"><br>
<br>
rutorrent&#x2F;rTorrent - <a href="https://www.feralhosting.com/faq/view?question=202">Selecting an rtorrent version</a><br>
Deluge &#x2F; Deluge Web Ui + Deluge Thin Client - <a href="https://www.feralhosting.com/faq/view?question=76">Deluge Daemon - Remote control with the local Thin client</a><br>
Transmission &#x2F; Transmission Web Ui + Transmission remote GUI - <a href="https://www.feralhosting.com/faq/view?question=4">Transmission and Transmission Remote GUI</a><br>
MYSQL - <a href="https://www.feralhosting.com/faq/view?question=9">Using Mysql</a><br>
OpenVPN - <a href="https://www.feralhosting.com/faq/view?question=5">Using Openvpn</a><br>
Host your own website - <a href="https://www.feralhosting.com/faq/view?question=52">Host a virtual host on your Feral slot</a><br>
<br>
<h2>How can I pay?</h2><br>
Feral accepts Stripe and Bitcoin with instant set-up times for new users (once the funds are actually received by Feral). GoCardless (UK only) and Amazon payments is available for users to renew existing slots.<br>
<br>
<h2>Bitcoin</h2><br>
If you would like to pay via Bitcoin we recommend these companies:<br>
<br>
<a href="https://www.coinbase.com/">Coinbase</a><br>
<br>
<a href="https://www.kraken.com/">Kraken</a><br>
<br>
<h2>What is account credit and how does it work?</h2><br>
Account credit is applied on a case by case basis by Staff. It is not something that is done automatically and we ask for a little patience during the process. When credit has been applied to your account you will see it in your Account Manager and you may then use it against the cost of your services at renewal time or when purchasing additional services.<br>
<br>
<h2>I want more disk space, how do I get it?</h2><br>
There is no way to provide a slot with increased storage capacity once it has been set up. In order to increase storage capacity or to take advantage of offers related to storage capacity you will be required to purchase an new slot. You can start the upgrade process yourself at any time by following this procedure - <a href="https://www.feralhosting.com/faq/view?question=33"> Slot Upgrades - Additional Disk Space or Speed Requirements</a>.<br>
<br>
<h2>My current Slot has less space that the current slots but the price is the same! How do I get more space?</h2><br>
We are constantly striving to improve our products and offer the best available value to the user. This means that sometimes the available plans changes their storage capacity. Unfortunately there is no way to provide a slot with increased storage capacity once it has been set up. So this is not something we can apply to your slot.<br>
<br>
But! you can upgrade at anytime to a new plan to take advantage of the better value, all you need to do is follow this process:<br>
<br>
<a href="https://www.feralhosting.com/faq/view?question=33">Slot Upgrades - Additional Disk Space or Speed Requirements</a>.<br>
<br>
<h2>Can I send emails from my slot?</h2><br>
Email has been blocked due to abuse from people attempting to spam. If you need to send email from your programs or Web Apps you can usually configure them to use an external smtp service like <code>Google Apps</code>. Here is an example of the configuration settings - <a href="https://www.digitalocean.com/community/articles/how-to-use-google-s-smtp-server">Google smtp settings</a><br>
<br>
<h2>Does my slot have a dedicated IP? </h2><br>
Your server has a dedicated IP that is shared by all the users on your server. So while your slot does have a dedicated IP, this IP is not unique to you.<br>
<br>
<h2>Can I have my Slot IP changed?</h2><br>
If you have a valid&nbsp; reason that you can substantiate then please <a href="https://www.feralhosting.com/manager/tickets/new">open a ticket</a> and ask for a dedicated IP. Please do not forget to provide your supporting evidence as to why you require a new IP.<br>
<br>
<h2>Is my slot a dedicated server? Is this&nbsp; a VPS?</h2><br>
No, Feral does not provide any dedicated servers or a VPS type service.<br>
<br>
Your slot will be on a powerful server that is shared by other users. Your account will be a user account on the currently running Linux OS that powers the servers.<br>
<br>
<h2>Where is my slot located? Where are the the servers hosted.</h2><br>
The servers are hosted at the <a href="http://www.interxion.com">Interxion</a> carrier-neutral data centre in the <a href="http://en.wikipedia.org/wiki/Netherlands">Netherlands</a>.<br>
<br>
<h2>Can I install Deluge, rTorrent&#x2F;rutorrent, rtorrent and transmission or can I only use one?</h2><br>
You can install and use all three applications if you want. All software on the Install Software page can be installed at the same time and actively used. You can also run more than one instance of certain applications, like Deluge and rTorrent as well. Staff might not support or troubleshoot your second running instances though, but if they do it is at their discretion.<br>
<br>
<h2>What OS is running on my slot &#x2F; What version of Linux is running on my slot?</h2><br>
Your slot is running on Debian Stable.<br>
<br>
This SSH command will show you your current Debian version<br>
<br>
<pre><code>lsb_release -d</code></pre><br>
<h2>OpenVPN - How many open and active connections can I have?</h2><br>
You can only have <code>1</code> active connection per OpenVPN server at any one time. This would usually mean one connected device at a time.<br>
<br>
You can use <a href="https://www.feralhosting.com/faq/view?question=37">SSH tunnels</a>, as there is no limit on how many tunnels you can open and create.<br>
<br>
<h2>Disk quota - How can I check mine?</h2><br>
<a href="https://www.feralhosting.com/faq/view?question=221">Check your disk quota in SSH</a> or use the provided Usage analyser in the manager <a href="https://www.feralhosting.com/manager/slot/usage?">Usage</a> (note this URL might not take you to the right slot if you have more than one)<br>
<br>
<h2>What software or programs will Staff install on request for me, via tickets?</h2><br>
Feral do not support external or third party applications that they do not provide as part of their set-up. Though some things can be installed upon request.<br>
<br>
<strong>1:</strong> <a href="http://packages.debian.org/stable/">Packages Debian stable</a> - You can make a request for versions of applications in this repository. You should provide your reasoning in the ticket (at the Staff&#x27;s discretion).<br>
<br>
<strong>2:</strong> Required dependencies of applications, such as Python libs. You should provide your reasoning in the ticket (at the Staff&#x27;s discretion).<br>
<br>
<strong>3:</strong> You can always raise a ticket and ask if you are unsure. This does not cover them installing or configuring applications for you. It is only for installing things that are part of the Debian stable repo, that are required for you to run your application.<br>
<br>
<h2>Can I install my own software?</h2><br>
Users do not have Root privileges so cannot use apt or package managers to install software. See this FAQ for a more in depth explanation with many linked examples - <a href="https://www.feralhosting.com/faq/view?question=195">Generic Software Installation Guide</a><br>
<br>
If you require packages and dependencies that are part of the Debian Stable branch, open a ticket and ask staff if they can install them. This is something they will do for users, but they will not support the installation or maintenance of software that they have not provided.<br>
<br>
<h2>Can I share my account?</h2><br>
Feral only supports one user account. This means they will only provide and support one set of user credentials (your account username and password). If you wish to share these credentials you can, but you do so at your own risk. Anyone you share you SSH&#x2F;SFTP&#x2F;FTP pass with will have as much control&#x2F;access to and over the slot as you do.<br>
<br>
<strong>1:</strong> Recommended - Create limited and jailed users using this FAQ - <a href="https://www.feralhosting.com/faq/view?question=193">Installing a Proftpd daemon for extra accounts</a> then share these credentials. This way they will never have total access to your slot.<br>
<br>
<strong>2:</strong> Create them a public&#x2F;private key pair that you can easily revoke so you do not have to share you main password - <a href="https://www.feralhosting.com/faq/view?question=13">Public Key Authentication for password-less login</a>. This still give them the same level of access that you have, but keys are simple to revoke.<br>
<br>
Can I use FTPS (also known as FTP-ES, FTP-SSL) on my feral slot.<br>
<br>
Feral do not provide FTPS access as part of their set-up, only SFTP. You can however use this FAQ - <a href="https://www.feralhosting.com/faq/view?question=193">Installing an FTP daemon for extra accounts</a> to set-up FTPS with limited users inside jailed directories.<br>
<br>
<h2>Is there a test file for Feral?</h2><br>
Please see this article - <a href="https://www.feralhosting.com/faq/view?question=48">Testing the Speed of Your Server</a><br>
<br>
<h2>Deluge, how do I use plug-ins, RSS and or make torrents.</h2><br>
You will need to use the Thin client. Here is a FAQ on how to set up the thin client - <a href="https://www.feralhosting.com/faq/view?question=76">Deluge Daemon - Remote control with the local Thin client</a><br>
<br>
<h2>I have files with another service provider, can I bring them with me to Feral?</h2><br>
Yes, you can do this quite easily if your other provider has provided you with SSH access and rsync.<br>
<br>
1: <a href="https://www.feralhosting.com/manager/tickets/">Open a support ticket</a> and provide Staff with your SSH details for you old server and what files you want. They will then start the process of moving your files for you and keep you updated via the ticket.<br>
<br>
2: You can move these files yourself if using this guide: <a href="https://www.feralhosting.com/faq/view?question=117">Transferring data from slot to slot</a>. The guide describes using rysnc to move files from one Feral slot to another during an upgrade. This method is identical in moving files from a non Feral server to a Feral server. <br>
<br>
Related article: <a href="https://www.feralhosting.com/faq/view?question=122">Completing a data transfer</a><br>
<br>
<h2>Can I use public trackers with my Feral slot?</h2><br>
Feral supports and allows the use of public trackers. No need to ask or get permission.<br>
<br>
<h2>I want to upgrade or downgrade my slot what do I do?</h2><br>
To upgrade your slot please:<br>
<br>
<strong>(1)</strong> Purchase the slot from our website. <br>
<strong>(2)</strong> Wait until you receive the slot. <br>
<strong>(3)</strong> Then open a ticket requesting a data transfer (optional).<br>
<strong>(4)</strong> Request a refund on your current slot (optional).<br>
<br>
This is the official Feral upgrade procedure. Any upgrade or downgrade involves the purchasing of a new physical slot. There is no way to expand or decrease your current slot specifications.<br>
<br>
Open a ticket as soon as your purchased slot is allocated. This opens a dialogue between you and the staff and can deal with any issues that might be relevant, such as non payment of a slot and more. Staff are reasonable and friendly people, so don&#x27;t be afraid to talk to them via the ticket with your concerns. Also be fair to them, don&#x27;t leave things until the last minute.<br>
<br>
Related article: <a href="https://www.feralhosting.com/faq/view?question=122">Completing a data transfer</a><br>
Related article: <a href="https://www.feralhosting.com/faq/view?question=117">Using rsync to transfer files to a new slot</a><br>
Related article: <a href="https://www.feralhosting.com/faq/view?question=33">Slot Upgrades - Additional Disk Space or Speed Requirements</a><br>
Related article: <a href="https://www.feralhosting.com/faq/view?question=8">Late Payments</a><br>
<br>
<h2>Using SFTP</h2><br>
SFTP is the ideal and supported way to securely transfer data between the server and your home computer. SFTP is FTP over SSH. All Feral users have SSH access to their slots. Feral does not use or support FTPS for file transfer.<br>
<br>
Here are a list of Windows and Mac FTP&#x2F;SFTP clients:<br>
<br>
<strong>Windows Free Solutions:</strong><br>
<br>
<a href="http://winscp.net/eng/download.php">WinSCP client</a> Recommended - FTP&#x2F;SFTP&#x2F;keyfiles&#x2F;Custom Commands e.g. unrar&#x2F;Putty integration&#x2F;parallel downloads<br>
<a href="https://filezilla-project.org/download.php?type=client">Filezilla Client</a> FTP&#x2F;SFTP&#x2F;keyfiles&#x2F;parallel downloads<br>
<a href="http://www.bitkinex.com/download">Bitkinex Client</a> FTP&#x2F;SFTP&#x2F;keyfiles&#x2F;Putty integration&#x2F;parallel downloads&#x2F;Segmented downloads<br>
<br>
<strong>Mac Free Solutions:</strong><br>
<br>
<a href="https://filezilla-project.org/download.php?type=client">Filezilla Client</a> FTP&#x2F;SFTP&#x2F;keyfiles&#x2F;parallel downloads<br>
<br>
Related article: <a href="https://www.feralhosting.com/faq/view?question=27">WinSCP: Performing Common Tasks (Creating Torrents, Unrar&#x27;ing, Symlinks, etc)</a><br>
Related article: <a href="https://www.feralhosting.com/faq/view?question=187">FTP &#x2F; SFTP using Filezilla</a><br>
Related article: <a href="https://www.feralhosting.com/faq/view?question=193">Installing an FTP daemon for extra accounts</a><br>
Related article: <a href="https://www.feralhosting.com/faq/view?question=153">Automated Sync from SeedBox to Home</a><br>
<br>
<h2>Using FTP</h2><br>
FTP is a second method for transferring files if SFTP is not available or slow. We recommend using the <a href="http://filezilla-project.org/download.php?type=client">FileZilla client</a>. It runs on all Major platforms. If you require more downloading power, please use a <a href="http://en.wikipedia.org/wiki/Download_acceleration">multi-part</a> ftp client, like <a href="http://www.bitkinex.com/download">Bitkinex Client</a> . There is a <a href="http://www.globalscape.com/cuteftpmacpro/">Mac version</a> of CuteFTP as well.<br>
<br>
Related article: <a href="https://www.feralhosting.com/faq/view?question=28">What to Do If FTP Speeds Are Slow</a><br>
<br>
<h2>Using SSH</h2><br>
SSH is useful for complete control over your account and is used to help fix any problems. We recommend using the <a href="https://www.feralhosting.com/faq/view?question=12">KiTTY client</a> on Windows. On Macs, you can just use terminal.<br>
<br>
Related article: <a href="https://www.feralhosting.com/faq/view?question=12">SSH Guide - The Basics</a><br>
Related article: <a href="https://www.feralhosting.com/faq/view?question=37">SSH Tunnels Basic - PuTTy</a><br>
Related article: <a href="https://www.feralhosting.com/faq/view?question=13">Setting up Public Key Authentication for Password-less Login</a><br>
Related article: <a href="https://www.feralhosting.com/faq/view?question=217">SSH guide basics - Mac</a><br>
<br>
<h2>Using HTTP &#x2F; WWW</h2><br>
Alternatively, you can use your preferred browser or a download manager to download your files via HTTP.<br>
<br>
With the purchase of a slot you are given two unique WWW URLs for you to use:<br>
<br>
<code>username.servername.feralhosting.com</code> &lt; https has a cert mismatch issue due to the name format.<br>
<br>
<code>servername.feralhosting.com&#x2F;username</code> &lt; https has a valid and matching SSL certificate for Feral sub domains.<br>
<br>
These URLs represent the same location with two ways to reaching it. The files in one will be the same files in the other and vice versa.<br>
<br>
Related article: <a href="https://www.feralhosting.com/faq/view?question=20">Putting Your WWW Folder to Use</a><br>
Related article: <a href="https://www.feralhosting.com/faq/view?question=161">Forcing HTTPS</a><br>
Related article: <a href="https://www.feralhosting.com/faq/view?question=22">Password Protect your WWW</a><br>
<br>
<h2>Using extra domains &#x2F; Hosting my own domain</h2><br>
You also have the option of getting an extra domain. Please read this article for how to set up your custom domain - <a href="https://www.feralhosting.com/faq/view?question=52">Host a virtual host on your Feral slot</a>.<br>
<br>
You can host a free domain or a domain you already own.<br>
<br>
