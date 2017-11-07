---
id: 424
title: 'Simplifying your Data Center with Cisco&#8217;s Nexus 2000 Fabric Extender (FEX)'
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/?p=424
permalink: /simplifying-your-data-center-with-ciscos-nexus-2000-fabric-extender-fex/
aktt_notify_twitter:
  - yes
aktt_tweeted:
  - 1
categories:
  - CISCO
  - nexus 1000v
  - Nexus 2000
  - Nexus 5000
  - Nexus 7000
  - NX-OS
  - Unified Computing
tags:
  - CISCO
  - Fabric Extender
  - FEX
  - Nexus 2000
---
The Nexus 2000 Fabric Extender is Cisco&#8217;s newest addition to the Nexus line of Data Center switching products. In this case, even though it is an addition to the Nexus line, the 2000 is not a switch itself. The Nexus 2000 is what is known as  a Fabric Extender, which works in conjunction with the Nexus 5000 series of Data Center switches.

<span style="font-size: medium;"><strong>What is a Fabric Extender?</strong></span>

If you think of a large switching chassis such as a Catalyst 6500 or Nexus 7000 you have the notion of a Supervisory module, a switching fabric forming the backplane, and line cards connected on the back into the fabric, and connecting to servers and other networking devices in the front. In the case of these switching chassis all of the items we just talked about are connected on the inside of the same physical box. Now suppose we took each of those components, the Sup, Fabric, and Line Card and installed them in different parts of your data center. The Sup module in this case would be a Nexus 5020 or Nexus 5010. The fabric would be four 10 Gig port bundles from the Nexus to the Fabric Extender, and the line cards themselves would be replaced by the Nexus 2000 Fabric Extender.

[singlepic id=71 w=500 h=500 float=]

<span style="font-size: medium;"><strong>Why use a Nexus Fabric Extension in your Data Center designs?</strong></span>

<span style="font-size: medium;"><span style="font-size: small;">1. Simplify network management &#8211; By moving from individualy managed standalone edge switches to an extended fabric you minimize the amount of devices in your datacenter that you have to manage. Say you have 10 racks full of pizza box servers, (That makes 42 servers per rack) you may throw 3750&#8217;s or 4948&#8217;s top of rack to provide connectivity. In this case your access layer would consist of at minimum 10 unique devices to manage, upgrade, etc. in your server access layer. If instead you put a Fabric Extender at the top of each rack, you still get 48 ports of coppert gigabit ethernet, but logically you would only have 1 device to manage.</span></span>

<span style="font-size: medium;"><span style="font-size: small;">2. Simplify your network topology &#8211; In the scenarios mentioned above with classic switching, you would have to manage a spanning tree topology accross your entire access layer. Half of your uplinks will be blocked by spanning tree so your network does not loop. This is a perfectly valid topology, but it does leave you open to the pains of spanning tree in your data center Now replace these switches with a Nexus 2000 Fabric Extender. Instead of spanning tree to integrating individual switches, you now how a very simple U topology forming your edge.</span></span>

<span style="font-size: medium;"><span style="font-size: small;">3. Lower your costs for Data Center class switching &#8211; Before the Nexus 2000 if you wanted to properly deploy a Data Center access layer, you either had to do buy 6748 blade on a 6500, a 48 port gig blade on a Nexus 7k (</span></span><span class="content">M148GT) </span><span style="font-size: medium;"><span style="font-size: small;">, ora 3750 or 4948 switch. These all are not the cheapest switches and blades, but they provide each gig switch port with the proper buffers and throughput that are needed for true Data Center applications. Now if we chose to use the Nexus 2000 Fabric Extender in conjunction with the Nexus 5000 we can provide Data Center class 1 Gig Ethernet services at roughly half the cost of using the older switches.</span></span>

<span style="font-size: medium;"><span style="font-size: small;">4. Integrate 10 gig and 1 Gig services in a clean way &#8211; I have seen many many clients try to cleanly integrate 10 Gig services (normally from blade centers w/ ESX clusters) into an existing 1 gig data center edge. Normally what happens is that the &#8220;best&#8221; integration case is to put some form of oversubscribed 10 Gig card into their existing distribution layer, or in a worst case some customers are only able to provide 10 Gig of a collapsed core. This is obviously not an ideal setup. By integrating the Nexus 5000 40 or 20 port 10 Gig switches with the Nexus 2000 Fabric extender it provides us with a very clean way to integrate both 10 Gig and 1 Gig services in our Data Center access layer.<br /> </span></span>

<span style="font-size: medium;"><span style="font-size: small;"><span style="font-size: medium;"><strong>Why am I excited about this product?</strong></span></span></span>

<span style="font-size: medium;"><span style="font-size: small;"><span style="font-size: medium;"><span style="font-size: small;">I am lucky enough to work with some forwarding thinking customers with very large Data Center requirements. We have been working with Cisco over the past couple months to incorporate this end to end Nexus infrastructure into multiple customer designs. Before the Nexus  5000 / 2000 combination, designs to provide large layer 2 adjacent mixed 10 and 1 Gig services were well&#8230;. not as elegant as we would have liked to see. Now with Fabric Extension, we  are able to answer this mixed 10 / 1 Gig Data Center access layer design scenario in an elegant and scalable way.</span></span></span></span>

<span style="font-size: medium;"><span style="font-size: small;"><span style="font-size: medium;"><span style="font-size: small;"><span style="font-size: medium;"><strong>Want to learn more?</strong></span></span></span></span></span>

<span style="font-size: medium;"><span style="font-size: small;"><span style="font-size: medium;"><span style="font-size: small;"><span style="font-size: medium;"><a href="http://www.cisco.com/en/US/products/ps10118/index.html" target="_blank"><span style="font-size: small;">Nexus 2148T Product Page </span>&#8211; Cisco.com</a><br /> </span></span></span></span></span>