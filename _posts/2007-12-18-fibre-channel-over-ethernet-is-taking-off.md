---
id: 55
title: Fibre Channel over Ethernet is taking off
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/2007/12/18/fibre-channel-over-ethernet-is-taking-off/
permalink: /fibre-channel-over-ethernet-is-taking-off/
blogger_blog:
  - colinmcnamara.blogspot.com
blogger_author:
  - Colin McNamara
blogger_permalink:
  - /2007/12/fibre-channel-over-ethernet-is-taking.html
categories:
  - CCIE Storage
  - cisco router eem email scripting ccie
  - FCOE
  - Fibre Channel Over Ethernet
  - Ie
tags:
  - blog
  - C
  - CCIE
  - CISCO
  - Colin
  - FCOE
  - Fibre Channel
  - Network
  - storage
  - Technology
---
Intel released open source drivers based on their current ISCSI driver implementation for Fibre Channel Over Ethernet (FCOE) today. For those that aren&#8217;t up to speed on FCOE, it is effectively ISCSI lite. When I say lite, I mean ISCSI without the layer 3 overhead. This will allow FCOE to leverage lower cost Ethernet transport (though most likely will be implemented using 1 and 10 gig interfaces.

This tactic address one key failing of ISCSI. Specifically an ISCSI interface running at 400 megabit will take 16% of a 3 ghz 64 bit cpu while using a software initiator or target. This can create some interesting issues where you don&#8217;t want to have them. By removing the layer3 information, and transposing fibre channel commands over the Ethernet transport a major cpu hit is avoided.

My gut feel is that this technology will follow a similar track as ISCSI did. ISCSI had a very low adoption in the first 3 years. Storage guys are naturally timid, as there are stiff consequences for failure, but eventually engineers warmed up to ISCSI and started deploying it where it was most appropriate, in lower bandwidth utilization hosts. FCOE will follow this same path, however this time we won&#8217;t have to fight the FUD of storage of a network transport. What is in FCOE&#8217;s favor is that as a protocol it is optimized for the general ISCSI setup of flat layer two transport between target and initiator.

That all being said, we are going to have to see some product releases from Cisco and Intel for FCOE to really take off. If we don&#8217;t, then FCOE will fall down the same hole that ATA over Ethernet disappeared down.

Colin McNamara  
CCIE #18233 (Storage Networking)  
[2 Cups Solutions][1]  
&#8220;The difficult we do immediately, the impossible just takes a little longer&#8221;

References &#8211;

[Intel Project Page][2]

<p class="blogger-post-footer">
  Colin McNamara<br /> CCIE #18233<br /> http://www.2cups.com<br /> &#8220;The difficult we do immediately, the impossible just takes a little longer.&#8221;
</p>

 [1]: http://www.2cups.com
 [2]: http://open-fcoe.org/