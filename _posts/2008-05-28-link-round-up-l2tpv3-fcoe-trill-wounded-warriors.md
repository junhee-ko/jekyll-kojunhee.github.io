---
id: 126
title: 'Link Round Up &#8211; L2TPv3 FCOE Trill Wounded Warriors'
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/?p=126
permalink: /link-round-up-l2tpv3-fcoe-trill-wounded-warriors/
categories:
  - CCIE
  - certification
  - CISCO
  - DC3.0
  - FCOE
  - Fibre Channel Over Ethernet
  - Green Data Center
  - MPLS
  - Nexus 7000
  - NX-OS
  - Technology
tags:
  - C
  - CCIE
  - CISCO
  - DESIGN
  - FCOE
  - L2TPv3
  - MPLS
  - NDA
  - Network
  - Provider
  - Rbridge
  - Root Kit
  - Router
  - san
  - security
  - service provider
  - storage
  - switch
  - Trill
---
I come accross alot of very interesting material each week, only some of which I write about. These are some links that I found interesting this week.

**1. <a title="Cisco L2TPV3" href="http://www.cisco.com/en/US/tech/tk364/technologies_configuration_example09186a00801f66fa.shtml" target="_blank">Layer 2 Tunneling Protcol (V3) static and hairpin configuration example</a>** **&#8211;** my buddy <a title="Rick Davis CCIE #5672" href="http://www.ricksdavis.com" target="_blank">Rick</a> was nerding it out in the lab and sent a great configuration doc for L2TPv3 my way. L2TP(V3) is used to create a layer 2 psuedowire across layer 3 routed links. This is a great service provider tool that you can use in your own network, no MPLS needed :).

**2. <a title="SNIA FCOE" href="http://www.google.com/url?sa=t&ct=res&cd=6&url=http%3A%2F%2Fwww.snia.org%2Feducation%2Ftutorials%2F2008%2Fspring%2Fnetworking%2FHufferd-J_Fibre_Channel_Over_Ethernet.pdf&ei=WpM4SLaUDpqMtwPxp_nLDQ&usg=AFQjCNEYKYGudYVgNcUpT06gZnRfEHu1BA&sig2=MFNvs2ygtZWkb1OnFv59Fg" target="_blank">SNIA Education &#8211; Fiber Channel Over Ethernet</a> &#8211; **There is a lot of buzz going around right now about Fiber Channel Over Ethernet (FCOE). There is also a lot of misunderstanding about the fundamentals of this architecture. This Storage Networking Industry Association (SNIA) does an outstanding job of covering FCOE at both at an architectural level, as well as going over low level messaging structures.

**3. <a title="Trill IETF draft" href="http://www.ietf.org/internet-drafts/draft-ietf-trill-rbridge-arch-05.txt" target="_blank">Trill (Rbridge) architecture &#8211; IETF internet draft</a> &#8211; **I think the last time I was this interested in an internet draft was when iSCSI was first being proposed in the IP Storage working group. Trill, in my opinion is basically a light weight version of MPLS / VPLS. It has as far as I can tell most of the advantages of this architecture, without some of the configuration and hardware requirement drawbacks. Fair warning, reading this document started a doc hunt that killed my Saturday.

**4. <a title="Cisco IOS Root Kit" href="http://www.cisco.com/warp/public/707/cisco-sr-20080516-rootkits.shtml" target="_blank">Cisco&#8217;s Security Response to Sebastian Muniz&#8217;s IOS rootkit</a> &#8211; **Security is a very important aspect of network design. Sebastian&#8217;s IOS rootkit demonstration is going to force some customers who in the past have been &#8220;OK&#8221; with having older, possibly vulnerable IOS versions floating around to update their operational practices and start keeping their routers and switches operating systems as often as they do their servers. Thankfully, Cisco has been embracing technologies such as kernel virtual machines, in service software upgrades and more to lesson or remove the impacts of software upgrades.

**5. <a title="Wounded Warriors" href="http://newsroom.cisco.com/dlls/2008/ts_052708.html?CMP=AF17154&vs_f=News@Cisco:+Top+Stories&vs_p=News@Cisco:+Top+Stories&vs_k=1" target="_blank">Turning Wounded Warriors into Network Ninja&#8217;s</a> &#8211; **As a former Marine (well, always a Marine, formerly employed by the USMC) this program goes straight to the heart. Cisco is partnering with Naval Medical Center San Diego (NMCSD, or Balboa Naval Hospital for us locals) to provide technical training to Marines and Sailors who have recieved service ending wounds in Afghanastan and Iraq.