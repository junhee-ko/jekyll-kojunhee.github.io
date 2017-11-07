---
id: 1191
title: 'Cisco Open Networking Environment &#8211; onePK OpenFlow and OpenStack'
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/?p=1191
permalink: /cisco-open-networking-environment-onepk-openflow-and-openstack/
categories:
  - CISCO
  - Cisco Live US CLUS
  - OpenFlow
  - OpenStack
tags:
  - CISCO
  - Cisco open
  - onepk
  - Openflow
  - openstack
  - quantum
---
Today Cisco is announcing their formal entrance into the SDN (Software Defined Network) market with the introduction of Cisco Open Networking Environment.

[<img class="aligncenter size-full wp-image-1196" title="Cisco One Networking Environment" src="http://www.colinmcnamara.com/wp-content/uploads/2012/06/Screen-Shot-2012-06-13-at-8.26.15-AM-e1339601285456.png" alt="Cisco One Networking Environment" width="500" height="225" />][1]

So what is this Open Networking Environment? Is is just another marketecture slideware play, or is the more meat to it? Lucky for us there is actually some meat to this release. So much so that two of the three area&#8217;s you can actually see working deep down in the Cisco booths at the world of solutions.

[<img class="aligncenter size-full wp-image-1198" title="Cisco Open Networking Portfolio" src="http://www.colinmcnamara.com/wp-content/uploads/2012/06/Screen-Shot-2012-06-13-at-8.44.35-AM-e1339602369515.png" alt="Cisco Open Networking Portfolio" width="500" height="224" />][2]

**Cisco OnePK &#8211; Standardizing the programmatic interfaces across Cisco&#8217;s networking products**

The first, onePK is something that I am personally very happy to see (Rick Davis and I proposed this to Cisco&#8217;s Routing Group during the Partner Technology Advisory Board in 2008). OnePK is a unified SDK (Software Development Kit) across IO, IOS-XR and NX-OS. What this will allow is simplification of deployment of configurations, changes, and operations and maintenance flows across a diverse suite of network products.

Personally, this is is a close tie for the 1000v on OpenStack as my favorite part of this release. Over the past few years I have built the some of the largest Data Centers on earth. Automating the deployments for these installations requires entirely to much Expect scripting, and still leaves a lot of custom coding to push and pull changes and statistics out of running equipment. OnePK should drastically simplify this process, and allow me personally to consolidate a large amount of deployment code into one simplified interface standard.

**Cisco&#8217;s OpenFlow Controller and OpenFlow Agent**

It is official, Cisco is creating an OpenFlow controller. What is even more interesting, is that I heard a rumor that if you ask nicely and go deep into the Cisco booth at the world of solutions you may actually get a sneak peak at one in action.

**Cisco Virtual Overlay Solutions &#8211; 1000v on everything**

[<img class="aligncenter size-full wp-image-1200" title="Cisco 1000v on everything" src="http://www.colinmcnamara.com/wp-content/uploads/2012/06/Screen-Shot-2012-06-13-at-8.46.05-AM-e1339602479977.png" alt="Cisco 1000v on everything" width="500" height="202" />][3]

This gets really interesting. One thing many people may have not noticed is that Cisco has been contributing code like crazy to the Quantum Networking Stack for OpenStack. Anytime I see a manufacturing committing that amount of code, you know something is up.

Well, now it is public, official, and we can all talk about it. Cisco is taking the Nexus 1000v and making it WAAAAY more useful. They are developing hooks for XEN, KVM, Hyper-V as well as continuing VMware support. That isn&#8217;t the cool part though. What they are doing is utilizing the network hypervisor to control and redirect flows across a many provider environments.

In the end what this will allow is the extension and linkage of cloud environments across disparate network and virtualization vendors. In short, linking your clouds through software only.

**My thoughts**

This release is a big milestone for Cisco. The Open Networking &#8220;movement&#8221; is significant to Cisco  in a similar way that Linux was significant to Sun. Sun went out of business (acquired by Oracle) because they didn&#8217;t embrace &#8220;Open&#8221; movements and layer on their unique value add. I believe what Cisco announced today is a very smart move, and will allow Cisco to stay meaningful as Networking, Systems and Clouds take a more Open Source / Stack / Flow flavor.

**Want to learn more?**

OpenStack Quantum

http://wiki.openstack.org/Quantum

Omar Sultan (Cisco) should be posting interesting content on the Cisco DC Blog

[http://blogs.cisco.com/category/datacenter][4]

Nice write up at CRN

http://www.crn.com/news/networking/240001990/cisco-live-new-developer-tools-details-on-sdn-strategy-emerge.htm

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

 [1]: http://www.colinmcnamara.com/wp-content/uploads/2012/06/Screen-Shot-2012-06-13-at-8.26.15-AM.png
 [2]: http://www.colinmcnamara.com/wp-content/uploads/2012/06/Screen-Shot-2012-06-13-at-8.44.35-AM.png
 [3]: http://www.colinmcnamara.com/wp-content/uploads/2012/06/Screen-Shot-2012-06-13-at-8.46.05-AM.png
 [4]: http://blogs.cisco.com/category/datacenter "Cisco Data Center Blog"