---
id: 7
title: Redhat AS3.3 and VMware ESX network issues
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/2005/06/27/redhat-as33-and-vmware-esx-network-issues/
permalink: /redhat-as33-and-vmware-esx-network-issues/
blogger_blog:
  - colinmcnamara.blogspot.com
blogger_author:
  - Colin McNamara
blogger_permalink:
  - /2005/06/redhat-as33-and-vmware-esx-network.html
categories:
  - Technology
  - vmware
tags:
  - blog
  - C
  - CCIE
  - Colin
  - funny
  - linux
  - Network
  - san
  - switch
  - vmware
---
OK, normally I can say nothing bad about VMware. However today I can definately say that I have gone past annoyed. Let me set the mood for you.  
At work we have a pretty decent VMware envioronment. We have an IBM Blade Center, Gig switches, hooked to a Netapp San. All and all pretty bitchen. Once of the things we run in VMware is our M$ Exchange 2003 staging envioronment, along with a working copy of Active Directory. Needless to say, this has to be seggregated from our production copy, or all sorts of hell breaks loose.

Now this system work pretty good, except when we have to do usability testing. Its just not the same on a XP image, as it is from your laptop, on wireless, at home.. etc etc. So we decide we need some sort of VPN solution into our Exchange staging environment. After not alot of thought, I decide to set up a linux PPTP server. Its a protocol that pretty much everybody can use, pretty lightweight, and free ;).

I have set these boxes up before, and its not terribly hard. Until I had to do it on VMware. Let me set the stage for you &#8211; Redhat AS 3.3 / VMware Esx server / VMware tools installed / 1 nic . One NIC generally isn&#8217;t best for a VPN server, so I used Virtual Center to deploy a 2nd NIC to my PPTP box.  
For anyone reasonably familiar with Redhat or Manadrake, we are used to installing well known hardware and seeing Kudzu add it on boot. Not this time. I rebooted, Kudzu came.. Kudzu went. I ran Kudzu manually no dice.

I know I know, auto anything never works&#8230; So I moved on to manually defining this network adapter. The first thing to check &#8211; is it actually plugged in. LSPCI reports the adapter as plugged in, and recognises it as a pcnet32 adapter. Normally I would take this as a positive sign, but not today. I issue IFCONFIG -a , network adapter is still not found. I was definately feeling a bit frustrated at this point. To be sure it wasn&#8217;t me, I bugged a friend and a co-worker (remind you of a game show?). Anson, who runs the VMware enviornment tried removing VMware tools, adding them&#8230;. still no dice. Shad tried to help through Yahoo, although to no avail.

By this time, I am frustrated, feeling like a moron, and ready for a break.  
I went to get lunch from the Cafe, and settled down to eat at my desk.  
Funny thing, how when you aren&#8217;t thinking about a problem is when you normally think of the solution. Let me give you a little background. Earlier when we were troubleshooting this problem, I googled this usenet post &#8211;  
<http://content.ix2.net/arc/t-4236.html> . This fellow describes his headaches with debian, in which he had a very similar problem.

His problem, along with mine was that the proper modules werent loading for his network devices. He had tried, along with me to add the module listing to /etc/modules.conf. The one thing however that I hadn&#8217;t tried was manually loading pcnet32 using modprobe.

needless to say, modprobe pcnet32 now sits in my rc.local file. Its lame, but it works.

&#8211;Colin  
[Copyright ©2008 | Colin McNamara | CCIE 18233 | All Rights Reserved&#8221;][1]

<p class="blogger-post-footer">
  Colin McNamara<br /> CCIE #18233<br /> http://www.2cups.com<br /> &#8220;The difficult we do immediately, the impossible just takes a little longer.&#8221;
</p>

 [1]: http://www.colinmcnamara.com "Copyright ©2008 | Colin McNamara | CCIE 18233 | All Rights Reserved"