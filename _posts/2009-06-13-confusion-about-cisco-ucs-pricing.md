---
id: 657
title: 'Confusion about Cisco UCS pricing &#8211; Setting the Record Straight'
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/?p=657
permalink: /confusion-about-cisco-ucs-pricing/
aktt_notify_twitter:
  - yes
aktt_tweeted:
  - 1
categories:
  - CISCO
  - Cisco B Series Blades
  - Cisco UCS B200
  - Cisco UCS B250
  - Cisco Unified Computing System
  - Cisco Unified Computing System Managerm UCSM
  - cloud computing
  - Paginated
tags:
  - CISCO
  - Data Center
  - Fabric Extender
  - FCOE
  - FEX
  - Fibre Channel
  - hosting
  - Network
  - Power
  - Server
  - Technology
  - UCS
  - Unified Computing System
  - virtualization
  - vmware
---
I read an interesting article in the Channel Register written by Timothy Pricket Morgan today. In his article &#8211; <a href="http://www.channelregister.co.uk/2009/06/12/cisco_ucs_pricing_revealed/" target="_blank"><em>Cisco California pricing revealed, $3,000 for a blade with no innards</em></a> he attempts to position UCS as a horribly overpriced system where Cisco is egregiously marking up components. A pretty strong statement from his article is listed below &#8211;

<p style="padding-left: 30px;">
  &#8220;it looks like one of the key features not on the list of components for the California boxes is going to be a red discount pen&#8221;
</p>

Timothy references sources who have obtained a price list and shared it with *&#8220;El Reg&#8221;* . I wish Timothy would have contacted an actual Cisco Unified Computing System Advanced Technology Partner, because any partner that is involved in the launch could have explained to him the concepts of List price (List), Manufacturers Suggested Retail Price (MSRP), and Purchase or Buy price.

<img style="float: right;" title="Saving Money with Cisco Unified Computing System" src="http://www.colinmcnamara.com/wp-content/gallery/cisco-unified-computing-system/istock_000007893322small.jpg" alt="Saving Money with Cisco Unified Computing System" width="250" height="279" />

In this article I want to dispel the myths of server and network manufacturer pricing, demonstrate the true cost of building a data center with blade systems, and at the end provide a cost comparison between legacy server vendors options and Cisco&#8217;s Unified Compute System.

First, lets go over some the basic concepts of vendor pricing. At the end of this you should understand the difference between list price, manufacturers suggested retail price, and purchase price.

**List Price**

List price is a high level number that Cisco publishes weekly in its global price list. The purpose of this list price is to provide a uniform price list across all product sets that Cisco offers. The most important thing about list price is **NOBODY EVER PAYS LIST PRICE**. Let me repeat that again **NOBODY EVER PAYS LIST PRICE. **Are we clear? This is similar to list price on a car on the car lot. All list price provides is a starting point where a Cisco partner and a customer can negotiate a common discount and end up with something close to (generally at or below depending on technology type and yearly spend) MSRP.

**Manufacturers Suggested Retail Price (MSRP)**

This concept is something that anyone who has purchased a car before is familiar with. The number that is on the window of the car when you look on the lot is list price. The first number the dealer brings up lower then sticker is MSRP. Depending on the popular of the product, the competition in that particular space, and the negotiating power of the customer you will either pay that price, or some percentage below. For example if you are buying one new car you may have the negotiating power to get the price to drop 5% off of list. If you are buying 200 new cars (say a fleet) you have significantly higher negotiating power, and you may be able to drop the price by 15% of of list price.

In Networking Sales MSRP is significantly less then list price. A good exercise to see what this number is, is to find a device, say a WS-C3560E-12SD-E (3560 with 12 Gig SFP ports and 2 10 Gig ports) in the Global Price List. You have access to this at any partner level at <a href="http://www.cisco.com/dprg" target="_blank">www.cisco.com/dprg</a> . (my point here is that this is no big secret). As of Friday June 12 2009 the LIST price for this product is $19,995.

Now take that same part number &#8211; WS-C3560E-12SD-E and pop it into your google search window. Within the top four links I found this product for $12,434.15 . This price is for  pure fulfillment, with no value added consulting or design work from you local Cisco partner.

If you do the quick math, this price difference is equal to 38% off of list price. Come to your own conclusions, but it would be safe to say that this could be considered MSRP for Cisco products.

**Purchase / Buy Price**

Buy price is just that, the price at which the customer purchases (buys) the product. This is can be at MSRP, or if the customer is buying significant amounts of hardware at a time, or if there is a &#8220;special&#8221; (programs and incentives) going on the number could be slightly lower then MSRP.

**Percent off of list differences between legacy server vendors and networking vendors**

This is where the biggest confusion is coming from. Legacy server manufacturers  have set their list prices much closer to MSRP then networking vendors (remember, MSRP is the price where most customers purchase at).

