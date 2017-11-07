---
id: 1225
title: 'VMware&#8217;s Acquisition of Nicira &#8211; VMware confirming the hypervisor is dead'
author: colinmcnamara
excerpt: |
  The hypervisor is dead, for VMware to stay relevant it has to continue innovating higher up the stack. The acquisition of Nicira will allow VMware to have a play in the service provider market and do just that.
  
  It also provides an avenue for VMware to port it's higher level applications to run on multiple hypervisors. This has the potential to slow flow of customers to free platforms like Hyper-V and OpenStack. 
  
  While this isn't the best thing for the Cisco relationship, the reality of the matter is that VMware and Cisco have an "Open" relationship where both companies work with many others. I don't see this relationship changing in the long run.
layout: post
guid: http://www.colinmcnamara.com/?p=1225
permalink: /vmwares-acquisition-of-nicira-vmware-confirming-the-hypervisor-is-dead/
categories:
  - CISCO
  - Cisco UCS
  - OpenStack
  - Unified Computing
  - virtualization
  - vmware
  - vSphere
tags:
  - CISCO
  - Nicira
  - Openflow
  - openstack
  - vmware
---
VMware recently announced its intent to acquire Nicira for 1.2 billion dollars. This acquisition is of interest because it clearly signals **VMware&#8217;s abandoning of the Hypervisor as a differentiating platform.**

<img title="VMware-tombstone.jpg" src="http://www.colinmcnamara.com/wp-content/uploads/2012/07/VMware-tombstone1.jpg" alt="VMware tombstone" width="500" height="300" border="0" />

Yes, the hypervisor is commodity now. Whether it is ESXi, Hyper-V, Xen or KVM. You can take multiple operating systems and virtualize them on one CPU, share memory as well as do a live migration between hosts on all platforms.

Not only have commonly used features listed above become available across many platforms, but in some cases open source technologies such as KVM be more extensible then VMware&#8217;s product.

**What is VMware thinking?**

For the past couple years, VMware has been investing in technologies outside of the hypervisor. Some of this include Cloud Automation, Virtual Desktop, Application security and control, and Operations and Management.

These investments are smart, because it transforms the conversation from a discussion about hypervisors (which is a hard one to win on its own merits) to a discussion about the value add of all of the products that VMware offers.

Bundling of products and services is business 101 when your product becomes commoditized. Cisco does it by integrating all aspects of their product lines, EMC does it by offering a range of integrated Tier 1-4 storage and backup solutions, and VMware does it by offering significantly more then a hypervisor.

**I believe that this is the first step in VMware integrating their services into NON-ESXi hypervisors. Here is why &#8211; **

A few key concepts have emerged to be true in the virtualization market

1. Integrating multiple hypervisor support into their management platform (Systems Center Operations Manager &#8211; SCOM) is something customers want.

2. Customers are willing to utilize &#8220;Free&#8221; hypervisors such as Hyper-V or KVM / Xen for at minimum second or third their applications. And in some cases such as cloud service providers they are using these (specifically KVM and Xen) for their tier one virtualization.

3. The Cloud Service provider market is booming. It is not possible to compete on cost in that market while running on anything but Open Source hypervisors.

What the acquisition of Nicira gives Nicira is an integration point between all of the rich applications that have been developed since ESXi and Hyper-V, Xen and KVM (OpenStack).

Nicira already has plugins and to each of those platforms, providing not only a richly developed code base, but a conduit for linking disparate clouds together.

**Does this signal an end to the honeymoon between VMware and Cisco?**

The partnership between VMware and Cisco has been one based on mutual benefit, not mutual exclusivity.

The fact of the matter is that Cisco has been working with multiple Hypervisor&#8217;s for a long time now. ESXi, Hyper-V, Xen and KVM are all supported platforms on their Unified Computing Platform (UCS). Just the same as VMware was working with HP and Dell long before Cisco started making servers.

If you look close, you will notice that Cisco has been a major player in the OpenStack project. So much that there is [**EXTREMELY RICH integration with OpenStack&#8217;s Quantum Networking service **][1]in both UCS and the Nexus switching platform.

What this shows is that Cisco is presenting itself as a network and systems platform for Virtualization software manufacturers to leverage. Nicira has networking functions, but then so does the distributed vSwitch. At the end of the day, logical switching still needs physical devices. This is still a place where Cisco can and will play &#8211; As an arms dealer to software manufacturers

**Summing it all up**

The hypervisor is dead, for VMware to stay relevant it has to continue innovating higher up the stack. The acquisition of Nicira will allow VMware to have a play in the service provider market and do just that.

It also provides an avenue for VMware to port it&#8217;s higher level applications to run on multiple hypervisors. This has the potential to slow flow of customers to free platforms like Hyper-V and OpenStack.

While this isn&#8217;t the best thing for the Cisco relationship, the reality of the matter is that VMware and Cisco have an &#8220;Open&#8221; relationship where both companies work with many others. I don&#8217;t see this relationship changing in the long run.

&nbsp;

&nbsp;

 [1]: http://wiki.openstack.org/cisco-quantum