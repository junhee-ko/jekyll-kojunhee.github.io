---
id: 108
title: Challenges integrating VMware into Cisco networks
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/2008/03/15/challenges-integrating-vmware-into-cisco-networks
permalink: /challenges-integrating-vmware-into-cisco-networks/
aktt_tweeted:
  - 1
categories:
  - CISCO
  - Technology
  - virtualization
  - vmware
tags:
  - blog
  - C
  - CCIE
  - certification
  - CISCO
  - Colin
  - Data Center
  - DESIGN
  - eplus
  - linux
  - NDA
  - Network
  - Nexus
  - nexus 1000v
  - passed
  - Power
  - security
  - storage
  - switch
  - Technology
  - VCP
  - virtualization
  - vmware
  - VMware Certified Professional
---
**UPDATE &#8211; for those looking for the [Nexus 1000v release, check out this post ][1]**

In the past couple years, VMware has changed from a product hidden in development and testing environments to a full fledged enterprise computing platform. It brings many benefits to the companies that implement it, however with those benefits come changes to the access layer of your data center. Your access layer is no longer a top of rack Cisco switch, or end of row aggregation chassis. It is now a virtual bridge that exists logically within your VMware ESX server.

[<img src="http://www.colinmcnamara.com/wp-content/gallery/cisco-vmware/vmware-overview-white-background.jpg" alt="vmware-overview-white-background.jpg" width="350" height="451" align="absmiddle" />][2]{.thickbox}

This causes an interesting question to come up in many customers &#8211; Who is responsible for the configuration and maintenance of this Vswitch? At first glance most groups reference the port on the last Cisco switch as the division of responsibility between network operations and systems operations. This has worked well in the past for a three main reasons.

First, it divided responsibilities based on technical skillset. For example a network engineer understands spanning tree, trunking, routing protocols, firewalling. While a systems engineer understands file systems, databases and Linux and Windows operating systems.

Second, it provided for a interconnection point where standardized configurations could be applied by an operational group, versus complicated configurations that could impact overall network designs and require an architectural board review.

Third it provided for a clean hand off for troubleshooting. Both network and systems operations could agree on layer 2-4 functionality in an area that provided for detailed debugging on both sides.

**Lack of a defined access layer**

VMware ESX throws a wrench in this model. We no longer have this well defined edge at the access layer. The access layer now exists virtually inside a server. More specifically, it is a logical devices running in a Linux server. This presents a challenge because it requires cross over knowledge. Whoever is responsible for this integration has to be fluent in Linux systems administration , and also fluent in network design and operations. Frankly this is a rare skill set to come across, as it requires and engineer who has attained high proficiency in both systems and network engineering.

I see this fuzzy line of demarcation often as a failing point for many VMware integrations. Many times I see network operations teams not involved in ESX cluster design because its a &#8220;server&#8221; , and systems operations teams generally don&#8217;t have the networking skills necessary to design and implement an fully functional system.. The solution to this problem is education and collaboration.

[![istock_000005344985xsmall.jpg][3]][3]{.thickbox}

**The need for collaborative design sessions**

The single most powerful element in a successful VMware integration is the creation of strong design documents. These are created by holding planning sessions where both your systems and networking leads hash out a strong design that takes both short and long term virtualization and network goals into account. Also, many times when people hear the word design, they think it is a high level Visio and a bill of materials. That is a just a fraction of the effort required. A proper design should cover everything from a 10,000 foot overview Visio down to protocol flow diagrams and configuration examples. By created a detailed design like this it is likely to bring up common issues such as 10 gig aggregation, trunking, VMotion security, layer two adjacency and layer 7 network service delivery on a white board instead of a production environment.

To create this detailed design, both your Network and Systems leads have to understand this product. VMware recognizes this is critical to successful implementation (and to further sales of their product) an offers the <a href="http://mylearn1.vmware.com/portals/certification/" target="_blank">VMware Certified Professional certification</a>. If you have the resources, I would recommend sending both your network and systems leads to this training at the same time. Having them attend training together allows them to leverage each others strengths and bring up questions specific to their network and their goals.

A real world example of this is the company I work for, Eplus. Last April forty of us, all senior engineers attended VMware Certified Professional training at the same time. The class was mixed up so there was an even distribution of CCIE&#8217;s, Systems Experts, and Storage Experts. Needless to say this presented our instructors with some extremely challenging questions, but more importantly it set the stage and created a venue for collaboration between these different practices within our own company.

