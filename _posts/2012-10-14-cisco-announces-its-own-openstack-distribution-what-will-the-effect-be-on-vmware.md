---
id: 1348
title: 'Cisco announces it&#8217;s own OpenStack Distribution &#8211; What will the effect be on VMware?'
author: colinmcnamara
excerpt: There are many reasons for this rapid transformation from interesting project to cloud standard. In my belief the primary reason is that the major networking and systems hardware manufacturers have figured out that by supporting the development of OpenStack that now have a way to fight back against Amazon and EC2.
layout: post
guid: http://www.colinmcnamara.com/?p=1348
permalink: /cisco-announces-its-own-openstack-distribution-what-will-the-effect-be-on-vmware/
categories:
  - CISCO
  - OpenStack
tags:
  - openstack
  - quantum
  - vmware
---
<p style="text-align: center;">
  <strong>Cisco Releases their own Edition of OpenStack</strong>
</p>

 <img title="NewImage.png" src="http://www.colinmcnamara.com/wp-content/uploads/2012/10/NewImage1.png" alt="NewImage" width="500" height="143" border="0" />

Over the past year OpenStack has transformed  from an interesting Open Source project used by some large web service providers, to the emerging standard for on premise OpenSource cloud platform.

There are many reasons for this rapid transformation from interesting project to cloud standard. In my belief the primary reason is that the major networking and systems hardware manufacturers have figured out that by supporting the development of OpenStack that now have a way to fight back against Amazon and EC2.

<p style="text-align: center;">
  <strong>Why is Cisco releasing their own Distribution of OpenStack</strong>
</p>

<p style="text-align: left;">
  A couple weeks ago Paul Perez (CTO of Cisco&#8217;s Server and Virtualization Business Unit) was speaking to Cisco&#8217;s top Data Center partners and revealed that <em><strong>Cisco has saved 40% on licensing costs in their development environments by utilizing OpenStack</strong></em>.
</p>

<p style="text-align: left;">
  Cisco has realized dramatic cost savings already by utilizing OpenStack in places where they would have had to use VMware in the past. These places are extraordinarily large, and quite complex.
</p>

<p style="text-align: center;">
  <strong>What does this mean for the VMware relationship?</strong>
</p>

> <p style="text-align: left;">
>   &#8220;Will we compete against VMware as it relates to networking? Absolutely,&#8221; Chambers told CRN. &#8220;And when we compete, we don&#8217;t lose.&#8221;  &#8211; John Chambers, CEO Cisco Systems
> </p>

John Chambers made some strong statements in an interview with CRN last week about how Cisco will compete with VMware. It is not secret that tensions have been high ever since the Nicira acquisition, and they probably won&#8217;t relax in the short term.

The reality is however that Cisco and VMware still have much to gain in remaining strong partners. Taking Paul Perez&#8217;s statements as an example &#8211; while they saved 40% of licensing costs in development, 60% of those dollars were still spent on something like VMware.

The future of our customers data centers will most likely have multiple hypervisor stacks. Some of these stacks will highlight commercial platforms like VMware, Citrix and Hyper-V. While most likely development, Q&A and &#8220;Cloud&#8221; environments will feature OpenStack.

It makes complete sense for Cisco to maintain positive relationships with all of these software vendors since they are very likely to install right on top of Cisco&#8217;s UCS platform. And last time I checked, everyone at Cisco is quite happy every time a UCS ships out the door.

<p style="text-align: center;">
  <strong>Who should you watch &#8211;  Lew Tucker &#8211; VP and CTO of Cloud Computing for Cisco</strong>
</p>

<p style="text-align: left;">
  As the CTO of SAVG, Paul Perez may be the one who talks a lot about OpenStack as it relates to Cisco in the classic press and events. However the man behind the curtain that everyone should be paying attention to is Lew Tucker.
</p>

<p style="text-align: left;">
  <img title="NewImage.png" src="http://www.colinmcnamara.com/wp-content/uploads/2012/10/NewImage.png" alt="NewImage" width="498" height="331" border="0" />
</p>

Lew, a former CTO at Sun Microsystems has quietly assembled a powerhouse team at Cisco that has been writing functional code that allows OpenStack to closely leverage key Cisco networking technologies.

Not only has Lew and the team been writing great code, but they have also been taking both public and private leadership roles in the OpenStack foundation.

Case in point, one of the developers on Lew&#8217;s team was the one who pushed through my OpenStack Individual Contribution License, allowing me to submit my first piece of code (Storage QOS enhancement) to OpenStack.

<p style="text-align: center;">
  <strong>What should you do next?</strong>
</p>

Frankly, you should do what I have been doing for the better part of a year. You need to focus on becoming knowledgeable about OpenStack. The most dangerous thing I have seen over this past year of escalating excitement is people talking, influencing, and making decisions without the proper knowledge.

I recommend getting it running in your internal lab environments and possibly finding a small corner or production to run it in (only if that corner is appropriate). Figure out how to deploy it, manage it and extend it. There more you poke around, the better prepared you will be.

<p style="text-align: center;">
  <strong style="text-align: center;">Want to learn more?</strong>
</p>

[Come to My Session at OpenStack Summit &#8211; An Engineers Guide to Contributing to OpenStack][1]

[Cisco Edition of OpenStack ][2]

[Cisco Quantum Plugin for Folsom][3]

[Cisco OpenStack reference architecture on UCS C2XX ][4]

 [1]: http://openstacksummitfall2012.sched.org/event/61ec15daff51c67eaf3188b306a095c1?iframe=no&w=700&sidebar=no&bg=no#
 [2]: http://www.cisco.com/web/solutions/openstack/index.html
 [3]: http://docwiki.cisco.com/wiki/OpenStack:Quantum
 [4]: http://docwiki.cisco.com/wiki/OpenStack:Reference_Architectures:UCS_C2xx_M3