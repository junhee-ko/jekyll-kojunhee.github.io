---
id: 137
title: 'Application Extension API notes &#8211; Cisco Live 2008'
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/?p=137
permalink: /application-extension-api-notes-cisco-live-2008/
aktt_tweeted:
  - 1
categories:
  - CCIE
  - CISCO
  - DC3.0
  - Networkers
tags:
  - AXP Application Extension API
  - C
  - CISCO
  - Cisco Linux
  - cisco live
  - communication
  - daughtercard
  - Instances
  - isr
  - IVR
  - kvm
  - linux
  - NDA
  - Network
  - Networkers
  - packet
  - paravirtualization
  - reconfigure
  - Router
  - virtualization
---
The AXP is a open platform for the Integrated Services Router (ISR) that enables you to program in-house, custom applications that leverage packet level interfaces with the ISR platform. You can choose to install either a daughtercard (AIM-102) or a network module platform.

**Where would you use these ?**

You want  your custom application to be able to react, and act on network specific information. Integrating both at a very close level. Fundamentally your application can dynamically reconfigure your router in reaction to network events.

You want to remove common services such as AAA, Syslog, DHCP, etc, IVR apps, Unified communication apps all at the branch office in the ISR. If there is a failure, your router can dynamically reconfigure around that.

**AXP architecture **

Base Cisco Linux os, IOS CLI, Virtual Instances, C++, Perl, Java, OSGI, Bash. Fundementally this is very similar to a fedora core 4 systems doing paravirtualization.

**API Fun &#8211; What can it do**

  1. You can query and change both the router and the network module
  2. Leverage Embedded Event Manager (EEM) to trigger events on changes, and react to network events.
  3. Network Packet monitoring .. Sniff, Sniff, Sniff

**My Questions &#8211; **

  1. How do I automate network updates, similar to YUM?
  2. Is Cisco using KVM for paravirtualization?