Why is this? In the networking space, vendors have historically created their own processors, ASICS and boards. This means that the sales discussions are feature to feature. It also meant that you had to have a conversation with the networking vendor or networking partner to properly size your network devices and get a quote &#8211; which is around MSRP, not List price.

In the legacy server space, especially the majority of the x86 server space, the market has been essentially commoditized. E.G. &#8211; You can buy an intel based server with X amount of memory and hard drives that will perform roughly equally from any of the main manufacturers. That made it much easier for a sever admin to just pull a price off of the web and compare. So what the server vendors ended up doing is setting their list price  only slightly above MSRP.

What this translates to is the list price, between legacy compute vendors and Cisco will be drastically unequal. What is equal is MSRP, or the generally accepted purchase price by common customers.

**Why did Cisco set the list price of UCS higher then the legacy server manufacturers?**

**<img style="float: left;" title="Cisco's Pricing Strategies" src="http://www.colinmcnamara.com/wp-content/gallery/cisco-unified-computing-system/istock_why_salesman_000003413016xsmall.jpg" alt="Cisco's Pricing Strategies" width="250" height="242" />**For the vast majority of its sales, Cisco relies on what is called the channel model. This means that Cisco partners with local Value Added Resellers (VAR&#8217;s) who sell Cisco&#8217;s products and then provide consultative services to design and implement them in customer networks. Most customers who purchase any regular amount of Cisco product either have a general expectation that they will buy Cisco product at a certain percentage discount off of list and sometimes the partner and customer have entered into purchasing contracts which require that all Cisco product is provided at a specific discount off of list price.

If Cisco decided to set the List price at a small percentage lift over MSRP, this would cause a problem for the entire channel. This would be especially hard for any customer who had a contract to buy product at a specific discount. What would happen is contracts would have to be renegotiated, which generally takes months and is about as fun as pulling teeth.

The second reason for setting list price the for compute the same as list for network is quoting. Right now, if you buy hundreds of different Cisco devices through a reseller it is very likely that the discount is going to be the same across all products. This makes the mechanics of sales much simpler, because you don&#8217;t have a lot of math in the quote (this can cause errors). On the customer side, having one set discount makes it much easier to compare quotes and to ensure that they are getting the best deal possible. In short, sticking with Cisco&#8217;s current list pricing structure benefits both the customer and the partner.

Now that we have set the record straight on list price, MSRP, and Buy price, lets take a deeper dive into what components make up a blade system powered data center. And then we will compare the price structures of both.

**Components of all Blade Systems**

**<img style="float: left;" title="Cisco Unified Computing System" src="http://www.colinmcnamara.com/wp-content/gallery/cisco-unified-computing-system/cisco-ucs-ppt-redundant.jpg" alt="Cisco Unified Computing System" width="278" height="210" />**

Blade Server &#8211; The compute blade where commodity silicon elements such as the CPU and RAM are housed. As of writing this article, the latest high performance blades from all major server manufactures support two xeon 5500 processors (Nehalem) and DDR3 memory.

Mezzanine cards &#8211; These cards take the place of PCI-e cards in a rack form factor server. In a blade system these provide data network and storage network connectivity. They attach to the blade itself via proprietary connectors that implement either PCI-e 8 or 16 lane connectivity at the time of writing. In some cases other functions such as IO accelerators can also be attached in the mezzanine card form factor.

Blade Enclosure &#8211; This is functionally a tin can where eight to sixteen blades are placed. It also is used to provide a centralized power distribution fabric, as wells as slots for interconnections of data and storage network devices.

Data Network Modules &#8211; These are effectively ethernet switches that have been miniaturized to fit into the tight confines of a blade enclosure. Classically they have provided 1 gig connectivity to the servers, and 10 gig to the distribution layer, however with Nehalem processors and VMware there is a move towards presenting 10 gig connections to the server, and multiple 10 Gig connections into the distribution layer.

Storage Network Modules &#8211; The local disk in a blade server is classically anemic. To provide higher IOPS (input outputs per second) to disk, Fibre Channel connectivity is extended by taking SAN fabric switches and miniaturizing them to fit into the blade enclosure.

Data Network Distribution &#8211; If you have multiple blade enclosures there is a need to connect them together at a reasonably high bandwidth. To serve that need a variety of 10 Gig distribution switches are provided from all server manufactures at varying cost and performance levels.

Storage Network Distribution &#8211; Along the same lines of the data network distribution, SAN fabric switches have to aggregate up to a SAN distribution layer, or if the installation is reasonably large a &#8220;director&#8221; class SAN switch. This allows all the blade enclosures to see the same storage network, as well as providing for deterministic storage network performance as you scale out.

Management Infrastructure &#8211; All manufactures have a need to manage and monitor all of the devices that comprise their blade system. Many manufactures have multiple management modules per blade enclosure.

**Comparison of Costs &#8211; Cisco vs Legacy Server Manufacturers**

**<img style="float: left;" title="Calculator" src="http://www.colinmcnamara.com/wp-content/gallery/cisco-unified-computing-system/istock_calculator_000007118327xsmall.jpg" alt="Calculator" width="250" height="165" />**

The funny thing, is that many people have assumed that Cisco&#8217;s Unified Computing System will be priced higher then legacy server manufactures products. In my mind this is because they associate higher quality with higher price (basically the Mercedes vs Kia discussion). Here is something that will shock you &#8211;** it costs less to buy an entire blade system through Cisco then to buy from the legacy server manufacturers. **

When people hear this, they are puzzled. How can two server manufacturers, who buy their CPU&#8217;s from the same company (Intel) and their memory from the same fabs end up with different prices? The answer is elegance in engineering. Lets go through each of the elements of a blade system infrastructure and find out where the costs are. More importantly lets look at where Cisco has innovated to provide higher performance at a lower cost.

<div>
  <p>
    Blade Server &#8211; Legacy server manufactures and Cisco have almost identical MSRP for their compute blades. All server manufacturers buy the components of <em>currently shipping blade servers </em>from the same manufactures. I italicized currently shipping blade servers because I have used Cisco&#8217;s B-200 series blade for this comparison. This fall Cisco will be shipping the B-250 blade which further increases Cisco&#8217;s price advantage.
  </p>
  
  <p>
    Mezzanine cards &#8211; The legacy server manufacturers require two separate mezzanine cards to provide both storage and data network access. This is one area where Cisco is able to provide a superior product at a lower cost. Cisco has miniaturized the Converged Networking Adapters (CNA&#8217;s) that have been available for a year now, and made them available for their blade system. 1/2 the adapters results in less cost.
  </p>
  
  <p>
    Blade Enclosure &#8211; If you take the cost per blade (some manufacturers have 16 blade enclosures and some have 8 blade enclosures) this cost is pretty much equal between manufacturers.
  </p>
  
  <p>
    Data Network Modules &#8211; Legacy server manufactures have put switches, or virtualized IO cards (essentially switches with a different GUI) into their blade enclosures. Cisco has taken a new route and miniaturized a 10 Gig version of their Fabric Extender Modules (FEX). This results in the ability to provide the higher bandwidths required by new virtualization platforms at a much lower cost then the legacy manufacturers.
  </p>
  
  <p>
    Storage Network Modules &#8211; In legacy environments, a pair of separate SAN switches is required per blade enclosure. Cisco is leveraging it&#8217;s Unified Fabric technology to pass this SAN traffic over the same Fabric Extenders used for transmitting data. Cisco again is lowering costs by removing the requirement for SAN devices in each blade enclosure.
  </p>
  
  <p>
    Data Network Distribution &#8211; No matter what manufacturer you go with, you have to aggregate up all the blade enclosures into a high bandwidth, low latency network. Cisco has introduced the concept of a Fabric Interconnect. This is where all of the 10 Gig Fabric Extenders aggregate into. Again, this lowers the cost of building your blade system infrastructure.
  </p>
  
  <p>
    Storage Network Distribution &#8211; Right now this burden is shared between all server manufacturers. If Fibre Channel networking is required on any scale, a storage distribution layer is required. Cisco is however reducing the challenges of scaling this system by implementing Network Port Virtualization at the fabric interconnects.
  </p>
  
  <p>
    Management Infrastructure &#8211; Cisco has taken the independent management blade commonly found in legacy server manufacturers blade enclosures and centralized that functionality in the Fabric Interconnects. Again, we see the common theme of Cisco doing more with less. And when you have to purchase less components, you spends less money.
  </p>
</div>

**Dollars and Cents &#8211; How much is the cost difference**

I worked up two quotes recently. These quotes included all elements required to build an end to end blade system using both legacy server manufactures devices, and using Cisco&#8217;s Unified Computing System. I have broken out two scenarios.

****

**8 blade servers &#8211; Cisco wins with a savings of 11%**

In this scenario the cost of servers and enclosures were fairly equal. The cost savings started racking up as storage and data networking devices were included, as well as base management software was taken into consideration.

**320 blade servers &#8211; Cisco wins with a savings of 31%**

With 32o blade servers the same cost savings seen in the 8 server scenario were amplified. Economies of scale translated into significantly less devices being required to support the individual compute blades. This resulted in 31% savings compared to the legacy server manufacturers.

**Summing it up**

Cisco has entered into a highly competitive server market by taking an elegant approach to its blade systems. This approach lowers the purchase price of the UCS through reducing the amount of components compared to legacy server manufacturers. I know that there is a lot of misinformation flying around, and I hope this helps to set the record straight on the pricing of Cisco&#8217;s Unified Computing System.