---
id: 79
title: 'Why GoDaddy Linux Virtual Dedicated Hosting Sucks &#038; How to Fix It'
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/2008/02/03/why-godaddy-linux-virtual-dedicated-hosting-sucks-how-to-fix-it
permalink: /why-godaddy-linux-virtual-dedicated-hosting-sucks-how-to-fix-it/
aktt_notify_twitter:
  - yes
categories:
  - CCIE
  - GoDaddy
  - howto
  - linux
  - scripting
  - Technology
tags:
  - C
  - Colin
  - connecting
  - error
  - GoDaddy
  - godaddy help
  - hosting
  - Instances
  - john
  - linux
  - NDA
  - Network
  - Pic
  - Provider
  - simple control panel
  - turbopanel
  - virtual private servers
---
**<span style="font-size: 12pt"><span style="font-size: 12pt"> Ok, put the guns away. Linux rocks&#8230; My beef is with GoDaddy and how they are hurting the average Linux virtual dedicated server user.</span></span>**

GoDaddy, one of the nations largest registrars and hosting providers is distributing bloated and possibly insecure code that will cause the average user to more then double their hosting costs. In the pages below you will learn exactly what GoDaddy is doing to your server, how their support staff will try to upsell you, and the steps you need to take to ensure proper operation of your Virtual Dedicated Server.

<span style="font-size: 14pt">Background</span>

One of my new years resolutions this year was to consolidate hosting accounts into one virtual server (hosted). I had my domains, and my old hosting with Godaddy already so it was a no brainer to try out one of GoDaddys VDS (Virtual Dedicated Servers).

I went with their 29.99 a month package, with Centos5, unlimited domains, 10Gb disk, and 256 MB of memory. This should be perfectly fine for hosting a couple MySql driven sites, and a couple gallery instances. Let me emphasise this is only handling 4 active domains, two of which only have static HTML.

Provisioning was a breeze, from order to shell account only took 4 hours. I was provided with shell access, pre-configured yum repositories, and this web control panel &#8211; simple control panel, or TurboPanel (seems to have two different names). I was able to pop into GoDaddy&#8217;s control panel interface with a direct link from their server manager console, and was setting up domains in no time. (Let me throw this caveat out though, don&#8217;t buy this product for your mom&#8217;s hosting&#8230;. the documentation is horrible, and by horrible I mean non-existant).

So I get my server all set up a couple weeks ago, transfer all my files from [2 Cups Solutions][1] and set up my new [www.colinmcnamara.com][2] site. Things go just fine, I changed over to wordpress as a CMS and am totally thrilled. My applications and email are working perfectly. Plus, I have a shell account at GoDaddy which is a very handy thing to have as a network engineer. Things are going so well, that I give my buddy Rick a Christmas present and get [ricksdavis.com][3] and <a href="http://www.el-cinco.net" target="_blank">el-cinco.net</a> for him, and host it on my GoDaddy VDS.I go ahead and purchase the domain through godaddy&#8217;s domain manager. This is obviously GoDaddy&#8217;s core competency, and goes flawlessly as usual. Next step, I go into the Turbo Panel web interface. Let me give you a little background on TurboPanel. This is the &#8220;free&#8221; equivalent &#8220;to plesk or cpanel. It is actually ok for automating your domain provisioning, though if you are a normal skill level user, I would recommend paying the extra 9.99 a month for Cpanel.

<span style="font-size: 14pt">Server Error</span>

I open up my TurboPanel interface and go to provision ricksdavis.com into the domain manager. It comes back with the least descriptive error I have ever received.

**Server Error  
We are sorry, the system has encountered an error while processing your request.**

**Home**

**If you continue to receive this error, please contact your system administrator.**

**Your URL: /domain/edit.do**

**Error details:**

**CommandFailedException: Unable to get min/max uids  
at c.g.t.f.systems.user.LinuxUserSubsystem.loadUids:825  
at c.g.t.f.systems.user.LinuxUserSubsystem.getMinUid:780  
at c.g.t.f.systems.user.LinuxUserSubsystem.loadUserInfo:670  
at c.g.t.f.systems.user.LinuxUserSubsystem.getUserInfo:646  
at c.g.t.w.actions.domain.ActionDomainEdit.process:84  
at c.g.t.w.actions.AbstractSpringAction.execute:118  
&#8230;  
at c.g.t.w.filters.AuthorizedResourceFilter.doFilter:38  
&#8230;  
at c.g.t.w.filters.RequestPopulationFilter.doFilter:117  
&#8230;  
**

