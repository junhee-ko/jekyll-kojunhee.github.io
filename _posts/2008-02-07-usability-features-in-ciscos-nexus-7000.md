---
id: 95
title: 'Usability features in Cisco&#8217;s Nexus 7000'
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/2008/02/07/usability-features-in-ciscos-nexus-7000
permalink: /usability-features-in-ciscos-nexus-7000/
categories:
  - CISCO
  - DC3.0
  - FCOE
  - Fibre Channel Over Ethernet
  - Nexus 7000
  - NX-OS
  - vmware
tags:
  - blog
  - C
  - CISCO
  - communication
  - Data Center
  - DC3.0
  - DESIGN
  - enhancements
  - FCOE
  - HP
  - mars
  - mds
  - NDA
  - Nexus
  - Nexus 7000
  - NX-OS
  - Pic
  - Power
  - security
  - Technology
  - virtualization
---
<a href="http://blogs.cisco.com/datacenter/about.html#doug_gourlay" title="Douglas Gourlay" target="_blank">Douglas Gourlay</a>, Sr Director, Marketing and Product Management for Cisco&#8217;s Data Center Business Unit and writer of [Cisco&#8217;s Data Center Blog][1] commented on my celebrity sighting post (me and the nexus 7000). He asked two questions regarding my post about the Nexus 7000, and I feel that it best serves everyone to answer them here.

**What useability enhancements do you feel are the most beneficial? **

  1. A separate, IP enabled, Management Interface. This has been a long time coming. The out of band management interface is very similar to a Ilo card in the HP world. it is effectively a supercharged console server that happens to site on the backplane of the sup engine. I am sure whoever pushed this feature through is going to get flowers one day from a Tech who DIDN&#8217;T lock himself out because the management interface was effectively a separate system.
  2. Finally, a functionally USB Interface that I can transfer IOS (well, now NX-OS) images through. Everyone has a USB key nowadays, even my Grandmother has one, it will make life so much easier when I can have a 4 gig key with me that has most IOS / NX-OS  versions and my common configs and just pop them right in.
  3. The integrated Cabling system is CLEAN. I love that it forces you to reserve the appropriate space for cabling, and that there finally is the possibility to avoid the flying spaghetti train wreck we see so often in Data Centers.
  4. Front to back Cooling. The cooling design is well thought out. I liked the fact that it draws from directly above the front floor and exits rear top.. This should help out in raised floor data centers that have a large temperature gradient as you move to the top of the rack. It also negates problem of having multiple 6500 chassis side to side and having warm air blowing from the exhaust of one 6500 to the intake of another 6500.
  5. Fan Slots are now placed where it is IMPOSSIBLE to cover with cables. I would say 7 out of 10 times when I walk into a new customers Data Center I find that there are cables run directly over the fan tray with no slack. That is not a failure in design per say, but it could have been avoided. With the Nexus 7000 fan trays in the back the problem is solved before it is created.
  6. Power supplies are in the back . FAR away from the data cabling. It never fails that 20 amp circuits get uncomfortably close to copper cabling. By moving the power supplies to the back side of the chassis, this becomes a mute point and we remove any shadow of a doubt about EM interference causing craziness in our cabling.
  7. This one sounds really mundane, but a quick heads up grouping of status lights. In the past these were normally in a position where you had to squat down to see them, or they are obscured by cables. Buy putting them on the front of the cable tray assembly it ensures these will always be visible.

**What can we focus on now to make it a better platform?**

  1. One thing that worried me a little was the placement of the compact flash cards in the supervisory module. For those how haven&#8217;t it up close look at this <a href="http://www.cisco.com/en/US/products/ps9402/prod_view_selector.html" target="_blank">picture of the chassis </a> and look for the Grey cover midway up the sup modules in the center slots. Behind them are two flash cards, one for system partition extension, and one to dump log files into. Having these cards available are great features however I could see an operational process of security rotating out the log partitions, or more likely and engineer pulling the flash card after dumping some data for analysis to it, and then pulling the wrong card by accident. Having a simple strap (like the screw downs for power supply plugs) or something similar would go along way towards mitigating that risk.
  2. Continue with the spirit of innovation that has defined Cisco over the years. Cisco has consistently came out with or acquired and integrated many great products that directly address the needs of the market place into the product line (MARS, ASA, AireSpace, TelePresence, MDS, ACE, Etc) but frankly the last *GAME CHANGING *product that set the industry on its heals and forced everyone to rethink how we utilize technology to accelerate business as a whole was the acquisition of Selsius and the introduction of VOIP as an enterprise class product to the world. I remember having the hair stand up on my arms from the excitement of going up against Avaya and Nortel back then and fighting that uphill battle, educating customers and peers about this &#8220;new thing called VOIP and how CallManager (now Unified Communications Manager) is your ticket towards productivity. 
    When we talk about the Virtual DataCenter, I/O Virtualization (FCOE) and VFrame Automation it is not just another incremental improvement of existing technology. It is a paradigm shift, a leap ahead, a *GAME CHANGER*. I get the same chills that I did when VOIP was new because I know that those are technologies that will force us to rethink how we approach computing and data systems. These technologies are to the Data Center what IP telephony was to the PBX, and Cisco is the only company with technologies and engineering know how in all the verticals necessary to pull this off.</li> </ol>

 [1]: http://blogs.cisco.com/datacenter/ "http://blogs.cisco.com/datacenter/"