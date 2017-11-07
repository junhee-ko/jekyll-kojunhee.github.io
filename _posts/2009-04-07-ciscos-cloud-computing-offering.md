---
id: 548
title: 'Cisco&#8217;s Cloud Computing Offering'
author: colinmcnamara
excerpt: 'Right now Cloud Computing is either the biggest threat that Cisco Systems has ever faced, or the biggest opportunity that Cisco has ever been presented with. How will Cisco react? '
layout: post
guid: http://www.colinmcnamara.com/?p=548
permalink: /ciscos-cloud-computing-offering/
aktt_notify_twitter:
  - yes
aktt_tweeted:
  - 1
categories:
  - CISCO
  - Cisco Unified Computing System
  - Cisco Unified Computing System Managerm UCSM
  - cloud computing
  - DC3.0
  - FCOE
  - Technology
  - virtualization
  - vmware
  - vSphere
tags:
  - CCIE
  - CISCO
  - cloud computing
  - Data Center
  - DC3.0
  - FCOE
  - paravirtualization
  - TrustSec
  - Unified Computing System
---
Right now Cloud Computing is either the biggest threat that Cisco Systems has ever faced, or the biggest opportunity that Cisco has ever been presented with.

Why do I say that? It is simple, every server that moves from a corporate data center into a cloud provider is a switchport and fibre channel port (and now server) that is not purchased from Cisco. More so, each system that is moved into the cloud hurts secondary sales of security and content switching products.

<span style="font-size: medium;"><strong>The promise of enterprise cloud computing<br /> </strong></span>

<span style="font-size: medium;"><strong></strong></span>The ability to dynamically scale enterprise compute workloads while only running a &#8220;right sized&#8221; private infrastructure is top of every CIO&#8217;s mind. This is the promise of cloud computing in the enterprise space. However, right now most cloud offerings are too new, and lack the critical integrations with VMware or XenSource (the two most common enterprise virtualization platforms) to make a serious dent in Cisco&#8217;s revenue stream. But fast forward 12 to 16 months and the kinks will be worked out. Projects that would previously have required new capital infrastructure will be restructured to use cloud providers as an operational expense. This will present a real threat to Cisco&#8217;s revenue moving forward.

John Chambers and his team of technologist are not new to this game, this is not the first threat to Cisco&#8217;s sales model. And I am sure that it won&#8217;t be the last. So if I was in their shoes, what would I do? (and more specifically, what do I think *they* are doing)

<span style="font-size: medium;"><strong>Create a compute platform that can power the cloud at a much lower cost that my competitors</strong></span>

Cisco publicly announced their computing offering, the Unified Computing System in March of this year. The promise of the UCS is to minimize power, cooling, capital costs and management overhead of data center compute. Looking at this new product line from an enterprise sales perspective it makes sence. For Cisco to continue with their growth plans they had to choose to enter the Compute or Storage markets, with the compute (server) market being the logical step.

While the Unified Computing System is well placed as an enterprise computing platform, I think there is a larger goal in mind. The large goal is to make a platform that can be shared by Cisco&#8217;s largest enterprise clients in their emerging private clouds, as well as by Cisco itself for it&#8217;s own cloud offering. By producing their own servers, with technology that Cisco alone has access too (memory expansion / hypervisor bypass) Cisco sets themselves up to have both lower hardware costs in their own cloud, as well as lower operational costs (power/cooling). This will provide Cisco with higher margin at the same price point as their competitors.

<span style="font-size: medium;"><strong>Distribute application aware network devices at customer locations</strong></span>

Cisco already has a significant edge over any competitive cloud offering. A vast majority of enterprise customers already run Cisco routers, switches and firewalls. If Cisco decided to say, port the TCP optimization code from their WAN acceleration platform into IOS, and configure it to work with their own cloud offerings this would give them an immediate leg up on the competition. Combine this with the existing WAAS auto discovery and Cisco could conceivably automatically integrate a cloud based caching offering with a customer&#8217;s onsite devices.

<span style="font-size: medium;"><strong>Create an application centric cloud security model that can be integrated with virtualization platforms</strong></span>

Last year Cisco announced a new approach to security called Cisco TrustSec. This technology includes a change from layer 4 based acl&#8217;s to an application focused role based implementation. This is applicable in the cloud environment because it provides a standard integration for controlling the access to and mobility of applications as they travel between public and private clouds.

An interesting side bar, is the fact that when integrating public and private clouds, there will always be applications that you want to keep on your internal cloud. The easiest way to do this is to put some sort of meta information on the virtual server containing a flag that this server should only run on the private cloud. With VMware there are fields that are used for DRS that can house just such data. I would not be surprised that with all the work that Cisco and VMware have been doing together if this was not implemented with vSphere (Virtual Infrastructure 4).

<span style="font-size: medium;"><strong>Learn as an organization how to profit from a SaaS model</strong></span>

I think this last piece of the puzzle has been overlooked by many people. Cisco already has in house experience dealing with a massive Software as a Service (SaaS) offering &#8211; Cisco WebEx. In acquiring WebEx Cisco also acquired the talent and technology behind the worlds largest collaboration platform. Cisco should be able to take the lessons learned from running and improving this platform, and apply them to their upcoming cloud offering.

<span style="font-size: medium;"><strong>Summary</strong></span>

Cisco has to go to market with a Cloud offering to maintain long term viability as a company. When they do they will have the benefit of lower cost of building and operating the grids that their cloud offering will run on. They will be able to leverage millions of Cisco network devices in their current install base as well as provide application centric security integrated with these same devices. And most importantly they will be able to use the lessons learned from running WebEx to ensure flawless delivery of an upcoming cloud computing offering.