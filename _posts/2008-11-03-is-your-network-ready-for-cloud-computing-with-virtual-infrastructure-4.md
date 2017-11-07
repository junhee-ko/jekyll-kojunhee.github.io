---
id: 273
title: Is your network ready for Cloud Computing with Virtual Infrastructure 4?
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/?p=273
permalink: /is-your-network-ready-for-cloud-computing-with-virtual-infrastructure-4/
aktt_tweeted:
  - 1
categories:
  - CISCO
  - cloud computing
  - DC3.0
  - FCOE
  - Fibre Channel Over Ethernet
tags:
  - cloud computing
  - VCP
  - vi4
  - vmware
---
Cloud computing is coming whether you like it or not. VMware&#8217;s next release , Virtual Infrastructure 4 (Vi4) is going to change how applications are fundamentally delivered in your Data Center. But what does that really mean to you as a network and systems architects?

**First and foremost it is important to discuss how many networks are right now (click for larger images)**

Figure 1.1

[<img class="ngg-singlepic ngg-center" src="http://www.colinmcnamara.com/wp-content/gallery/vmware/thumbs/thumbs_commen-current-hybrid_0.jpg" alt="Cisco VMware Data Center" />][1]{.thickbox}

This is a pretty common setup, with 80% of so of systems still physically attached to a mix of 100 and 1000 Megabit access layer switches. The other 20% of virtual systems are attached as through blade center switches with 10 gig to distribution or larger (8-16 core) systems with bundled uplinks to the distribution switches. Service aggregation such as firewall, load balancing, and wan acceleration , image deployment, monitoring / management and other key Data Center services generally provisioned off 1000 Megabit ports in the distribution.

Last but not least, a shadow storage network runs connected to a small percentage of physical servers, and connected to all of the virtual servers via Fiber Channel, iSCSI, or NFS presentation. One thing to keep in mind that all of these elements may not be configured in the &#8220;optimal&#8221; SRND setup, but it is something that you can expect to see in a real life network today.

**What&#8217;s so special about Vi4 Application vServices ?**

Figure 1.2

[<img class="ngg-singlepic ngg-center" src="http://www.colinmcnamara.com/wp-content/gallery/vmware/thumbs/thumbs_cloud_diagram_510x272.gif" alt="cloud_diagram_510x272.gif" />][2]{.thickbox}

The one new feature that is going to throw your network on its heels is vApp. Imagine if any application could be installed on any server in any location of your network at any time. What vApp enables you to do is create a portable application, similar to a Java application that installs in your web browser. But this application can be dynamically deployed to any virtual system in your Data Center as needed in response to a new application request, or the need to dynamically scale an application. What this means to us as network engineers is that any corner of our networks where virtualization is present can become a hot spot for critical application flows. This introduces a new dynamism to our fabrics which wasn&#8217;t there before, and frankly many networks are not equiped to handle it successfully.

Currently, to provide virtual machine redundancy we have VMware HA, where we both monitor the availability of a virtual machine. If there is a problem we can restart that virtual machine on another ESX host. With Application vServices there are many new elements and traffic flows. The two most important ones are vLockstop and vCenter Data Recovery. VMware is taking high availability to the next level by keeping a hot standby VM running on a second physical ESX server. If you think about it, you now are adding both additional latency sensitive heartbeat traffic as well as creating a situation where your storage traffic flows can be highly volatile. Additionally vData Center Recovery will be throwing traffic in new and interesting ways across your links.

**Adjusting your network designs to deal with the cloud**

Figure 1.3

[<img class="ngg-singlepic ngg-center" src="http://www.colinmcnamara.com/wp-content/gallery/vmware/thumbs/thumbs_scaled-out-current.jpg" alt="scaled-out-current.jpg" />][3]{.thickbox}

First and foremost application virtualization needs a front end, in network engineering circles we have been handling this successfully for a long time with content switches (load balancers). These provide the logical rallying point for dynamic cloud applications. Since more and more systems will be utilizing these services it is important to ensure that your current content switches have headroom to grow, and if you don&#8217;t have any content switching capabilities, it is probably time to take a look at adding them to your data center.

