---
id: 46
title: Zone based IOS firewalls
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/2007/10/15/zone-based-ios-firewalls/
permalink: /zone-based-ios-firewalls/
blogger_blog:
  - colinmcnamara.blogspot.com
blogger_author:
  - Colin McNamara
blogger_permalink:
  - /2007/10/zone-based-ios-firewalls-cisco-has.html
categories:
  - CCIE
  - CISCO
  - Technology
tags:
  - C
  - CCIE
  - CISCO
  - Colin
  - DESIGN
  - error
  - NDA
  - Network
  - packet
  - Router
  - security
  - threat
  - virtualization
---
Zone based IOS firewalls

Cisco has finally included zone based firewalling in the IOS firewall feature set. The configuration guide can be found here &#8211;

[Zone Based Firewall Design and Configuration Guide][1]

The things that really got me interested are &#8211;

1. It is VRF aware (works well with network virtualization strategies)  
2. No more CBAC&#8217;s  
3. Policing built into firewalling classes  
4. Content inspection including HTTP,P2P, and Instant Messenger

I think the biggest plus for this release is that IOS firewalls are finally following the general trend of zone based firewalling. By moving this way, configuration errors resulting in lax controls are likely to be minimized.

Excerpts from the documentation &#8211;

Cisco IOS Software Release 12.4(6)T introduced a new configuration model for the Cisco IOS Firewall feature set. This new configuration model offers intuitive policies for multiple-interface routers, increased granularity of firewall policy application, and a default deny-all policy that prohibits traffic between firewall zones until an explicit policy is applied to allow desirable traffic.

Nearly all firewall features implemented prior to Cisco IOS Software Release 12.4(6)T are supported in the new zone-based policy inspection interface; supported features are as follows:

•Stateful packet inspection

•Application inspection

–HTTP

–Post Office Protocol (POP3), Internet Mail Access Protocol (IMAP), Simple Mail Transfer Protocol/Enhanced Simple Mail Transfer Protocol (SMTP/ESMTP)

–Sun RPC

•VRF-aware Cisco IOS Firewall

•URL filtering

•Denial-of-service (DoS) mitigation

Zone-based policy firewall generally improves Cisco IOS performance for most firewall inspection activities.

The only Cisco IOS Firewall features that are not supported in zone-based policy firewall in Cisco IOS Software Release 12.4(6)T are as follows:

•Authentication proxy

•Stateful firewall failover

•Unified firewall MIB

Zone-based policy firewall completely changes the way you configure a Cisco IOS Firewall.

The first major change to the firewall configuration is the introduction of zone-based configuration. Cisco IOS Firewall is the first Cisco IOS Software threat defense feature to implement a zone configuration model. Other features might adopt the zone model over time. The classical Cisco IOS Firewall stateful inspection/context-based access control (CBAC) interface-based configuration model employing the ip inspect command set will be maintained for a period of time, but few, if any, new features will be configurable with the classical command-line interface (CLI). Zone-policy firewall does not use the stateful inspection/CBAC commands. The two configuration models can be used concurrently on routers but not combined on interfaces; an interface cannot be configured as a security zone member as well as being configured for ip inspect simultaneously.

Zones establish the security borders of your network. A zone defines a boundary where traffic is subjected to policy restrictions as it crosses to another region of your network. Zone-Policy Firewall&#8217;s default policy between zones is to deny all. If no policy is explicitly configured, all traffic moving between zones is blocked. This is a significant departure from stateful inspection&#8217;s model, in which traffic was implicitly allowed unless it was explicitly blocked with an access control list (ACL).

The second major change is the introduction of a new configuration policy language known as CPL. Users familiar with the Cisco IOS Software Modular quality-of-service (QoS) CLI (MQC) might recognize the format being similar to QoS&#8217;s use of class maps to specify which traffic will be affected by the action applied in a policy map.

Colin McNamara  
[Copyright ©2008 | Colin McNamara | CCIE 18233 | All Rights Reserved&#8221;][2]

 [1]: http://www.cisco.com/en/US/products/ps6350/products_feature_guide09186a008072c6e3.html#wp1061094
 [2]: http://www.colinmcnamara.com "Copyright ©2008 | Colin McNamara | CCIE 18233 | All Rights Reserved"