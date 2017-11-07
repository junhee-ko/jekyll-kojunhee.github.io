---
id: 101
title: Identity aware networking using Cisco TrustSec
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/2008/02/23/identity-aware-networking-using-cisco-trustsec
permalink: /identity-aware-networking-using-cisco-trustsec/
categories:
  - CISCO
  - DC3.0
  - security
tags:
  - C
  - CISCO
  - Data Center
  - DC3.0
  - DESIGN
  - encryption
  - GLBA
  - HIPPA
  - HP
  - MPLS
  - Network
  - network infrastructure
  - Nexus
  - Nexus 7000
  - Sarbanes Oxley
  - security
  - SOX
  - switch
  - TrustSec
  - vlan
---
With all the fanfare surrounding the recent Nexus 7000 release I think many people have missed a significant new development in Cisco&#8217;s security portfolio. That new development is Cisco TrustSec. TrustSec takes the classic notion of access control based source and destination ip:ports and replaces it with a role and resource based methodology that fits quite nicely with security requirements driven by information assurance groups. It also brings link security on certain platforms using the 802.1ae protocol that encrypts high speed links at line rate without taking a performance hit.

Cisco TrustSec starts at the edge by negotiating a secure link if both hosts support it (802.1ae). This is similar to wireless encryption schemes, where a secure handshake is established and the L2 path become impervious to sniffing. This is user configurable, and to my knowledge the asics available to support line rate encryption are currently only on the Nexus 7000 blades.

The next step is to start 802.1x negotiations. For the people not familiar with 802.1x, it is a way of passing username / password information from your computer up into the network infrastructure. Once this is completed, the switch can not only utilise tools like NAC to place you into the appropriate quarantine, or access vlans, but it also know knows your identity.

Now the &#8220;network&#8221; is aware of your identity, a new level of granular security control can be deployed across your infrastructure. These security policies can map into &#8220;user x can connect to webserver y&#8221; instead of being restricted by ip and port. This allows you to utilize true roles based administration similar to what you use in your Windows and Unix file systems, but now you can do this across the network.

How is this done ? I like to think of this as a mix between dscp and mpls tags. Which in a nutshell means that when traffic enters the network it is tagged with a small amount of additional &#8220;identity: information which is retained as it traverses the network. This information can be used to augment or completely replace your current ACL based security controls in a way that enables you to more effectively comply with complex regulatory environments such as PCI, SOX, GLBA and HPPA.

Over the past few years we have learned how to leverage intelligence in the the network by utilizing tools like QOS, MPLS VPN&#8217;s, and many others. Expect to add Cisco TrustSec to your quiver of tricks to address the ever growing compliance needs faced by today&#8217;s network designers.

<a href="http://www.cisco.com/en/US/netsol/ns774/networking_solutions_package.html" title="http://www.cisco.com/en/US/netsol/ns774/networking_solutions_package.html" target="_blank">Learn more about Cisco TrustSec</a>