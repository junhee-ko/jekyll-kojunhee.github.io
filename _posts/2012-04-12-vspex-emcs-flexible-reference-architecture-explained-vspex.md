---
id: 1142
title: 'VSPEX &#8211; EMC&#8217;s Flexible Reference Architecture Explained'
author: colinmcnamara
excerpt: "VSPEX is a pre-validated set of reference architectures currently focused around Server Virtualization (cloud computing if you want to church it up) as well as end-user computing (VDI/VXI/Application Presentation Solutions). It fills the gap in EMC's solution offerings that exists between a design and build your own solutions and their converged infrastructure product (VCE Vblock)."
layout: post
guid: http://www.colinmcnamara.com/?p=1142
permalink: /vspex-emcs-flexible-reference-architecture-explained-vspex/
categories:
  - CISCO
  - Cisco Unified Computing System
  - EMC
  - VSPEX
tags:
  - B-Series
  - C-Series
  - CISCO
  - Cisco Unified Computing System
  - cloud computing
  - Data Center
  - DESIGN
  - EMC
  - flexpod
  - hyper-v
  - NDA
  - NetApp
  - service provider
  - storage
  - switch
  - UCS
  - VBlock
  - virtualization
  - vmware
  - VSPEX
---
&nbsp;

What is VSPEX? There has been a bit of speculation floating around the industry the past couple of weeks regarding what EMC will be releasing. I have heard rumors spreading from the extreme of EMC create a new super version of VPLEX, to EMC creating a product wholly and completely competitive with Vblock ([mentioned here by CRN last week talking about a VMAX based VPLEX][1]). A few people, notable the folks at the register ([VSPEX article here][2]) have come quite a bit closer to the truth by calling out that a new reference architecture positioned to address the mid-market in a similar fashion to [NetApp&#8217;s FlexPod][3] offering.

### The truth about VSPEX

VSPEX is a pre-validated set of reference architectures currently focused around Server Virtualization (cloud computing if you want to church it up) as well as end-user computing (VDI/VXI/Application Presentation Solutions). It fills the gap in EMC&#8217;s solution offerings that exists between a design and build your own solutions and their converged infrastructure product (VCE Vblock).

[<img title="VSPEX-Option" src="http://www.colinmcnamara.com/wp-content/uploads/2012/04/VSPEX-Option-1024x432.jpg" alt="VSPEX Solutions Offering" width="502" height="211" />][4]

<div>
  <p>
    The idea behind VSPEX is to provide a customers complete virtualization solution, while allowing for flexibility in the selection of compute, virtualization and data protection (backup) technologies that best fit their needs and current environments.
  </p>
  
  <p>
    VSPEX is designed to allow for that flexibility of choice while removing the risk and lowering deployment times by deliver pre-validated tested reference architecture, as well as logical build guides similar to what is used to deploy and manage Vblock. The end result of this is to have a solution that scales to known capacities and can be deployed in a rapid reliable manner with build guides created by EMC and it&#8217;s ecosystem partners.
  </p>
</div>

### What components create VSPEX

[<img title="UCS-5548-VNX" src="http://www.colinmcnamara.com/wp-content/uploads/2012/04/UCS-5548-VNX-e1334213510463.jpg" alt="VSPEX test architecture" width="500" height="487" />][5]

**Networking** &#8211; VSPEX will be featureing Cisco&#8217;s Nexus 5548 Unified Port Switch as the networking component. This is the standard 10 gig switch used in Cisco&#8217;s other Validated Designs and is the standard platform for an aggregation layer for most Cisco based Data Centers.

**Compute** &#8211; Cisco Unified Computing System will be featured as the compute platform for VSPEX. For the mid market solutions that feature VNX storage Cisco B-Series blade centers will be recommend. For SMB focused solutions featuring VNXe storage Cisco&#8217;s C-Series servers will be featured.

**Unified Storage** &#8211; EMC VNX 5500/5300 Unified storage, supporting Fibre Channel, NFS and iSCSI will be offered for Mid Market solutions and VNXe supporting only IP protocols will be specified for SMB solutions.

**Server Virtualization** &#8211; Both VMware vSphere or Microsoft Hyper-V based validated and tested designs will be released. This is very interesting as both NetApp and EMC now have included Hyper-V as a supported scalable hypervisor. I personally have been a huge fan of VMware over the years, however I think that signs like this show that Hyper-V is increasingly penetrating both EMC and NetApp&#8217;s customer base.

**End-User Compute (VDI)** &#8211; Two solutions will be initially released. VMware View or Citrix XenDesktop. Both of these products are featured in Cisco&#8217;s VXI architecture and will now be featured in VSPEX. Is this the year of VDI? I would say yes.

**Data Protection** &#8211; The often forgotten, but always need backup and recover solution tied into any virtualization project will be EMC Avamar and or Data Domai

### How flexible is VSPEX

VSPEX is surprisingly flexible. The components specified in the architecture are explicitly called out as starting points to design around. You are allowed to substitute components as long as you stay within the sizing parameters and guidelines specified in each architecture document.

[<img title="Time to Adapt " src="http://www.colinmcnamara.com/wp-content/uploads/2012/04/iStock_000012497023Small-e1334216460679.jpg" alt="VSPEX Adaptation" width="500" height="398" />][6]

Personally this solves a big challenge that happens when selling a Vblock solution. Vblocks tend to be very rigid what your are allowed to do with them, and what and how something can be installed. This presents a challenge when a customer wants the speed of installation and single number support of a Vblock, but has requirements that drastically diverge from what Vblocks were designed for.  With VSPEX these customers can still have the safety and speed of delivery of a tested and validated solution, while benefiting from the flexibility of a reference architecture based solution.

### Is VSPEX competitive with Vblock

There is technically a bit of overlap in the solutions, however the two offerings are really targeted to completely different customer and workloads. While there are some smaller Vblocks out there, the majority of Vblocks sold have been focused towards higher end solutions at Enterprise and Service Provider customers.

VSPEX is targeted to fill the gap that Vblocks tend to miss, which is the Mid-Market and SMB space. That Mid-Market space is the same space that NetApp has had so much success with the FlexPod offering. I expect VSPEX to provide these Mid-Market and SMB customers options that were not available to them from a Vblock solutions.

### What is my verdict on VSPEX

EMC has brought together a strong reference architecture offering for the mid market with VSPEX. They are moving the ball one step forward by providing many of the benefits of Vblock in a flexible reference architecture delivered to Mid-Market customers. This is needed by EMC, Cisco and it&#8217;s channel partners and I fully expect it to be embraced by their joint customers.

&nbsp;

 [1]: http://www.crn.com/news/cloud/232800391/sources-emcs-new-vspex-reference-architecture-set-to-battle-netapp-vce.htm?pgno=1 "Getting it Wrong"
 [2]: VSPEX%20article%20here "VSPEX article"
 [3]: http://www.netapp.com/us/technology/flexpod/
 [4]: http://www.colinmcnamara.com/wp-content/uploads/2012/04/VSPEX-Option.jpg
 [5]: http://www.colinmcnamara.com/wp-content/uploads/2012/04/UCS-5548-VNX.jpg
 [6]: http://www.colinmcnamara.com/wp-content/uploads/2012/04/iStock_000012497023Small.jpg