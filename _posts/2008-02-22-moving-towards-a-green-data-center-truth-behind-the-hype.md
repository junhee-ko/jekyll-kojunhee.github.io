---
id: 97
title: 'Moving towards a Green Data Center &#8211; Truth behind the hype'
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/2008/02/22/moving-towards-a-green-data-center-truth-behind-the-hype
permalink: /moving-towards-a-green-data-center-truth-behind-the-hype/
categories:
  - CISCO
  - DC3.0
  - efficiency
  - Green Data Center
tags:
  - 
  - C
  - CISCO
  - Data Center
  - eplus
  - Green Data Center
  - HP
  - MPLS
  - Network
  - network infrastructure
  - 'PG&amp;E'
  - Power
  - Provider
  - service provider
  - switch
  - virtualization
  - vmware
---
Eplus, Cisco, Hewlett Packard and PG&E held a luncheon this last Friday focused on Green Data Center. I&#8217;ll be the first to admit that at first I thought &#8220;green&#8221; Data Center initiatives were just political and corporate marketing initiatives. I thought they saw Al Gore give some rocking presentation and decided it would be great to market their products as &#8220;green&#8221; while continuing to spew toxins and club baby seals in their manufacturing plants.

I was wrong, the Green Data Center is not about saving baby seals, it is about saving cold hard cash. Saving the world is just a nice side benefit.

That being said, saving cold hard cash is a very important discussion item in any IT Operations group as they are normally seen as a cost center. For them, a penny saved is literally a penny earned. Not only can you save money by not paying for power, but PG&E will actually has a budget to pay you NOT to use their power. Most people here this and get a puzzled look on their face. &#8220;why would the power company, who makes money on power, not want me to buy it from them?&#8221; The answer is that Californians use more power then PG&E can produce at peak times. When they have to buy it from another state it can cost them 10 times or more then they charge us. This is the reason why PG&E will pay you to use less. Each penny they give to the consumer for saving a watt, saves them 4 pennies (80% return on investment).

**Great, PG&E saves money by giving it to me. How do I get this cash? Well there are a couple ways to get this.**

  1. Incentives for new buying new energy efficient servers
  2. Rebates for moving to virtualized servers
  3. Rebates and incentives for moving to thin client desktop systems
  4. Audit teams for cooling and power if your Data Center is 10,000 square feet or more
  5. Incentives for airflow control systems
  6. Incentives for high efficiency UPS and power distribution systems
  7. Technical services for cooling system evaluation (PG&E funded)

That is a pretty comprehensive list of how to get money from the power company, but you can save even more money buy not using the power in the first place. Not unsurprisingly this starts with the server.

First thing you can do, is virtualize, virtualize, and virtualize some more. For most people this means VMware. For others this may mean Xen, or Microsofts virtualization product. Whatever flavor you chose, the key message is to consolidate from many servers to few. A server sitting &#8220;idle&#8221; still pulls 50% of its max current. Now, howe many servers do you have that are just sitting there? My guess is a large amount. By virtualizing these servers, you allow them to be stacked onto high performance server that can be run at a higher utilization. This lowers the over all power utilization for your DataCenter. Another side benefit is that ever watt that you remove from a server, you get another watt removed from your cooling.

These same virtualization techniques can also be applied to your network devices, which account for 6 to 12 percent of your datacenters power draw.

Ask yourself a few questions

  * &#8221; Do I need 4 different firewall clusters?&#8221;. It is likely that these are leftovers from organic growth, and that you could consolidate them into virtual firewalls on a more efficient chassis (ASA comes to mind).
  * &#8221; Do I need to maintain physically separate infrastructure?&#8221;. There are technologies like MPLS, VFR-Lite, Virtual Switching and more that allow you to consolidate onto a shared network infrastructure, taking a service provider approach to providing transport in your network.
  * &#8221; Am I running old inefficient gear?&#8221;. Power supplies have increased in efficiency over the last few years. There may be a good return on investment for you to upgrade.
  * &#8221; Can I consolidate into larger chassis?&#8221;. Ask the question, which is more efficient &#8211; a closet full of 3560&#8217;s or a 4507? There is efficiency in scaling out.

I hope that reading this has caused you to ask some questions, and maybe look at the larger impact of your network operations on both the ecosystem and your operational expenses. With these questions in hand, you might want to talk to PG&E and your Cisco / HP parter about going &#8220;Green&#8221; in the data center.