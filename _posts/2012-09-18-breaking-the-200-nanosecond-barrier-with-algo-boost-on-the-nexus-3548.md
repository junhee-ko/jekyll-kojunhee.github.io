---
id: 1299
title: Breaking the 200 nanosecond barrier with Algo Boost on the Nexus 3548
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/?p=1299
permalink: /breaking-the-200-nanosecond-barrier-with-algo-boost-on-the-nexus-3548/
categories:
  - CISCO
  - Data Center
tags:
  - Algo Boost
  - algorythmic trading
  - CISCO
  - hpc
  - Nexus 3548
---
<!--?xml version="1.0" encoding="UTF-8" standalone="no"?-->

<span style="font-family: Arial;">&#8220;We have 600 silicon designers at Cisco, but are not religious about merchant silicon. There are many products at Cisco that utilize it. However as a company we must control our own destiny&#8221; &#8211; <span style="font-family: Arial;">Paul Perez, CTO of Cisco&#8217;s Server and Virtualization Technology Group (SAVTG</span></span>

There has been a lot of discussion in the past couple years regarding networking manufacturers using market silicon vs developing ASICs in house. While there are valid arguments on both sides of the table, Cisco just made a strong argument for the creation on custom ASICs and controlling their own destiny.

### Nexus 3548 &#8211; 190 nanosecond latency in a 48 port 10 gig switch

<img title="NEXUS 3548.jpg" src="http://www.colinmcnamara.com/wp-content/uploads/2012/09/NEXUS-35481.jpg" alt="NEXUS 3548" width="500" height="246" border="0" />

This argument comes to life with the Cisco Nexus 3548 low latency data center switch. Coming in a 1RU form factor and with 48 10 gig SFP+ ports it resembles  the nexus 5500 line, however the guts are packed with some shiny new bits that make trades execute faster then the competition and HPC clusters sing.

### **Performance Numbers &#8211; RFC2544 testing**

<img title="3548-algo-boost.jpg" src="http://www.colinmcnamara.com/wp-content/uploads/2012/09/3548-algo-boost1.jpg" alt="3548 algo boost" width="500" height="243" border="0" />

The punchline of Cisco&#8217;s statement is a 48 port switch that operates (in a non optimized mode) at 250 nanoseconds across all frame sizes. That is 653 nanoseconds faster then the closest 48 port low latency switch on the market, and 333 nanoseconds faster than the 24 port option. This is roughly 60% faster than the closest current competition in the market. All of these numbers are for the switch operating in normal (full function) mode. There is a second mode called &#8220;Warp&#8221; mode that focus&#8217;s the resources of the switch towards lowering latency down to 190 nanoseconds.

### Technology powering the Nexus 3548 &#8211; Algo Boost

<img title="algo-boost.jpg" src="http://www.colinmcnamara.com/wp-content/uploads/2012/09/algo-boost1.jpg" alt="Algo boost" width="500" height="265" border="0" />

The key technology behind the ASICs in the 3548 is Algo Boost. Algo Boost adds another dimension to HPC network design, which historically has been defined by latency and bandwidth. This new dimension, which can be critical to HPC system performance is buffer management. Not only does the Nexus 3548 have very large (18MB) buffers, but it also has intelligent buffer management features that allow for monitoring and reporting of utilization and more importantly buffer congestion across the switch, increasing application performance.

### **Summit it up**

Cisco is making many bets in the ASIC development space. The most recent bet with the Nexus 3548 allows Cisco to present an option to the market that is 60% faster then any of the current competition, and is likely to retain a speed advantage even against the upcoming Alta chipset from Intel. This combined with the proven performance of NX-OS should result in Cisco regaining a leadership position in the HPC and Algorithmic trading market.