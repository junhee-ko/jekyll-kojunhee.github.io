---
id: 1401
title: Simplifying scale out DataCenter design with UCS Manager 2.1
author: colinmcnamara
excerpt: "In this case the 2.1 release of UCSM takes a product that many people already have (Unified Computing System) and makes it do more. There aren't going to be press conferences about this, but it is worth taking a closer look at. It will make my life easier, and I hope it does the same for you."
layout: post
guid: http://www.colinmcnamara.com/?p=1401
permalink: /simplifying-scale-out-datacenter-design-with-ucs-manager-2-1/
al2fb_facebook_image_id:
  - 1400
al2fb_facebook_link_id:
  - 667137287_10151294000057288
  - 667137287_10151294000147288
al2fb_facebook_link_time:
  - 2012-11-01T19:32:26+00:00
al2fb_facebook_link_picture:
  - meta=http://www.colinmcnamara.com/wp-content/uploads/2012/11/NewImage5-287x300.png
categories:
  - CISCO
  - Cisco UCS
  - Cisco Unified Computing System
  - Cisco Unified Computing System Managerm UCSM
tags:
  - C-Series
  - CCIE
  - ccie lab
  - CISCO
  - Cisco Linux
  - Data Center
  - DESIGN
  - FCOE
  - Fibre Channel
  - Hadoop
  - Network
  - openstack
  - UCS
  - ucsm
  - Unified Computing
  - Unified Computing System
---
I&#8217;ve been designing and deploying UCS since the product was released a couple years ago (technically I was involved in the pre-release so we will say since UCSM v 0.8). From the start I was constantly pushing up against scalability and design constraints of UCS. The benefits of the system outweighed the challenge, but these design constraints created some challenges in creating external systems to meet the needs of large UCS customers.

Don&#8217;t get me wrong, out of any server platform I prefer UCS. That being said there are a few area&#8217;s that have really caused headaches for me over the years.

<h3 style="text-align: center;">
  Headaches solved with the release of UCSM 2.1
</h3>

<img class="aligncenter" title="NewImage.png" src="http://www.colinmcnamara.com/wp-content/uploads/2012/11/NewImage5.png" alt="NewImage" width="500" height="522" border="0" />

<h3 style="text-align: center;">
  <strong>Headache #1 &#8211; Once I scale past a certain number of servers, I have to establish a new UCS domain</strong>
</h3>

This has been a huge challenge for both large single data center instances, as well as multi data center instances (such as DR). In both these cases I would have to utilize tricks like placing mac address, wwn pools and other &#8220;unique&#8221; identifiers into a CMDB (Configuration Management Database) outside of UCS. And even when utilizing external CMDBs, there was a still a bit of design necessary to lay out UCS domains in a fashion that would support eventual integration in the future without overlapping configuration elements.

All of this work was done to ensure that if two servers were instantiated in two different UCS domains that they wouldn&#8217;t have conflicts if they wound up on the same segment. Handling this logically by bit swapping the UCS domain ID in certain resource pools wasn&#8217;t terribly complicated, but in my opinion unnecessary (though integration with CMDB&#8217;s can be very complicated).

This got even more complicated If you wanted to have a DR site. Making something simple happen like having a server that boots from SAN boot of the DR site SAN in an outage involved using external tools or scripts. In my opinion this is something that should be handled by UCSM or a manager of UCSM.

<h3 style="text-align: center;">
  <strong>Headache solved &#8211; UCS Central Manager of Managers</strong>
</h3>

<img style="display: block; margin-left: auto; margin-right: auto;" title="NewImage.png" src="http://www.colinmcnamara.com/wp-content/uploads/2012/11/NewImage3.png" alt="NewImage" width="500" height="260" border="0" />

<span style="font-weight: normal;">For those in the now, this has been in the works for a VERY long time. In fact the early install (1000+ servers) that I mentioned above where we had to use external CMDB&#8217;s to glue UCS domains together in the first year of UCS generated this feature request. </span>

UCS Central is in a sense a manager of managers. This allows you to aggregate pools and policies of multiple independent UCS domains into one central management platform.

