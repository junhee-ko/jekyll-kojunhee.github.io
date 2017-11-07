---
id: 30
title: My CCIE Storage Shopping List
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/2006/12/06/my-ccie-storage-shopping-list/
permalink: /my-ccie-storage-shopping-list/
blogger_blog:
  - colinmcnamara.blogspot.com
blogger_author:
  - Colin McNamara
blogger_permalink:
  - /2006/12/my-ccie-storage-shopping-list.html
categories:
  - CCIE Storage
  - CISCO
  - Uncategorized
tags:
  - blog
  - C
  - CCIE
  - CISCO
  - cisco secure
  - Colin
  - Fibre Channel
  - HP
  - mds
  - Network
  - Router
  - storage
  - switch
  - vmware
---
My CCIE Storage Shopping List

Lets just start this out by saying, darn.. this is going to be expensive.  
Now that that is out of the way, lets get started. Cisco publishes the hardware that is in the Storage lab.

Here is the hardware summary &#8211;

<ul class="compact-bulleted">
  <li>
    Cisco Routers
  </li>
  <li>
    Cisco Catalyst Switches
  </li>
  <li>
    Cisco Secure Access Control System
  </li>
  <li>
    MDS 9506*
  </li>
  <li>
    MDS 9216*
  </li>
  <li>
    Port Analyzer Adapter
  </li>
  <li>
    JBOD
  </li>
  <li>
    RAID storage
  </li>
  <li>
    HBA
  </li>
  <li>
    3rd Party Fibre Channel Switch
  </li>
</ul>

My guess is that this equals a basic routed network with a CS-ACS server on the backend.  
It looks like there is also at least 1 pc with an HBA connected into one MDS. The one big question I have is on the connected storage.  
My guess is that Cisco&#8217;s JBOD reference = Fibre Channel connected storage, and the RAID array mentioned is connected to at least one server.  
If my guess is right then there is the 9506 and 9216 &#8211; (note, no I in the name) and a third party switch.

So lets start the shopping list.

1. Cisco Routers  
I have those coming out of the yinyang, no need to purchase anymore for this lab.

2. Cisco Catalyst Switches  
Mine are a little old, but I don&#8217;t expect a storage exam to have anything challenging in the switching arena. No need to upgrade there.

3. Cisco Secure Access Control System  
Thankfully Cisco provides VAR&#8217;s with NFR binders. ACS will be loaded on HMB-SERVER1 in a vmware image. No expenditure needed.

4. MDS 9506*  
Holy smokes, this is a lot of money. I have seen them on ebay for $8,000. This includes both sup modules. I would need to buy a line card, which I see going for about 1k. so $9000

5. MDS 9216  
Still bad, but not horrible. I just saw one on ebay for $5500. Depending on lab requirements it may be smart just to get to 9216&#8217;s. so $5500

6. Port Analyzer Adapter  
Best I can find is $2000 refurbished. I have a feeling practicing using this, and seeing the ethereal dumps is going to be integral to success. worst case this is 2k, best case beg or borrow $2000

7. JBOD  
Normally you are looking at 2-4k for one of these. My strategy is to find an old Netapp shelf, and low level format it. I found one on ebay that ends in 22 hours for $89. Sounds good to me.

8. RAID storage  
I am going with my guess that this is just to facilitate data transfers between storage and host. My tactic is to use the existing storage inside one of my servers. $0

9. HBA  
Interesting &#8211; Only one HBA .This can be up to $2000 to buy new. Luckily ebay is my friend. I found a qlogic 2340 card for $50. My kind of deal

10. 3rd party Fibre Channel Switch  
Luckily Brocade resells to everyone and their mother. IBM, Dell, HP, Compaq, ETC. I have found some Silkworm 2800&#8217;s for as low as $50 on ebay.  
I do have my eye on a 3800 that is going for $24 right now (I hope it stays low).

So how much is the damage?

$16,700

Holy smokes I could sell my truck just to buy the lab gear.

&#8211;Colin  
[Copyright ©2008 | Colin McNamara | CCIE 18233 | All Rights Reserved&#8221;][1]

<p class="blogger-post-footer">
  Colin McNamara<br /> CCIE #18233<br /> http://www.2cups.com<br /> &#8220;The difficult we do immediately, the impossible just takes a little longer.&#8221;
</p>

 [1]: http://www.colinmcnamara.com "Copyright ©2008 | Colin McNamara | CCIE 18233 | All Rights Reserved"