** **

This is the most descriptive error ever right? it tells you what is wrong, has a link to the support system, and gives you actionable information&#8230;. I would say a resounding NO. This is a classic example of why friends don&#8217;t let friends program in Java. When I got this error last night, I was scratching my head. As an engineer, the first thing I will look at is the last change to the system. Coincidentally I had installed awstats two nights before, and looking at my change logs, I saw that I had upgraded my perl version. So, with no fast response to the support email from GoDaddy I chose to put in a server re provision request (fully automated) and restore from my backups. That process took about an hour, but afterwards I was back online with no errors. Eureka! I found it (I thought). I provisioned Rick&#8217;s domain, wordpress, gallery2 etc and then went to bed.

<span style="font-size: 14pt">GoDaddy Support Response </span>

Fast forward to this morning, and I finally recieve an email reply from godaddy support. The email is pasted below-

(I have replaced the agents name with John Doe. Tech support is a hard job and I see no reason to highlight him specifically)

<table border="0" cellspacing="1" cellpadding="2" width="100%">
  <tr>
    <td bgcolor="#99cc99">
      <strong>Support Staff Response</strong>
    </td>
  </tr>
  
  <tr>
    <td>
      Dear Sir or Madam,Thank you for contacting Server Support.Your system may not have the resources needed to accommodate the processes running when you observed this issue. To resolve this issue, you can attempt to restart Java and Simple Control Panel with the following commands through SSH as root;/etc/init.d/tomcat55 restart<br /> /etc/init.d/turbopanel restartIt may be necessary to remove unneeded processes, stop unused processes, or limit the currently running processes to not over utilize the server&#8217;s resources. To remedy this issue long-term, you could either setup a server with 512mb RAM, or upgrade to a Dedicated server.In order to properly support this issue we will need to reveal account specific information. Before we can give out any information on the account, we will need to verify the last 4 digits of a credit card, PayPal Billing Agreement/Account Number, or Support PIN on the account. Payment information on the account can be found under &#8220;Credit Card & Payment Info&#8221; from the &#8220;Customer Info & More&#8221; dropdown. We appreciate your understanding in this matter.Please contact us if you have any further issues,John Doe<br /> Server Support<br /> Hosting Operations
    </td>
  </tr>
</table>

Before re-provisioning the server, I went ahead and tried the old three finger salute (reboot) the error still existed. So even if this email would have came to me on time, it would not have helped.

But that is besides the point. lets dig into the solution

The agent suggested the following fix &#8211;

Restart tomcat &#8211; which I was NOT using for any of my web applications (not an ejb guy)

/etc/init.d/tomcat55 restart

