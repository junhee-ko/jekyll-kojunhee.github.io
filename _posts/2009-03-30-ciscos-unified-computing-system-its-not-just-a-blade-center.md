---
id: 523
title: 'Cisco&#8217;s Unified Computing System &#8211; It&#8217;s not just a blade center'
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/?p=523
permalink: /ciscos-unified-computing-system-its-not-just-a-blade-center/
aktt_notify_twitter:
  - yes
aktt_tweeted:
  - 1
categories:
  - CISCO
  - Cisco 2100 Fabric Extender
  - Cisco 6120XP
  - Cisco 6140XP
  - Cisco B Series Blades
  - Cisco Server Array Manager SAM
  - Cisco UCS B200
  - Cisco UCS B250
  - Cisco Unified Computing System
  - Cisco Unified Computing System Managerm UCSM
  - cloud computing
---
**<span style="font-size: large;">Overview of Cisco&#8217;s Unified Computing System</span>  
**

This March, Cisco formally announced its entry into the enterprise computing market with a new product line called the Cisco Unified Computing System (UCS). I say formally announced, becase the existence of the Unified Computing System might just be the worst kept secret in history. In the months prior, to launch Cisco has been openly talking about the system, as well as many news agencies. The only people who haven&#8217;t been talking about the system were those of us who got briefed in early and were under strict NDA. (yours truly being one of them). But now, the multiple layers of NDA have been removed and I am free to talk. So, let me tell you about a new concept called Unified Computing.

The Unified Computing System answers a simple question &#8211; &#8220;what would you do if you could build a system with no preconceptions&#8221;. That same question has been asked over the years by Cisco. The results have given us the Catalyst 6500 line of switches, the Cisco MDS storage line, as well as the Nexus 7000/5000/2000/1000V family of switches.

<span style="font-size: small;"><strong>Nuova &#8211; a history of innovation</strong></span>