It solves the problems &#8211;

  * resource conflicts across pools,
  * mobility of service profiles between UCS domains as well as
  * centralizing access logs
  * centralizing access to console servers

<h3 style="text-align: center;">
  <strong>Headache #2 &#8211; Even when Cisco released code to manage c-series 19&#8243; rack mounts under UCSM it still required a bunch of extra cables and equipment to make it work.</strong>
</h3>

70% of the worlds x86 servers are in a 19&#8243; rack mount form factor. Recently Cisco enabled them to be managed under UCSM and to have a data path that exits through the fabric interconnects. This allowed a couple key things to happen. First, it allowed a unified view of systems for an administrative staff for a data center. Second, it allowed a clean data path from, say a storage caching engine run on a a b-250 blade, to a compute node housed on a c240 rack mount. All of this communication would be contained within the fabric interconnects, and not have to exit northbound as it had in the past.

I was happy with this release. It allowed the c-series servers to be managed under UCSM with the same tools techniques and API&#8217;s that we manage the blades with. However the code was not updated to allow all that magic to happen over a single wire.

You would end up with beautiful cabling on the backs of your blade centers, and a giant mess of cables coming out of your rack mounts since you needed separate cables to support data path vs management plane. Call me a neatnick, but I like my racks to be pretty and clean (and not have to buy extra switches, cables and adapters).

<p style="text-align: center;">
  <strong>Headache solved &#8211; Single wire management for ALL UCS servers</strong>
</p>

****<img class="aligncenter" title="NewImage.png" src="http://www.colinmcnamara.com/wp-content/uploads/2012/11/NewImage4.png" alt="NewImage" width="600" height="240" border="0" />

With the 2.1 release now all you need is a single Cisco Virtual Interface Card in your UCS 19&#8243; rack mount (two if you want redundancy) to allow the full feature set that you have available on a UCS blade. For me this not only simplify&#8217;s my designs, but also allows flexibility in things like designing Hadoop and OpenStack Swift Object Storage clusters where redundancy is done at the application level and dual 10 gig interfaces are not needed.

<h3 style="text-align: center;">
  <strong>Headache #3 &#8211; For certain topologies I want storage locally attached to my pods using whatever protocol I want</strong>
</h3>

Here is a dirty little secret. Even though you can abstract a bunch of storage functions into UCS, most server guys are still a bit impatient with their peers on the storage teams. There are many times when the server guys want to consolidate a bunch of boot disks into an array and connect them directly to the fabric interconnects.

Over time Cisco has been releasing support for additional protocols connected in this way, however it was not ubiquitous. This created problems because you could not create a standard topology that supported flexible protocol consumption in your network. You would end up with two to three variants of supported topologies. In my opinion this creates issues with operational procedures and leads to extension of outages and generally inefficient designs.

**Headache solved &#8211; Flexible and consistent storage topology options no matter what protocol is being used.**

<img style="display: block; margin-left: auto; margin-right: auto;" title="ucs-fcoe-multi-hop.png" src="http://www.colinmcnamara.com/wp-content/uploads/2012/11/ucs-fcoe-multi-hop.png" alt="ucs fcoe multi-hop cisco" width="600" height="243" border="0" />

With UCS 2.1 now, no matter what protocol floats your boat you can implement them in a consistent manner. This may include directly connecting Fibre Channel storage to your fabric interconnects and zoning them. Or it may include utilizing multi-hop FCoE (I&#8217;ll leave the argument to whether you SHOULD use this till later).

Either way, the most important thing to me is that no matter what the design requirements are. Now you have the tools available to meet them in a consistent fashion without changing your entire network and systems topology.

<h3 style="text-align: center;">
  Colin&#8217;s Thoughts
</h3>

Quite often there is lots of glitz and glamor when a new product is released. Press conferences are held where everybody looks at the shiny blinky things and oohs and aweess. However when new software makes things you already use every day work better, or allows them to do new things comes out nobody notices.

In this case the 2.1 release of UCSM takes a product that many people already have (Unified Computing System) and makes it do more. There aren&#8217;t going to be press conferences about this, but it is worth taking a closer look at. It will make my life easier, and I hope it does the same for you.

&nbsp;

&nbsp;

&nbsp;