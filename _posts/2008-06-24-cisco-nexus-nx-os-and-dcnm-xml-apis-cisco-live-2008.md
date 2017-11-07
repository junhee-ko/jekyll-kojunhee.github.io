---
id: 136
title: 'Cisco Nexus NX-OS and DCNM XML API&#8217;s &#8211; Cisco Live 2008'
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/?p=136
permalink: /cisco-nexus-nx-os-and-dcnm-xml-apis-cisco-live-2008/
aktt_tweeted:
  - 1
categories:
  - CISCO
  - DC3.0
  - NX-OS
  - Technology
tags:
  - C
  - CISCO
  - cisco live
  - communication
  - NDA
  - Network
  - Nexus
  - NX-OS
  - Technology
  - virtual device
---
Since I am at Cisco Live Networks all week, and I take notes anyways, i thought I would share them with you.

**NX-OS / DCNM XML API Fundamental Technology**

Netconf &#8211; platform for secure communication of XML data between DCNM / NX-OS and mgmt station.

XML, using clear text tags, creates a self describing API. This is necessary because of the confusion and unneccessary complexity inherent in the current SNMP MIB based structure commonly in place today.

Webservices API = SOAP/XML over HTTPS.

**Netconf/XML on NX-OS capabilities.**

  * Must be run over SSH
  * Maximum of eight concurrent NetConf Sessions per nexus virtual device context.
  * Every single CLI capabilities is assigned a XML tag

**JMS is supported in DCNM as wel as NETCONF**

  * Native integration with IBM Message Queue