---
id: 782
title: Cisco Nexus 4000 Blade Switch
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/?p=782
permalink: /cisco-nexus-4000-blade-switch/
categories:
  - CISCO
  - Nexus 4000
tags:
  - CEE
  - certification
  - CISCO
  - Data Center
  - Fabric Extender
  - Nexus
  - Nexus 4000
  - Nexus 7000
  - NX-OS
  - switch
  - Technology
  - UCS
---
Cisco&#8217;s vision of the unified data center took another step forward today with the announcement of the Nexus 4000 series blade center switches. This switch is another step forward  in Cisco&#8217;s view of a true multiprotocol network.

What does this mean?  In Cisco&#8217;s view of the world this means supporting the transport of Fibre Channel, Fibre Channel over Ethernet, iSCSI, NFS and CIFS in a scalable and dependable fashion.

**What is the Nexus 4000?**

<img alt="" src="http://www.colinmcnamara.com/wp-content/gallery/nexus-4000/screen-shot-2009-09-29-at-11-07-06-am.png" title="What is the Nexus 4000" class="aligncenter" width="515" height="371" />

The Nexus 4000 is the 5th release of the Nexus line of switches (counting the UCS 6100 as a release).  This switch fits in the blade center form factor. It is intended to be used in the place of the Catalyst 3000 and 3100 series blade switches. It is a full featured Nexus switch, very similar to it&#8217;s big brother the Nexus 5000.

**What protocols will it support?**

In keeping with Cisco&#8217;s vision of a Unified IO platform in the data center the Nexus 4000 will support Converged Enhanced Ethernet (CEE) (yes, they finally caved on the naming) as well as providing the same reliable transport of iSCSI, NFS, and CIFS that you get with the Nexus 5000.

<img alt="" src="http://www.colinmcnamara.com/wp-content/gallery/nexus-4000/screen-shot-2009-09-29-at-11-06-32-am.png" title="What Protocols Will It Support" class="aligncenter" width="514" height="369" />

**What blade centers will it work with?**

Cisco is playing close to the chest announcing what blade server vendors will support this product.

My initial gut reaction was that HP would not be supporting this product, however I just saw that HP is OEM&#8217;ing the Nexus 5020. It would make sense that they would support the Nexus 4000 in their C Class blade centers, though only time will tell.

IBM however has been very supportive of integrating Cisco technology, as well as OEM&#8217;ing the Nexus 5000 switch in their portfolio. I fully expect the Nexus 4000 to be supported in the IBM BladeCenter platform, though again I cannot confirm.

Dell also has resold Cisco blade switches, and although they do not OEM the nexus 5000 they have been large proponents of the Nexus solution and unification of IO workloads throughout their platforms.

**Is it the same as a Fabric Extender?  
**

The Nexus 4000 is not a Fabric Extender. What is the difference? A Fabric Extender is a really efficient multiplexer. While using a Fabric Extender the main goal is vast simplification. What you end up with is a dumbed down remote line card that provides simple, fast services to your access layer. This is great for most uses, however there are instances where you need to provide richer services. A full function switch like the Nexus 4000 is appropriate in this case.

**What does it run?**

<img alt="" src="http://www.colinmcnamara.com/wp-content/gallery/nexus-4000/screen-shot-2009-09-29-at-11-06-48-am.png" title="What does it run" class="aligncenter" width="514" height="375" />

The Nexus 4000 runs NX-OS, Cisco&#8217;s data center switching operating system. This is the fourth release of what was previously named SAN-OS which ran on Cisco&#8217;s MDS line of SAN switches. This operating system is shared between the Nexus 7000, 5000, 4000, 1000v,UCS Fabric Interconnect and MDS line of SAN switches. Now you can have a consistent operating system platform from your data center core, all the way down through your blade switches and into your virtualization layer.

**When will it be available?**

Just like when the 3000 and 3100 series blade switches got announced, we are going to have to wait on the individual server manufactures to announce support at their own pace.** **My gut feel says we will be waiting a couple months for units to get out, and for the vendor certification process to complete. Though with business picking back up, this product may get out sooner.