---
id: 190
title: Cisco releases Nexus 1000V virtual switch for VMware
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/?p=190
permalink: /cisco-releases-nexus-1000v-virtual-switch-for-vmware/
aktt_tweeted:
  - 1
categories:
  - CISCO
  - cloud computing
  - DC3.0
  - Nexus 7000
  - vmware
tags:
  - blog
  - C
  - CISCO
  - Colin
  - Data Center
  - DESIGN
  - HP
  - linux
  - NDA
  - Network
  - Nexus
  - nexus 1000v
  - NX-OS
  - security
  - storage
  - switch
  - Technology
  - TrustSec
  - virtualization
  - vlan
  - vmware
  - vn-link
---
This afternoon Cisco released a new member of the Nexus family of switches, the Nexus 1000V. This is the first switch to take advantage of VMware opening up their ESX and ESXi platforms to for third party network device manufacturers. This switch directly address some pretty big pain points surrounding current virtualization implementations.

**The boundary between server team and network team responsibilities has become &#8220;fuzzy&#8221;**

Cisco address&#8217;s this issue by putting a switch that can be managed via the same methods common to other network devices inside the ESX cluster. This switch runs the same code that has become standard on Cisco&#8217;s Nexus series of Data Center switches &#8211; NX-OS.

Prior to adoption of virtualization, when there was a connectivity problem with a host it was quite common for the network team to verify functionality down to the switch port. The server team would do the same. This allowed for each team to focus on areas that met their core competancy. Once we moved from a real switch port, to a dumb bridge inside ESX, lots of finger pointing resulted.

Now, with a Nexus 1000V sitting virtually inside the ESX clusters, the boundary between network and systems teams has been re-estabilished. Now when there is a problem with a host inside an ESX cluster, the network team can use the same day to day troubleshooting tools available to them in other portions of the network to resolve issues faster, and with less finger pointing.

**Security controls have been moved further away from the hosts then we would like**

A best practice for applying security policy is to apply controls as close to the source as possible. Think of this analogy &#8211; Your kids are blasting Radio Disney from their computer. Which of the following do you do?

A. Turn down the speakers at the source

B. Distribute earplugs to all members or the household

Of course, the obvious action is to go to the source, and apply a control (turn down the volume, and tell the kids to clean their rooms). The same principle is valid on the networking side. The best practice is to apply security policies such as VLAN ACL&#8217;s and TrustSec policies directly to the switchports that host your switches. Before the Nexus 1000V this was impossible to do in ESX, and forced many environments to move security controls further up into the distribution layer. The side effect of this was that now the security stance from host to host inside ESX clusters was diminished.

The Nexus 1000V brings something called port policies to the table to address this. What these are is pre-configured application security descriptions that are available to you systems administrators to apply in a point and click fashion. Once these policies are applied to the virtualized host, they follow the host where ever it is moved in your virtual cluster.

**Provisioning and integrating the networks of VMware ESX clusters with classic networks for most is challenging at best  
**

I wrote an article in march about this specific issue in my post &#8211; <a href="http://www.colinmcnamara.com/2008/03/15/challenges-integrating-vmware-into-cisco-networks" target="_blank">Challenges integrating VMware into Cisco networks</a> . The core of this issue is that in general that the network integration portions of VMware ESX clusters is not really designed to address server teams , or network teams. In fact, you need to be pretty savy with both portions to successfully integrate VMware clusters into your network. In the real world, you generally find people that are good at one or the other, not both.

By putting a Nexus 1000V in your VMware clusters, you know give the networking teams something they can understand without having to learn Linux, and how it handles bridges (key to understanding ESX networking). With a Cisco switch running virtually inside your clusters, network teams can follow standard core / distribution / access models with the access layer now residing inside the ESX clusters. The network teams can also leverage their existing LAN switching skills for integrating the virtual switches in the clusters with the existing Data Center switching fabrics.

**With these roadblocks addressed, Cisco is moving to further the DC 3.0 vision**

To realize the DC 3.0 vision, the network inside of VMware clusters had to be under control, and follow the same architectural guidelines that the rest of our network is subject to. With the Nexus 1000V this is now a reality. The next steps withing the DC 3.0 vision to are to extend virtualization and mobility throughout our storage fabrics, and to continue to extend virtualization to the network as a whole, as well as focusing on application virtualization and acceleration to truly realize the vision of cloud computing in the data center.

On the storage virtualization side, Cisco will be using a technology called FlexAttach to enable virtual and physical hosts to change locations in the datacenter without storage team intervention (more on this in a near future post). And on the application virtulization and acceleration side, expect Cisco to continue to enhance it&#8217;s existing Application Control Engine (ACE) and Wide Area Application Services (WAAS), and further integrate these into their virtualization offerings.

**Want to learn more ?**

<a href="http://www.cisco.com/en/US/prod/collateral/switches/ps9441/ps9902/solution_overview_c22-494040.html" target="_blank">Introduction to VN-Link network services &#8211; Cisco.com</a>

<a href="http://www.cisco.com/en/US/prod/collateral/switches/ps9441/ps9902/data_sheet_c78-492971.html" target="_blank">Nexus 1000V overview &#8211; Cisco.com</a>

<a href="http://download3.vmware.com/vdcos/demos/DVS_Demo_800x600.html" target="_blank">VMware distributed vNetwork switch demo &#8211; VMware.com</a>

<a href="http://www.colinmcnamara.com/2008/03/15/challenges-integrating-vmware-into-cisco-networks" target="_blank">Challenges integrating VMware into Cisco networks &#8211; colinmcnamara.com</a>

<a href="http://blogs.cisco.com/datacenter/comments/video_blog_about_our_vmworld_announcements_today/" target="_blank">Douglas Gourley speaking about how Cisco and VMware will drive Cloud Computing in the Data Center</a>