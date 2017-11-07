---
id: 1275
title: 'Scale Computing HC3 &#8211; Hyper-Converged Server, Storage, Virtualization'
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/?p=1275
permalink: /scale-computing-hc3-hyper-converged-server-storage-virtualization/
categories:
  - open source
  - OpenStack
  - scale computing
  - techfieldday
  - virtualization
tags:
  - '#techfieldday'
  - gpfs
  - kvm
  - opensource
  - openstack
---
**Companies using OpenSource virtualization in their unified products targeting the mid market**

I have been saying that we will start seeing Open Source virtualization technologies in two different areas of the market (signs the world is changing). These are web service providers and the small to medium business (SMB)

The web service providers have already long ago chosen open source hypervisors for their platforms (Amazon = Xen, Many others KVM, etc etc). Where Open Source Virtualization hasn&#8217;t shown up yet is  small business (250 users and below).

I should say, this hadn&#8217;t show up until recently….

<div>
  <strong><strong>Accessible OpenSource Virtualization and Scale Out Storage technology with Scale Computing</strong></strong>
</div>

<p style="text-align: center;">
  <a href="http://www.colinmcnamara.com/wp-content/uploads/2012/09/scale-hc3.jpg"><img class="aligncenter  wp-image-1277" title="Open Source Server Storage Virtualization" src="http://www.colinmcnamara.com/wp-content/uploads/2012/09/scale-hc3-1002x1024.jpg" alt="Open Source Server Storage Virtualization" width="500" height="500" /></a>
</p>

Scale computing started as a storage company with scale out unified storage. They have been shipping a consumer friendly implementation of GPFS (a horizontally scalable files system that is notoriously hard to configure) since 2009. They have been nipping at the heals of Dell and HP&#8217;s low end product lines, coming in with a competitive product at a fraction of the price.

They are  lowering the technical barrier to entry of open source virtualization platforms by putting a pretty and accessible wrapper around open source virtualization software and scale out storage software with its new Hyper-Converged virtualization platform &#8211; HC3 (hypercube for the nerds out there) product.

**What is a hyper-converged platform**

Quite simply a hyper-converged platform is a server with storage, virtualization and networking software all rolled up into one. Think of a FlexPod or VSPEX all squished into one box.

**Open Source Virtualization used in Scale HC3**

Guess what, you can run a virtual machine on many technologies including, but not limited to VMware. One of these technologies which is widely used is Kernel-based Virtual Machine. Here is the kicker, it is Open Source. That means that it is free. It is Open Source, which generally means it is hard to configure for the common admin. That is where the next piece comes in.

**An actual usable portal in front of Open Source virtualization  
**

<p style="text-align: center;">
  <a href="http://www.colinmcnamara.com/wp-content/uploads/2012/09/hc3_ui_lg.jpg"><img class="aligncenter  wp-image-1279" title="Scale HC3 web portal" src="http://www.colinmcnamara.com/wp-content/uploads/2012/09/hc3_ui_lg.jpg" alt="Scale HC3 web portal" width="491" height="369" /></a>
</p>

This is the missing piece in most Open Source or free implementations of server or virtualization. KVM is awesome, GPFS works well. Both are extremely hard for your average desktop / phone / network / single IT guy for all things that exist in small companies to implement.

The portal in HC3 puts a nice GUI wrapper on this technology and makes it consumable in a click click next fashion. Is it vSphere? Absolutely not. What it is, is a way to handle simple things running a windows VM, or taking a backup, or replicating your data somewhere else.

**Why am I talking about Scale?**

Full disclosure, I met their CEO and CTO at an industry experts discussion a while back. The context of the discussion was wide ranging, but generally focused on the evolving cloud computing and virtualization markets. Even though they run a software/hardware company, and I manage a line of business at a systems integrator, many of our views lined up.

One of the views that we share is that small business will start consuming hyper-converged (server, storage, network all on one server) virtualization solutions based off of open source or free technology. The key worlds to pay attention to here are using open source or free technology.

Fast forward to the week of VMworld. I was invited by [Stephen Foskett][1] to participate in the [#techfieldday round table at VMworld. ][2] Low and behold, there are the guys from Scale ready and armed to have a nuts and bolts technical discussion of their product internals and go to market. Needless to see I was able to get my nerd on.

The reason I think Scale is worth talking about is because they already penetrate the low end of the commercial market (SMB) with their scale out storage product. And now are shipping  a product that takes free or open source technology and packages it in a way that the common man can implement a small infrastructure on it. Not only do I think the direction they are taking their company is right, but they are shipping products to make it happen.

**Who should be worried about Scale?**

Dell has made a business out of making low cost servers. In the past few years companies like SuperMicro and SGI(Rackables) have taken that tittle as their own. Dell has evolved by acquiring low cost storage and networking solutions and selling them into the SMB market.

I think that the fact that Dell acquired (and not developed) its low cost storage offerings will paint it into a corner as Scale and other companies like it compete in the field with a solution that is equivalent in function, but a fraction of the cost. Eventually as these as these hyper-converged solutions gain acceptance other manufacturers like Cisco and HP may start to see a bit of competition, but are likely to

**Want to learn more?**

[Stephen Foskett&#8217;s View on Scale HC3 ][3]

[Tech Field Day round table on Scale][4]

[IBM GPFS &#8211; Scalable File System in Scale HC3 ][5]

[Kernel-based Virtual Machine &#8211; KVM, The open source hypervisor used in HC3][6]

[Scale Computing HC3][7]

 [1]: http://blog.fosketts.net/
 [2]: http://techfieldday.com/event/rvmwu12/
 [3]: http://blog.fosketts.net/2012/08/28/scale-computing-hc3-converged-infrastructure/
 [4]: http://techfieldday.com/appearance/scale-computing-roundtable-at-vmworld-us-2012/
 [5]: http://www-03.ibm.com/systems/software/gpfs/
 [6]: http://www.linux-kvm.org/page/Documents
 [7]: http://www.scalecomputing.com/