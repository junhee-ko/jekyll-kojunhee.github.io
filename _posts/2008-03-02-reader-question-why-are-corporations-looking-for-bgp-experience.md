---
id: 102
title: 'Reader question &#8211; Why are corporations looking for BGP experience?'
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/2008/03/02/reader-question-why-are-corporations-looking-for-bgp-experience
permalink: /reader-question-why-are-corporations-looking-for-bgp-experience/
categories:
  - CCIE
  - certification
  - CISCO
  - Technology
tags:
  - BGP
  - blog
  - C
  - CCIE
  - CCNA
  - CISCO
  - Colin
  - Data Center
  - DESIGN
  - hiring
  - Learning
  - Mike
  - MPLS
  - NDA
  - Network
  - Provider
  - service provider
  - Technology
  - virtualization
---
Mike, a reader of my blog, sent me an email last week with decent question for someone early in their career. Mike is currently looking for a new job. He was curious why so many corporate IT jobs were requiring BGP knowledge and experience.

**Mike Writes &#8211;**

&#8220;Hi Colin,  
I&#8217;m an avid reader of your blog and had a question that I figured you could answer. I don&#8217;t have CCIE knowledge like I&#8217;m sure a lot of your readers do. I have worked for the same company for 6 years and during that time had been promoted into the Network Group where I was sent through class and earned my CCNA. The company I worked for decided to relocate across the country and so I have been looking for a new job. Finding a new job doesn&#8217;t seem to be that big of a deal but I noticed a lot of job descriptions are asking for BGP experience. We didn&#8217;t use BGP at my last job and I thought BGP is used primarily by ISPs for routing between Autonomous systems? If that is the case why do so many non-ISP companys list BGP experience in Networking job descriptions? What are they doing with it? Shouldn&#8217;t the ISP be doing the BGP routing for them?  
Thanks!  
-Mike&#8221;

Well Mike there are 3 primary reasons why a company would require (or want) BGP knowledge from its candidates.

**Scenario 1. The company has an redundant Internet edge. **

In this case lets call our company sample\_company. Sample\_company has its website hosted in a publicly facing DMZ and wants to make sure that its web servers are available in the case of an ISP failure. Normally in this case the company would request and Autonomous Systems Number (ASN) from ARIN and would get assigned a block of publicly routeable IP address&#8217;s (normally /24) that they can advertise. Sample\_company would then peer with multiple ISP&#8217;s for example one connection to AT&T and the other to Sprint. Sample\_company would advertise their ASN through both these ISP&#8217;s, and in the case of a failure of one of their ISP&#8217;s, the rest of the Internet would be able to calculate a path to sample_company&#8217;s web servers via the backup ISP.

**Scenario 2. The company is utilizing MPLS for its WAN connectivity**.

From a customer perspective MPLS is a private BGP based WAN where all edge devices connected to the MPLS provider utilize BGP to inject and learn routes. One note, some providers do support advertisement of routes via OSPF and even EIGRP now, but the most common scenario is to use BGP as your internal WAN protocol while running MPLS. One trend I am starting to notice, is that since companies are already using BGP on the MPLS WAN, they have started utilizing BGP as their primary routing protocol for their sites to avoid running multiple routing protocols and having to redistribute into BGP to cross the WAN.

**Scenario 3. The company is using MPLS inside their data centers for segregation of business units.**

In essence they are using the same tools and technologies that MPLS service providers are, however applying it inside of their data center and campus networks. In this case, BGP is the routing protocol necessary to carry the routes between the seperate MPLS VPN&#8217;s that are running inside the corporate data center. While this sounds pretty complicated, it actually simplifies many of the designs that you would normally implement to attain the same goals.

**  
**

**Learn more about BGP &#8211;** Of course, there are many other reasons why you may see BGP on a job listing, but I think the previous covers the most common. If you are curious, and want to learn more about BGP I recommend buying <a href="http://www.amazon.com/gp/product/1578700892?ie=UTF8&tag=wwwcolinmcnam-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=1578700892" target="_blank">Routing TCP/IP volume 2 by Jeff Doyle</a>. This covers many great scenarios and configuration examples in EGP protocols. It is also written in plain English which can be a challenge with many technical books.

**Learn more about MPLS in the enterprise &#8211;** If you are feeling like learning about how you can implement MPLS inside of your own enterprise network then I would recommend buying<a href="http://www.amazon.com/gp/product/1587052482?ie=UTF8&tag=wwwcolinmcnam-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=1587052482" title="Network Virtualization" target="_blank"> Network Virtualization by Kumar Reddy and Victor Moreno</a>. I was lucky enough to have Rick Davis translate the whole idea of utilizing MPLS in a campus environment into plain English for me a couple years back. From that point I was able to really expand my knowledge base and start asking the right questions from a firm foundational understanding of the technology. Kumar and Victors book took my understanding to the next level, showing how to incorporate many very cool features to make a MPLS network stand on its head if you want to. I can say (and actually have said to Kumar Reddy) that this book redefined my data center designs for large corporate and enterprise customers. I really recommend that you add this to your collection.