**Real world benefits**

A great example of this model&#8217;s success this occurred last month. Rick and I were sitting in the engineering side of our Sunnyvale office, catching up on email after giving presentations at Cisco that morning and afternoon. In the bullpen behind us, one of the Microsoft architects was engrossed in a troubleshooting call with a large customer on the other line. It turns out a large systems vendor (who shall remain nameless) had been trying for a week to integrate the first ESX cluster into this network and just could not get the networking portion to work correctly. Our account manager received the call from a the customer, and asked the technical teams to step in to see if we could help out in any way.

The systems engineers were able to isolate the problem down to the network interconnections, but needed to bring in networking resources to resolve the problem. Rick and I were waved over and were given an overview of the problem and introduced us to the customer the far side of the call. We asked a few questions about the physical and logical architecture of their network and created a diagram of their network on the whiteboard. With this we were able to ask them to execute commands continuously isolating the problem domain until we found and resolved the issue.

Seven minutes had passed from the point Rick and I were waved over to the point the customer had a working installation. This allowed the customer to focus on moving their business forward instead of fixing a failed implementation. Three of us on the call had attended VMware Certified Professional training together. We had spent at a minimum 50 hours each creating a baseline of understanding in class, as well as many discussions in engineering meetings. The solution came in seven minutes not because of any one teams individual strengths, but because of collaboration. The systems engineers were able to isolate the problem domain very specifically. And as network engineers trained on VMware were able to quickly understand and digest the issues, and tie it together with our larger understanding of networks as a whole. Only at that point, when the team was able to leverage each others strengths were we able to address the problem so quickly.

[![istock_000004877664xsmall.jpg][4]][4]{.thickbox}

There will come a point in the next few years where this fuzzy boundary between the &#8220;network&#8221; and the &#8220;server&#8221; is established again. My call is that this will coincide with Cisco finishing development of their Vswitch that will reside inside the ESX server. This switch will require both Cisco and VMware improve their design and integration guides for ESX which are both frankly lacking substance. Until those detailed architecture, integration and troubleshooting guides exist the key to successful ESX cluster implementation will be a strong cross trained systems and network teams that are collaborating on the next level of virtual network design in your enterprise.

**Want to learn more?**

<a href="http://www.cisco.com/univercd/cc/td/doc/solution/vmware.pdf" target="_blank">Cisco &#8211; Integrating Virtual Machines Into Cisco Data Center Architecture</a>

This is Cisco&#8217;s main design guide regarding the integration of virtual machines. You can use it as a decent high level overview if you are a network engineer who is curious how VMware ESX, or Xen servers for that matter will fit into your network.

<a href="http://www.vmware.com/files/pdf/virtual_networking_concepts.pdf" target="_blank">VMware &#8211; Virtual networking Concepts</a>

This VMware document goes between high level overviews and detailed descriptions. It is a decent resource for a network engineer, and provides an overview of ESX network features, however it misses the target for providing configuration examples.

<a href="http://blog.scottlowe.org/" target="_blank">Blog of Scott Lowe &#8211; Technical Lead for Virtualization at Eplus Technology</a>

Scott is an engineer that works with me at Eplus Technology. He is based out of the east coast and covers servers, storage and virtualization. His blog is chock full of good of information. A recent post of interest was how to <a href="http://blog.scottlowe.org/2008/03/11/identifying-esx-server-nics-in-blades/" target="_blank">enable Cisco Discovery Protocol (CDP) on VMware ESX server network interface cards</a>.

 [1]: http://www.colinmcnamara.com/2008/09/16/cisco-releases-nexus-1000v-virtual-switch-for-vmware
 [2]: http://www.colinmcnamara.com/wp-content/gallery/cisco-vmware/vmware-overview-white-background.jpg "vmware-overview-white-background.jpg"
 [3]: http://www.colinmcnamara.com/wp-content/gallery/cisco-vmware/istock_000005344985xsmall.jpg "team-collaborating-cisco-vmware.jpg"
 [4]: http://www.colinmcnamara.com/wp-content/gallery/cisco-vmware/istock_000004877664xsmall.jpg "istock_000004877664xsmall.jpg"