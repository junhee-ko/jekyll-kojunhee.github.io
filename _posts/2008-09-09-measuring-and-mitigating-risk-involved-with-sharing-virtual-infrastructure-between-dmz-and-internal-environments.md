---
id: 177
title: Measuring and mitigating risk involved with sharing virtual infrastructure between DMZ and Internal environments
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/?p=177
permalink: /measuring-and-mitigating-risk-involved-with-sharing-virtual-infrastructure-between-dmz-and-internal-environments/
aktt_tweeted:
  - 1
categories:
  - hyper-v
  - virtualization
  - vmware
tags:
  - blog
  - breach
  - business context
  - C
  - CISCO
  - Colin
  - compromise
  - Data Center
  - DESIGN
  - device contexts
  - enhancements
  - FCOE
  - HP
  - hyper-v
  - Instances
  - linux
  - NDA
  - Network
  - network infrastructure
  - Nexus 5020
  - passed
  - Pic
  - risk risk
  - san
  - security
  - storage
  - switch
  - threat
  - TrustSec
  - virtual device
  - virtualization
  - vlan
  - vmware
  - vulnerability
---
Ivan Pepelnjak over at <a href="http://blog.ioshints.info/2008/09/are-vlans-safe-in-dmz-environment.html" target="_blank">IOS Hints and Tricks </a>wrote a post about DMZ VLAN leaking that got me thinking.

He writes about &#8220;the VLAN leaking myth&#8221; and how it encourages clients to utilize physically separate network infrastructure in the DMZ&#8217;s. Now first things first, I wouldn&#8217;t call VLAN leaking a myth. At one time it was a very real and serious vulnerability that was exploited by overflowing the capacity of the switch you were attacking, and causing it to &#8220;downgrade&#8221; from switch to a hub. Once this happened you now had access to previously protected devices, as well as having the ability to sniff data as it passed through the shared hub backplane.

As he mentions though, this is 8 years ago. Most switches have evolved to the point where backplanes far exceed the traffic that could ever be injected into their switchports. Even beyond backplane enhancements there are many ways to further firm up your security stance &#8211; Virtual Device Contexts, not using Layer 3 SVI&#8217;s on a DMZ VLAN, utilizing PVLANs, using port security, virtual routing instances, and many more. Of course, there are still many other attack vectors that still remain, but can be mitigated by utilizing features built into the majority of enterprise switches available today.

I think the real question is not &#8220;are VLANs safe in a DMZ&#8221;. The important question is have you mitigated the probability of compromise (the actual threat) to levels that are acceptable to your business. This question remains whether you have a standalone switch or not. So many times we hear about risk risk and more risk. But risk alone is meaningless in a business context. What is important is combining risk with likelihood. For that I like to use a simple table to come up with the true threat.

[<img class="ngg-singlepic ngg-center" src="http://www.colinmcnamara.com/wp-content/gallery/breach/thumbs/thumbs_risk_grid.gif" alt="risk_grid.gif" />][1]{.thickbox}

For example, as I drive to Fry&#8217;s there is the risk of me dying due to a car crash. The impact of me dying is very high (risk) however the likelihood of an accident is low, and furthermore I reduce (mitigate) the latent risk (threat) by wearing my seat belt. So all in all the threat of me dying on my way to Fry&#8217;s is pretty darn low.

In a business context this may be that I have public facing web servers and network devices in my DMZ. The impact of them being compromised is that my public image may be tarnished for a short time, and my end users may lose productivity if they are not able to VPN into work, or access the Internet while on premise. I mitigate this risk by using firewalls and both host and network based Intrusion Prevention Systems as well as implementing best security practices on my network and systems devices. The latent risk (threat) remaining is at a level that is acceptable to the business leaders, so the system is allowed.

One question that I have seen coming up more often as we move towards fully virtualized data centers is centered around commingling of virtual infrastructure. There are some hard questions which challenge some practices that we have held true over the years.

  * Should you allow sharing of physical memory on a host virtual machine between an internal and DMZ server?
  * Should you allow virtual infrastructure from multiple security zones to share a storage array or cluster of arrays?
  * Should you allow multiple virtual switches in different security zones commingling on the same ESX or Hyper-V cluster?
  * Should you allow virtual firewall and load balancing instances protecting internal and external zones to reside on the same hardware?
  * Should you allow virtual routing instances from multiple zones to share a physical infrastructure?

In the past world of standalone systems, the additional cost of providing a wholly separate infrastructure for DMZ environments was relatively low. Each system generally had internal disk, or at most direct attached storage. Network devices themselves were scaled down to support one chassis one function. This fit quite neatly into the Enterprise Composite Network model that was quite common from 1999-2003.

Now, many data centers have moved to the Service Oriented Network Architecture (SONA). In this model the cost of a virtualized data center is primarily focused on foundation elements such as the virtual storage and virtual fabrics, virtualized network, and virtual systems elements. The cost of providing additional virtualized services off these elements is low, however the cost of duplicating the physical infrastructure is quite high on both the capital and operational levels. This is forcing the technical and executive leadership at many companies to take a long hard look at the true threats they are facing in previously physically separate security zones such as DMZ&#8217;s, Financial and other secure zones. In the end, they are having to decide whether the threat remaining after their security controls is worth duplicating hundreds of thousands of dollars worth of infrastructure or not.

These are hard questions, with really no single good answer. My gut feel is that over the next few years we will continue the move towards the fully virtualized data center where components such as memory, PCI-X buses, storage and network devices are even further decentralized. This will make the cost of duplicating the infrastructure more and more significant, causing consolidated data center (or compute) fabrics to be the norm. At this point the discussion will move away from securing zones by creating separate infrastructure, to providing end to end security, starting integrated application level security, maybe with TrustSec or a dirivative, all the way down to securing the data at rest on disk. For the time being however, the best we can do is sit down and do an honest appraisel of our security stances, mitigate what we can, and do our best to design data center architectures that provide the flexibility of implementing whatever choice the technical and business leaders agree on.

 [1]: http://www.colinmcnamara.com/wp-content/gallery/breach/risk_grid.gif