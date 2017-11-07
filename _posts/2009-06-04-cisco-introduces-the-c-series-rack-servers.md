---
id: 614
title: Cisco introduces the C-Series Rack Servers
author: colinmcnamara
excerpt: |
  Cisco announced the expansion of its server offering today with the inclusion of the C-Series 19" rack form factor servers. These servers will ship in the fall of the 2009. This announcement rounds out Cisco's server product line, allowing customers the to choose between a range of options including the B-series blade center form factor Unified Compute System and the C-Series 19" rack form factor servers.
layout: post
guid: http://www.colinmcnamara.com/?p=614
permalink: /cisco-introduces-the-c-series-rack-servers/
aktt_notify_twitter:
  - yes
aktt_tweeted:
  - 1
categories:
  - B-Series
tags:
  - B-Series
  - C-Series
  - CISCO
  - FCOE
  - Server
  - Technology
  - UCS
---
Cisco announced the expansion of its server offering today with the inclusion of the C-Series 19&#8243; rack form factor servers. These servers will ship in the fall of the 2009. This announcement rounds out Cisco&#8217;s server product line, allowing customers the to choose between a range of options including the B-series blade center form factor Unified Compute System and the C-Series 19&#8243; rack form factor servers.

[singlepic id=92 w=420h=340 float=]

<span style="font-size: medium;"><strong>The Server Landscape</strong></span>

If you take a look at most enterprise and commercial customers data centers, you will notice a trend of larger fixed workloads running on two rack unit servers (very commonly HP&#8217;s DL380), and newer virtualization workloads consolidated onto blade center form factor servers (commonly c7000 class blade systems, and soon Cisco UCS B-Series blades).

However when you go to a remote site where the compute needs are much smaller, you tend to see a few 1 and 2 rack unit system (DL360 or DL380). Why is this? There are a couple reasons, but the most pressing reason is cost. In a blade system, even if you virtualize there is a tipping point where it costs less to install blades and use centralized storage then it costs to use rack form factor servers with local storage. I find that tipping point is generally between five and 8 blades.

If you are a small remote site, or small to medium size business you may not have the compute needs (especially with virtualization) to push you over that tipping point into the blade center form factor. In that case, a few rack optimized servers provide the optimal return on investment for that smaller site.

<span style="font-size: medium;"><strong>Taking a closer look at Cisco&#8217;s C-Series Servers</strong></span>

<span style="font-size: medium;">Cisco UCS C 200 M1 &#8211;</span>

<p style="padding-left: 30px;">
  Effectively this is a clone of the B-200 M1 blade in the B series UCS chassis with the addition of two PCIe slots and two more SFF SAS/SATA drives..
</p>

<p style="padding-left: 30px;">
  The C 200 M1 is a 1 rack unit form factor server (pizza box). It supports a dual port 10 gigabit converged network adapter. two Xeon 5500 series processors, four small form factor SAS drives, 12 dimms for a total of 96 Gigabytes of memory.
</p>

<span style="font-size: medium;">Cisco UCS C 210 M1 &#8211;</span>

<p style="padding-left: 30px;">
  The C 210 is a 2 rack unit form factor server, with the same CPU and memory architecture as the C 200. What has been added is 3 additional PCIe slots (for a total of 5). There is also support for up to 16 SFF SAS/SATA drives.
</p>

<p style="padding-left: 30px;">
  Out of all the C-Series servers I think this will be the most popular. The extra local disk and PCIe slots will be extremely tempting. For example if this server was populated with 750 Gig SFF SATA drives and augmented with some Fusion-io cards you could have 6 Terabytes of raw disk inside this server. An end user could install Open Filer or iSCSI Enterprise Target and have a pretty respectable NAS head. The other possibility is someone will notice that the Palo adapter can be used as a FCoE target, and use a couple of these as backends for FC storage. (This FC target functionality is mentioned in Silvano Gai&#8217;s book).
</p>

<span style="font-size: medium;">Cisco UCS C 250 M1 &#8211;</span>

<p style="padding-left: 30px;">
  Effectively this is a clone of the B-250 M1 blade in the B series UCS chassis with the addition of five PCIe slots and eight SFF SAS/SATA drives.
</p>

<p style="padding-left: 30px;">
  The C 250 M1 is a 2 rack unit form factor server. It supports a dual port 10 gigabit converged network adapters. two Xeon 5500 series processors, eight small form factor SAS/SATA drives, and 48 dimms for a total of 384 Gigabytes of memory.
</p>

<p style="padding-left: 30px;">
  This server utilizes the same catalina chipset for memory expansion that it&#8217;s cousing the B-250 M1 utilizes.  The ability to aggregate low cost memory plus the PCIe slots to insert solid state I/O acceleration make this a prime candidate to business intelligence / data warehousing workloads as well as Electronic Design Automation.
</p>

<span style="font-size: medium;"><strong>When can I buy these?</strong></span>

Putting any new product line into production is a monumental effort that many of us take for granted. My gut feel is that Cisco will focus on satisfying demand for the B Series Unified Compute System first, and once manufacturing has hit their stride with the UCS Cisco will start production of the C-Series. In short, I&#8217;m  expecting the first C-Series servers to roll off the line at the end of 2009, and  meaningful availability of the C-Series in the first quarter of calendar year 2010.

<span style="font-size: medium;"><strong>How do I integrate these into my network?</strong></span>

This is a question that is bound to come up. Cisco&#8217;s C-Series servers can integrate directly into your 10 Gig enabled network. Now, to get the best bang for your buck, you should ideally connect these into a pair of Nexus 5000&#8217;s to converge your storage and data networks into simple 10 Gig Data Center Ethernet links.

You may however have site without 10 gig enabled switches. In that case, there are multiple PCIe slots in these servers so we should be free to utilize 10/100/1000 adapters. Then when these sites have the need to move to 10 Gig, the server will be capable of supporting that level of connectivity.

<span style="font-size: medium;"><strong>My Perspective </strong></span>

At the end of the day, Cisco is now a server manufacture. Just like the HP and IBM, Cisco has to provide platforms that meet customer needs. While the B-Series Unified Computing System is an outstanding platform, it shares similar entry costs that other blade systems have (the need to purchase chassis and interconnects first) which can server as a barrier for smaller server installations. By introducing a 19&#8243; rack form factor line of servers that share many of the I/O and memory benefits of the B-Series servers, Cisco is directly answering the needs it&#8217;s customer base by providing a form factor that can scale across all size of customer installation.

<span style="font-size: medium;"><strong>Want to learn more?</strong></span>  
<a href="http://www.colinmcnamara.com/ciscos-unified-computing-system-its-not-just-a-blade-center" target="_blank"><br /> Cisco Unified Computing System Overview</a> &#8211; colinmcnamara.com  
<a href="http://www.cisco.com/en/US/prod/ps10265/rack_mount_promo.html" target="_blank"><br /> UCS C-Series Rack Servers: A New Path to Unified Computing</a> &#8211; Cisco.com

<a href="http://www.datacenterknowledge.com/archives/2009/06/03/cisco-unveils-rackmount-servers-for-ucs/" target="_blank">Cisco unveils rackmount servers for UCS </a>&#8211; datacenterknowledge.com