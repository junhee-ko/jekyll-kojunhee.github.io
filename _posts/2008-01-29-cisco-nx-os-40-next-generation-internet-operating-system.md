---
id: 90
title: Cisco NX-OS 4.0 | Next Generation Internet Operating System
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/2008/01/29/cisco-nx-os-40-next-generation-internet-operating-system
permalink: /cisco-nx-os-40-next-generation-internet-operating-system/
categories:
  - CCIE Storage
  - DC3.0
  - IOS-NX
  - NX-OS
tags:
  - 
  - C
  - CISCO
  - Data Center
  - DC3.0
  - device contexts
  - Instances
  - mds
  - MPLS
  - Network
  - Nexus
  - Nexus 7000
  - NX-OS
  - NX-OS 4.0
  - Power
  - Router
  - san
  - security
  - storage
  - switch
  - Technology
  - virtual device
  - virtualization
---
The latest product to make its way from the storage networking arena into the data center networking arena is Cisco&#8217;s new NX-OS, next generation network operating system. Cisco has taken the highly succesful MDS line of switches, and  expanded on their success by taking their core operating system &#8211; SAN-OS and expanding it to provide the operating platform for the new Nexus 7000 series DataCenter switching platform. NX-OS 4.0 takes your DataCenter to storage level availability by decoupling the forwarding planes. This allow &#8220;always on&#8221; upgrades, millisecond failure response, and 5 nines services levels that the converged DataCenters of today require.

One feature that is new, and frankly extremely exciting is Virtual Device Contexts. Each virtual device runs with its own process, vs the use of tagged differentiators in technologies such as VRF-Lite. This provides for paravirtualized management instances, and clear lines of delineation for both software and hardware for a resource that can be shared between different groups within an enterprise.

Chassis that run NX-OS will support In Service Software Upgrades (NSSU) to allow operations groups to upgrade operating systems with zero downtime. This is accomplished through a combination of modular software architecture, and the decoupling for the control and forwarding planes.

One of my favorite features in SAN-OS is the embedded is fabric analyser. This is a tool that can sniff management traffic without having to plug in a sniffer, or provision a span port. You can dump in real time to a tcpdump like interface in the command line, output to a local file, or map to the ip of a wireshark instance that layer 3 access to the management port. Cisco again has taken the best of SAN-OS and bundled it with NX-OS. You will be able to remotely span management traffic without having to set up rspan, or trudge down to the datacenter to set up a sniffer.

Now, your router can call home right now so that is not a totally new feature. Smart Call Home was released recently into IOS. But that still doesn&#8217;t stop it from being a great feature. This allows you to configure NX-OS powered devices to mail an xml formatted troubleshooting email to TAC, and / or your support staff. This has been proven to drop the average time to resolution from 16-30 hours to 6 hours.

Now the drum roll&#8230;&#8230; All IP routing features are VRF aware. This has been a point of contention with me for a while. As Cisco and the market in general has embraced virtualization as an answer to pressing business concerns of leveraging shared infrastructure, while retaining security controls segregating disparate environments technologies such as MPLS and VRF within the datacenter have become more and more prevalent. That is great, however it never fails that the feature you need at that moment always seems to be coming out in the NEXT IOS release. With Cisco NX-OS 4.0 this is no longer a question.

Now, if I was a CIO and I was reading about all these new technologies that Cisco was pushing with NX-OS, I would frankly be cautious, and rightfully so. The thing is, most of these features are not new, they have been in use, and in production under the most stringent uptime conditions in the world &#8211; storage networking. They have been tried and tested on Cisco&#8217;s MDS line of storage networking switches. So get comfortable, get educated, but most importantly get on board for DataCenter 3.0.