A couple of years ago, Cisco funded a startup called Nuova (meaning &#8220;New&#8221; in Italian). The founders of this startup were the same innovators who led the Catalyst, MDS and Nexus products. Not only did they have a track record of successful products, but they also had experience in both types of Data Center networking &#8211; Ethernet, and Fibre Channel. This startup took the lessons they learned creating a non blocking, low latency, highly available fabric for the MDS line of SAN switches and created a new line of Data Center switches, the Nexus 5000 that is able to transport Fibre Channel and Ethernet traffic at the same time, through a single adapter.

In April of 2008 Cisco formally acquired Nuova (which in effect was just hiring prior innovators back). Nuova was renamed the Server and Virtualization Business Unit (SAVBU), and the Nexus 5000 was released to market, making Cisco the first vendor to deliver a solution based around the upcoming Fibre Channel over Ethernet standard (FCOE). This pattern of innovation continued, as SAVBU released a virtual switch for VMware (the nexus 1000V) and this January released a remote line card technology called Fabric Extension. Those of us on the inside got the hint that the choice of names for this new business unit (**SERVER** and **VIRTUALIZATION** Business Unit) was a foreshadow of things to come.

<span style="font-size: large;"><strong>Unified Computing System enclosure w/ redundant 6120 Fabric Interconnects</strong></span>

[singlepic id=78 w=420 h=440 float=]

**Here are some spec&#8217;s to get you started &#8211; **

  * Single point of management for all devices in the fabric.
  * Virtual machine enabled networks adapters. (VNtag capable)
  * Up to 320 B-series compute blades in one fabric.
  * Up to 384 Gigabytes of memory per blade (full width blade)
  * Server Profiles &#8211; virtualize server identities (UUID, WWN, MAC)
  * Hardware Assisted Virtualization using Intel&#8217;s next generation Xeon (code named Nehalem-EP) processors
  * Redundant 10 Gigabit connections between servers.
  * Fibre Channel SAN access available to every blade.
  * Capital costs up to 20% less
  * Operational costs up to 30% less

The UCS does all of this while using 1/3 less components then the competition. What does using less components give you? Less components means less things to buy (lower capital expense). It also means less things to power and cool (lower operational expens). And finally it means less items to manage (lower management burden) How does Cisco do all of this while using drastically fewer components? I think it is necessary to talk about the major components that they system is built from to answer that question.

<span style="font-size: medium;"><strong><br /> </strong></span>

<span style="font-size: large;"><strong>Cisco UCS 6100 Fabric Interconnect (Nexus 5000 on steroids)</strong></span>

[singlepic id=87 w=500 h=440 float=]

<p style="color: #ffffff;">
  .
</p>

The primary building block of the system is the Cisco UCS 6100 Fabric Interconnect. Cisco took the non blocking, low latency, lossless fabric from the MDS that was used on the Nexus 5000 and used it as a building block for the 6120 and 6140 Fabric Interconnects. These fabrics support 20 and 40 (6120/6140)10gig Data Center Ethernet (combined Fibre Channel and Ethernet support).

  * 6120 &#8211; 20 Fixed 10 Gig Data Center Ethernet ports along with an expansion module that supports native Fibre Channel, or additional Data Center Ethernet interfaces
  * 6120 &#8211; 40 Fixed 10 Gig Data Center Ethernet ports along with two expansion module that supports native Fibre Channel, or additional Data Center Ethernet interfaces

The 6100 series Fabric Interconnect unifies Storage and Ethernet network, as well as providing supervisory functions for its remote line cards, the 2100 series fabric extenders that are inserted the compute chassis. The other thing the 6100 Fabric Interconnect does is house the Unified Computing System Manager (UCSM).

<span style="font-size: large;"><strong>Cisco Unified Computing System Manager (UCSM)</strong></span>

The UCSM runs on the fabric switches, providing a single point of management for all components in the fabric &#8211;

  * I/O Fabric
  * Chassis and Services
  * Adapters and Virtual I/O

This interface can be accessed through either a web based Gui or CLI. It also supports a full API for programatic integration and management of the system. The biggest thing that they SAM gives you is the ability to dynamically provision server attributes down to the compute blades. Attributes that can be pushed down dynamically include CPU UUID, SAN PWWN, Ethernet MAC address, and many more. These items are pushed down through as Service Profiles.One key component of the service profile is the Port Profile.

[singlepic id=81 w=500 h=440 float=]

<p style="color: #ffffff;">
  .
</p>

These Port Profiles are dynamically created in the SAM, and most importantly enable you to create virtual network interfaces (vNics) that show up to your server administrators as normal network interfaces. This allows your server administrators to follow their application vendors recommended interconnection topologies.

A great example would be VMware&#8217;s recommended topology for ESX. In this topology there are four network intefaces defined. Each for a specific function. This logical topology can be implemented, with all the relevant speed, QOS, VLAN, and security attributes all &#8220;pre-configured&#8221; for the virtulization administrators, simplifying their virtualization cluster deployments.

<span style="font-size: large;"><strong>Cisco UCS 2100 Fabric Extender (Next Generation FEX)</strong></span>

 The next component in this architecture is the UCS 2100 Series Fabric Extender (FEX). There are two of these in each bladechassis. Each FEX has the capability of up-linking to 6100 Fabric Interconnects with four 10 Gig ports. for a total of 80 Gigabit persecond out of each blade chassis (supporting 8 half width blades, or 4 full width blades). Each FEX is managed as a &#8220;remote line card&#8221; connected off of the Fabric Interconnects.

Logically, think of your 6500 series switch in your Data Center right now. You have three logical functions, supervisory functions (sup module), a bus for the switching fabric (traces in the chassis) and line cards (6748 for example). You will notice that you only manage the sup module itself. You don&#8217;t shell into to each line card to set up backplane interconnects, or to update microcode. You update software and configurations on the sup module, and the intelligence that Cisco builds into its software manages this for you.

The 6100 and the 2100 interact in the exact same way. In this case the 6100&#8217;s are the sup modules, the 2100&#8217;s are the line cards, and we are running 10 Gig connections to build the switching fabric. What this gives you is a simplified network architecture, which takes elements that would in the past be individually managed, maintained, upgraded, etc and consolidates that into one highly available, high bandwidth consolidated SAN and Ethernet for your Data Center compute needs.

<span style="font-size: large;"><strong>Putting Network Intelligence on the Compute Blade</strong></span>

<span style="font-size: medium;">[singlepic id=88 w=520 h=440 float=]<br /> </span>

Cisco will be giving customers three mezzanine card network adapters options for the UCS.

The first card (based is based on a the Palo chipset. This chipset was developed internally at Cisco and performs Network, Storage and Virtual Machine networking functions all on one 10 Gig capable chip. This chipset effectively extends network intelligence into the blade itself allowing for some pretty interesting integrations with Virtual Machine Hypevervisors (VMware, Hyper-V, Etc).

The second option is based on the Menlo chipset in conjunction with either a Qlogic or Emulex Fibre Channel adapter chipset that gives you 10 Gig network access, while retaining strict compatability with applications that require either of these classic HBA&#8217;s.

The third option is an &#8220;economy&#8221; option based on an Intel chipset. This will give the compute blade 10 Gig access.

What will drive your choice of network adapter? I think the biggest driver will be a technology called &#8220;VNtag&#8221;. This technology is currently in use on the FEX to encapsulate traffic that enters the fabric with a little shim header that communicates the identity of the incoming port (VLAN, QOS, Security info, etc). This shim header passes from the FEX up to the 6100 where the shim header is removed and the frame is processed.

This alone is very cool, however Cisco has taken things one step further and put the ability to impose VNtag&#8217;s in the Palo chipset (on the blade) itself. What this gives you the ability to logically attach a virtual machine DIRECTLY to the network. We no longer need a vSwitch, or even a 1000V to give full network functionality to a virtual machine. Effectively, Cisco is giving the network adapter inside of the blade many of the functions of a network switchport. Logically what this does is reduce your network tiers from four tiers in a competitive system, to two tiers in a Unified Computing System.

[singlepic id=83 w=500 h=440 float=]

<span style="font-size: large;"><strong>Cisco UCS B-Series Blades </strong></span>

The compute blades themselves are available in either 1/2 width of full width form factors. As stated in the formal announcement the maximum memory for a full width blade will be 384 Gigabytes per blade. Why is this important?

At release, there will be two option for compute blades.

Half width blade

  * 2 quad core Intel Xeon 5500 processors
  * 96 Gigabytes of memory
  * Two small form factor SAS drives (raid 0 and 1)
  * Single Converged Network Adapter slot (connected to redundant fabrics)

Full width blade

  * 2 quad core Intel Xeon 5500 processors
  * 384 Gigabytes of memory
  * Two small form factor SAS drives (raid 0 and 1)
  * Dual Converged Network Adapter slots

As CPU&#8217;s become more powerful, the host compression ratio&#8217;s (the amount of virtual machines you run on one physical blade) increases. The one thing is, you can only over commit your memory to a point. Once you are at that point you have to physically add more memory. Your only option with legacy server architectures is to add another physical server, pay for additional licenses and add more memory to it. Then add that server to the cluster and allow your virtual machines to utilize its additional resources in the pool.

The problem with this is a simple one, Cost. The problem was that the virtual machines needed more memory, but since there was a limitation on how much memory the legacy server could handle, it forces costs skyward to meet those memory needs. In this scenario if the customer had been using a full width Unified Computing blade the customer could have avoided purchasing an additional server and avoided the additional licensing and management cost associated with that additional server.

What does this balance out to in real costs? By allowing for higher host compression ratios there is the capability to avoid a significant amount of cost (50%+) in your compute layer. 

<span style="font-size: large;"><strong>Intel Xeon 5500 ( Code Named Nehalem-EP)</strong></span>

Intel&#8217;s next generation Xeon CPU (code named Nehalem) will be driving the Compute Blades. The Xeon 5500 signals Intel&#8217;s move away from the legacy &#8220;Front Side Bus&#8221; (FSB) architecture into what is called &#8220;Intel Quick Path Interconnect&#8221; (QPI). Intel&#8217;s Xeon 5500 with Quick Path Interconnect changes a couple key things from previous generation Xeon procesors.

  * high bandwidth, full mesh, routed interconnect between CPU&#8217;s instead of a low bandwidth bus
  * DDR3 vs DDR2 memory and moves the memory bank adjacent to the CPU&#8217;s for higher performance
  * I/O Hubs are now dedicated for network and storage interconnects

**First and Second Gen Xeon vs Xeon 5500 (Nehalem)**

[singlepic id=84 w=500 h=440 float=]**  
**

<p style="color: #ffffff;">
  .\
</p>

If you look at the picture above, where the last generation processors are to the left, and the processor that will be in the UCS is on the right, you will notice a couple key items. I think the most important items to point out is that the bandwidth in pretty much all directions is superior in this architecture. If you think about this as a network on your server itself, you can see how moving from a bus based network, to a full mesh routed network has significant performance advantages. Stay tuned for later posts where I will talk about some of these advantages in detail.

<span style="font-size: large;"><strong></strong></span><span style="font-size: large;"><strong>Hardware Assisted Virtualization</strong></span>

<span style="font-size: medium;"><span style="font-size: small;">One of most important new features that Intel is bringing to the table is the notion of hardware assisted virtualization. Intel has created a couple key technologies to address the following problems faced in virtual environments.</span></span>

<span style="font-size: medium;"><span style="font-size: small;">[singlepic id=85 w=500 h=440 float=]<br /> </span></span>

**<span style="font-size: medium;"><span style="font-size: small;">Processor Virtualization </span></span>**

<span style="font-size: medium;"><span style="font-size: small;">Currently to virtualize an operating system, we rely on the hypervisor (ESX, for example) to accomplish two key tasks &#8211; Ring Depriveleging and Context Switching. When we are talking about CPU overhead in virtual environments this is what we are talking about.<br /> </span></span>

**<span style="font-size: medium;"><span style="font-size: small;">Memory Virtualization</span></span>**

<span style="font-size: medium;"><span style="font-size: small;">Again, in current environments the hypervisor is used to abstract memory. ESX uses a technique called page table shadowing to virtualize the physical memory. This again however adds inefficiency to the process and shows up as virtualization overhead.<br /> </span></span>

**<span style="font-size: medium;"><span style="font-size: small;">I/O Device Virtualization</span></span>**

<span style="font-size: medium;"><span style="font-size: small;">As our virtual machines go to disk, we are again presented with a situation where the hypervisor has to abstract disks and networks presented tot he physical server, and connect these to the relevant virtual machines. Again, this shows up as virtualization overhead, lowering the efficiency of our virtual servers as well as introducing I/O sprawl.</span></span>

<span style="font-size: large;"><strong>Solving virtualization overhead problems</strong></span>

<span style="font-size: medium;"><span style="font-size: small;"><span style="font-size: medium;">[singlepic id=89 w=520 h=440 float=]</span></span></span>

<span style="font-size: medium;"><span style="font-size: small;"><span style="font-size: medium;"><span style="font-size: small;">With the Xeon 5500 on Cisco&#8217;s Unified Compute System blade you will be able to use processor features to solve the problems listed above. VT-X is used to extend CPU virtualization down to the physical CPU, Extended Page Tables, Cisco Memory Expansion and DMA remapping is used to speed remove memory access overhead from virtual network and I/O interfaces, and I/O devices sharing through VT-C is used to integrate the physical network with the virtual network transparently and with much less overhead. </span><br /> </span></span></span>

<span style="font-size: large;"><strong>Summary</strong></span>

<span style="font-size: medium;"><span style="font-size: small;">Cisco&#8217;s entry into the computing space is not a &#8220;me too&#8221; entry into a commodity x86 market. It is a well thought out strategic move unifying storage, network and compute functions in a unique way that will differentiate the Unified Computing System from other compute offerings. I expect some fierce debate of the upcoming months as competitors release products to compete. I feel that Cisco&#8217;s value proposition of a unified compute / network layer in the Data Center uniquely solves problems that most customers face. And at the end of the day, the vendor that can solve the customers problems is the vendor that will succede.</span><br /> </span>