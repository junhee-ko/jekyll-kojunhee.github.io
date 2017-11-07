---
id: 727
title: Cisco Unified Computing System Quoting and Configuration with Netformx
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/?p=727
permalink: /cisco-unified-computing-system-quoting-and-configuration-with-netformx/
aktt_notify_twitter:
  - yes
aktt_tweeted:
  - 1
categories:
  - B-Series
  - CISCO
  - Cisco 2100 Fabric Extender
  - Cisco 6120XP
  - Cisco 6140XP
  - Cisco B Series Blades
  - Cisco Server Array Manager SAM
  - Cisco UCS B200
  - Cisco UCS B250
  - Cisco Unified Computing System
  - Cisco Unified Computing System Managerm UCSM
tags:
  - bom
  - CISCO
  - Cisco Unified Computing System
  - dynamic configuration tool
  - Netformx
  - ordering system
  - Server
  - UCS
  - Unified Computing
  - workflows
---
What I would like to share today is a video guide on how to properly create a Unified Computing System (UCS)  Bill of Materials (BOM), and how to route that BOM into the appropriate ordering system.

You may notice that I am using a tool called Netformx. You may ask &#8211; since this is a Cisco product, why aren&#8217;t we using the Dynamic Configuration Tool or the MultiLine Configurator? The answer that was given to me was that UCS requires a bottom up configuration. It requires that you start with the type and number of systems, and then work your way up to the amount of Chassis, FEX&#8217;s, links and Fabric Interconnects that are required. All of the workflows in Cisco&#8217;s existing tools require a top down approach. Until the new configuration workspace is released from Cisco, Netformx is your only option to quote any UCS product.

.

Thank you for taking the time to watch this walk through. If you found this helpful, please feel free to leave a comment or ping me on twitter.