Since applications can exist in any corner of the network, dynamic provisioning of storage and network connections has become critical. Maintaining &#8220;shadow&#8221; storage networks can provide some dynamic access to storage, however it is now becoming advantageous to virtualize your storage fabric along with your systems and network devices. Fibre Channel Over Ethernet (FCOE) provides just that.

If you look at figure 1.3 above, you will notice a new color introduced into the diagram, as well as the &#8220;shadow&#8221; storage network removed. This is possible because all the orange links run Data Center Ethernet (DCE) which provides a lossless path for FCOE to follow. The ESX servers now only connect into the Nexus 5000 switches. As you can see, we also have removed the shadow storage network, as it is now consolidated onto our new data center fabric. There may be use cases where we need to extend classic fibre channel connectivity out to certain hosts, and we can do that of the Nexus 5000. However if all possible it is advantageous to utlize FCOE to gain storage mobility and higher bandwidth for your hosts.

You may notice that our uplink counts have doubled. Since we are moving both storage and data traffic over the same links, as well as supporting vMotion and other bandwidth intensive network applications it is time to make the push to port channeled 10 gig adapters. Luckily prices have dropped considerably, where it is not cheaper to use 10 Gig then to bundle 8 1 Gig adapters together.

Last but not least you will notice the core switching is a different color. This is because the Nexus 7000 has found its home in the data center. I wont go to deep into the nexus as that is an article in and of itself. What I will say is that it is the best platform to use to aggregate the amount of 10 Gig links that are populating the data center in a highly available fashion. If you want to learn more about the 7000 I recommend reading these previous articles [here][4] [here][5] and [here][6], as well as [Cisco&#8217;s Data Center Switching page.][7]

**Your network once Virtual Infrastructure 4 (Vi4) and the Nexus 1000V are released  
**

Figure 1.3

[<img class="ngg-singlepic ngg-center" src="http://www.colinmcnamara.com/wp-content/gallery/vmware/thumbs/thumbs_scaled-out-current-future.jpg" alt="scaled-out-current-future.jpg" />][8]{.thickbox}

Fast forward to early summer 2008 VMware Virtual Infrastructure 4 (Vi4) and Cisco&#8217;s Nexus 1000V are released. Of course a new major version of VMware running your compute cloud, application vServices are in effect, vLockstep is running, and many other features that go with the platform such as the Nexus 1000V.

The Nexus 1000V brings a long missing feature to the Data Center, a defined network edge. Since VMware has taken hold in the Data Center, the boundary layer between the virtual machine and the network has devolved to a dumb bridge running in the memory of a ESX server. Installing the Nexus 1000V in your ESX servers creates a virtual switch with interface counters, pvlans, access controls, QOS and many other features that are critical to operating a Data Center. [(check out a previous article about the Nexus 1000V)][9].

**Enjoying the fruits of our labors  
**

Cloud computing in general, and specifically Virtual Infrastructure 4 have specific benefits that will drive efficiency and agility in IT as a whole. The mechanisms for these benefits will put increasing load on the storage and data networks in your Data Center. It is our responsibility as network architects to take a proactive stance and provision a network with the immediate future in mind. Luckily planning and preparing for these changes in advance have both benefits for our current infrastructure, as well as allowing us to enjoy the fruits of our labors as Cloud Computing changes from a buzz word to a reality.

 [1]: http://www.colinmcnamara.com/wp-content/gallery/vmware/commen-current-hybrid_0.jpg
 [2]: http://www.colinmcnamara.com/wp-content/gallery/vmware/cloud_diagram_510x272.gif
 [3]: http://www.colinmcnamara.com/wp-content/gallery/vmware/scaled-out-current.jpg
 [4]: http://www.colinmcnamara.com/2008/02/07/usability-features-in-ciscos-nexus-7000
 [5]: http://www.colinmcnamara.com/2008/01/28/cisco-nexus-7000-datacenter-switch-released-welcome-to-datacenter-30
 [6]: http://www.colinmcnamara.com/2008/02/07/me-and-the-nexus-7000-last-week-at-the-data-center-vt
 [7]: http://www.cisco.com/en/US/products/ps9441/Products_Sub_Category_Home.html
 [8]: http://www.colinmcnamara.com/wp-content/gallery/vmware/scaled-out-current-future.jpg
 [9]: http://www.colinmcnamara.com/2008/09/16/cisco-releases-nexus-1000v-virtual-switch-for-vmware