Restart TurboPanel (or simple control panel now &#8211; they haven&#8217;t updated their init scripts)

/etc/init.d/turbopanel restart

<span style="font-size: 14pt">GoDaddy tried to upsell me, instead of fixing their code</span>

He gives the standard, run less stuff on your server speech (remember, I only have 4 domains on this server)

Now here is the kicker &#8211; **To remedy this issue long-term, you could either setup a server with 512mb RAM, or upgrade to a Dedicated server.**

What the heck is with that? I should not need an upgrade with only 4 domains on a server. Especially when in the setup the default Cpanel implies support of 30 domains. Is this Tech Support or a Sales Call?

But, since my server was working fine I don&#8217;t pay much attention to the email and move on with my life.

Fast forward an hour, and I am show Rick how to access all the features of his new site, and I figure that I need to change an email account on his domain to forward to his old account. Fine, this should take two minutes. I log onto the TurboPanel interface to put the email forward in.. and there it, a big useless error screen. What the heck is with that?

So this time I actually read the email, and try the fix. Results = nothing. GoDaddy offers shell access so I log in, run top and filter for %memory used. Low and behold, there is only 8142 bytes of memory free, and a Java process owned by root is using 300Mb of virtual memory, and 132Mb of real memory, and Tomcat is using 115Mb of virtual memory and 86Mb of real memory.

Let me translate this into English &#8211; **Godaddy&#8217;s control panel application was using 218 Megabytes of the 256 Megabytes of memory I had purchased. That left me with 34 Megabytes of memory** . Let me clarify this, I had paid for a virtual server with 256Mb of ram, up to 1000Mb bursted (which I think is their code for swap). I am only running 4 domains on this server, and two pop3 email servers. This should not be a problem.So what is the cause of the problem? I can sum it up, crappy Java programming. Someone decided to write this program in Java (probably easier to outsource) instead of optimising it to run on lean systems. Their code effectively takes up all the available memory. And on top of that, they are are running a webserver process as root&#8230; yes as root. It is like asking for your server to get hacked.

<span style="font-size: 18pt"><strong>Now, that I am done ranting, let me highlight how to fix this problem.</strong></span>

<span style="font-size: 14pt">If you are on Windows use the following procedure to get shell access to your GoDaddy VDS &#8211;<br /> </span>

  * you will want to download a ssh client called putty &#8211; <a title="putty download" href="http://the.earth.li/~sgtatham/putty/latest/x86/putty.exe" target="_blank">Download Here</a>
  * Copy this file to your desktop, double click putty.exe , and you should see something like this &#8211;

[singlepic id=73 w=320 h=240 float=]

  * In the host name field I have www.*yourdomain*.com . replace *yourdomain* with your domain name.
  * Click on the open button on the bottom right, and a shell should pop up, along with a warning that looks like this (you can click OK to the warning)

[singlepic id=74 w=320 h=240 float=]

  * Now skip past the linux section

<span style="font-size: 14pt">If you are running Linux or Unix start here &#8211;</span>

  * Open up a command line terminal
  * ssh using your godaddy simple control panel username example &#8211;

ssh your-godaddy-control-panel-username@www.yourdomain.com

  * If this is your first time connecting to this server, you will be prompted to accept an unkown ssh key into known_hosts, choose yes to accept

<span style="font-size: 14pt">Both Windows, Linux and Unix Continue Here &#8211; </span>

  * Enter your the password you use to access your GoDaddy Simple Control Panel Interface
  * You will be presented with what looks like a DOS window, this is called a secure shell terminal. Type in the username you use to access your Godaddy Simple Control Panel and then hit enter

[singlepic id=76 w=320 h=240 float=]

  * Now type in the password that you use to access your Simple Control Panel Interface and hit enter

[singlepic id=75 w=320 h=240 float=]

  * Congratulations, if you see the window below you are now shelled into your virtual dedicated server.

[singlepic id=72 w=320 h=240 float=]

<span style="font-size: 14pt">Change to the Root user</span>

  * Now that you are shelled into a Linux device you need to escalate your privileges to get administrator level access. In the Unix world this user is known as Root. You can change to this user, and get full system privileges by using the following command.

su &#8211; root

  * You will be presented with a password prompt, enter in the same password that you have used to log into your Simple Control Panel Interface
  * You are now root, be careful with what command you enter under this user, as you can do some damage if you are careless

<span style="font-size: 14pt">Clean out your servers memory</span>

  * Most recent Redhat direvatives (including Centos) utilize a tool called yum to add and remove packages. This is also true with your linux servers at GoDaddy.
  * you need to install a tool called memhog, it is part of a package called numactl that is normally used to assign specific process&#8217;s to specific cpu&#8217;s in a multi-core system. We will be using it today to fix GoDaddy&#8217;s memory hogging application

yum install numactl

  * choose yes to all the prompts, and numactl will automatically be downloaded and installed on your server

<span style="font-size: 14pt">Stop GoDaddy Simple Control Panel, and Tomcat, and tell them not to start automatically when your server restarts. </span>

  * Tomcat is a special type of webserver for Java based applications. Godaddy uses it to run their control panel interface. 99.99999 percent of users will not need to use Tomcat. If you do need to use Tomcat then you are a technical user and will know what to do.
  * In Linux, server applications are called daemons. The are executed by init scripts. We will use these scripts to turn off these server applications
  * Turn off the TurboPanel daemon ( this is the process that runs your simple control panel web interface

/etc/init.d/turbopanel stop

  * Next we need to turn off Tomcat

/etc/init.d/tomcat55 stop

  * Now that we have these services turned off, we need to make sure that they don&#8217;t come back when we reboot the server. We can do this by using the chkconfig command.
  * Stop the Simple Control Panel Interface from starting automatically by executing the following command

chkconfig turbopanel off

  * Stop the Tomcat server from starting automatically by executing the following command

chkconfig tomcat55 off

<span style="font-size: 14pt">Clean the mess GoDaddy made of your servers memory</span>

  * A couple steps back we installed numactl. The executable we wanted out of this package is memhog. Issue the following command to take your memory back. This command will overwrite 200 megabytes of your memory, allowing the rest of your applications to get access to that memory.

memhog 200m

  * This will Clear out the memory that GoDaddy&#8217;s application took over, and allow the rest of your daemons to run fine.

<span style="font-size: 14pt">Great, my server is running better now. But I want to use my Simple Control Panel Interface. How do I do that?</span>

  * Easy, all you need to do is temporarily start the turbopanel daemon. When you are done making changes, you can turn it off again

/etc/init.d/tomcat55 start

/etc/init.d/turbopanel start

  * When you are done, don&#8217;t forget to turn it off

/etc/init.d/turbopanel stop

/etc/init.d/tomcat55 stop

<span style="font-size: x-large;"><strong>*** UPDATE *** </strong></span><span style="font-size: x-large;"><strong>*** UPDATE ***</strong></span>

I managed to stay with Godaddy and use their Virtual Dedicated Servers for 12 months. However I have moved to a new hosting provider (<a title="rimuhosting " href="http://rimuhosting.com/?r=6053414aa51e6c7a2d97931a7cf85e88" target="_blank">rimuhosting)</a> in the spring of 2009. My last straw with GoDaddy occurred when I noticed that even with my memory utilization under control my applications were performing poorly. I shelled into verify and found that the virtual disk I/O was severly limited.

<span style="font-size: large;"><strong>Performance issues &#8211; </strong></span>

Simple command to determine directory size on GoDaddy VPS

[root@ip-72-167-15-128 home]# time du -hs  
1.3G    .  
real    0m49.013s  
user    0m0.011s  
sys    0m0.062s

Simple command to determine directory size on Rimuhosting VPS  
[root@colinmcnamara home]# time du -hs  
1.3G    .  
real    0m0.343s  
user    0m0.050s  
sys    0m0.290s

<span style="font-size: medium;"><strong>Translated into english, it took 49 seconds to execute a simple command on my GoDaddy server, and it too 0.34 seconds (under 1 second) to execute the same command on my virtual server at <a href="http://rimuhosting.com/?r=6053414aa51e6c7a2d97931a7cf85e88" target="_blank">Rimuhosting</a>.</strong></span>

On top of that, I was paying $32 dollars a month to GoDaddy for a server with 256 megs of ram as well as a FTP backup account. When I created my short list of hosts, I noticed that I was not getting the best deal by staying with GoDaddy.

<span style="font-size: medium;"><strong>Pricing at <a href="http://rimuhosting.com/?r=6053414aa51e6c7a2d97931a7cf85e88" target="_blank">Rimuhosting</a></strong></span>

  * <a title="Rimuhosting VDS" href="http://rimuhosting.com/vps-servers?r=6053414aa51e6c7a2d97931a7cf85e88" target="_blank">Virtual Dedicated Server 190 Megabytes RAM &#8211; $19.95</a>
  * <a title="Rimuhosting VDS" href="http://rimuhosting.com/vps-servers?r=6053414aa51e6c7a2d97931a7cf85e88" target="_blank">Virtual Dedicated Server 400 Megabytes RAM &#8211; $29.95</a>
  * <a title="Rimuhosting VDS" href="http://rimuhosting.com/vps-servers?r=6053414aa51e6c7a2d97931a7cf85e88" target="_blank">Virtual Dedicated Server 900 Megabytes RAM &#8211; $39.95</a>
  * <a title="Rimuhosting VDS" href="http://rimuhosting.com/vps-servers?r=6053414aa51e6c7a2d97931a7cf85e88" target="_blank">Virtual Dedicated Server 1150+ Megabytes RAM &#8211; $49.95</a>

<span style="font-size: small;">One thing you may notice, is that for the same price as the base GoDaddy VDS ($29.95) you get 400 Megabytes of RAM instead of 256. (and they won&#8217;t put on a memory sucking turbopanel app) On top of that, things that I had to pay extra for at GoDaddy such as backup space, backup mail relays, and DNS service came bundled for free. </span>

<span style="font-size: small;">I made the choice to move to Rimuhosting, and the service has been superior to GoDaddy in every single way. If you get sick of GoDaddy like I did, <a title="Rimuhosting" href="http://rimuhosting.com/?r=6053414aa51e6c7a2d97931a7cf85e88" target="_blank">you might want to check Rimuhosting out,</a> I think you&#8217;ll like them.</span>

 [1]: http://www.2cups.com
 [2]: http://www.colinmcnamara.com
 [3]: http://www.ricksdavis.com