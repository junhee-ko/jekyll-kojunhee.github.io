---
id: 130
title: 'Simplifying remote site security with Cisco&#8217;s new video surveillance modules on the ISR'
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/?p=130
permalink: /remote-site-security-cisco-analog-video-gateway-video-management-storage-system-network-modules-on-the-integrated-services-router-isr/
aktt_tweeted:
  - 1
categories:
  - 4s ranch rancho bernardo san diego witch fire evacuated
  - CCIE
  - CISCO
  - security
  - sun
  - Technology
tags:
  - archived footage
  - C
  - camera control
  - CCIE
  - center infrastructure
  - CISCO
  - cisco secure
  - Colin
  - Data Center
  - dust mites
  - encoders
  - Gadget
  - hardware replacement
  - HP
  - ip cameras
  - isr
  - legal
  - life on mars
  - linux
  - management infrastructure
  - mars
  - mitiigation
  - Network
  - network storage
  - Pic
  - Power
  - Router
  - security
  - security environments
  - security infrastructure
  - storage
  - storage system
  - support contract
  - surveillance systems
  - switch
  - Technology
  - threat
  - two choices
  - video encoding
  - video management
  - video streams
  - video surveillance
---
One giant pain I have always faced when working with high security environments is dealing with surveillance systems. They are a necessary and required part of your security infrastructure. However they just never seem to integrate as well as your network, storage, or server devices.

When I work with data center infrastructure I expect the following &#8211; clean, remotely manageable, secure devices that runs on the same power and similar cabling, and everything can have a 24x7x4 support contract for hardware replacement. For the most part, you get this when dealing with Cisco, HP, Sun and similar manufacturers.

More often then not (with a few very cool exceptions), when I run into video surveillance infrastructure the video management infrastructure runs on some random third tier manufactured server. It never fails that the video management software is on Windows (normally XP or win2k). I have even seen some systems where the vendor requires you to have a session open to run the software.

And then when you get to the encoders themselves, it never fails. You have two choices.

  1. The Uber package that can run a Casino, Identify and track dust mites , and if you point it at space, determine if there is life on mars.
  2. Individual dinky encoders that run one or two camera&#8217;s each. They have limited encoding choices, limited camera control, no remote management, and normally run on 110 volt system that require different power distribution then the 220 that is common in systems today.

**Cisco&#8217;s answer to this mess**

Cisco has released both a video management solution, as well as a video encoding solution in a network module form factor for the Integrated Services Router (ISR).

[<img class="ngg-singlepic ngg-none" src="http://www.colinmcnamara.com/wp-content/gallery/cisco-surveillance/thumbs/thumbs_cisco-vmss-network-module-internal-view.jpg" alt="cisco-vmss-network-module-internal-view.jpg" />][1]{.thickbox}

The first part of this system, the Video Management and Storage System (VMSS) module fills the following roles &#8211;

  * Management of multiple video streams from one interface, including IP cameras, 3rd party encoders, and streams from Cisco&#8217;s video encoding module
  * Streaming of live and archived footage through a web browser interface
  * This one is pretty cool &#8211; The module can mount external storage via iSCSI. So, in addition to its 160 gig internal drive, you can mount a filer and utilize external storage to scale the system.
  * &#8220;fast forward&#8221; to events, as well as notify security and other personnel through SMS and email

<p style="text-align: left;">
  <p style="text-align: left;">
    <a class="thickbox" href="http://www.colinmcnamara.com/wp-content/gallery/cisco-surveillance/ip-surveillance-both.jpg"><img class="ngg-singlepic ngg-none" src="http://www.colinmcnamara.com/wp-content/gallery/cisco-surveillance/thumbs/thumbs_ip-surveillance-both.jpg" alt="ip-surveillance-both.jpg" /></a>
  </p>
  
  <p style="text-align: left;">
    The second part of the system (the module on the left in the picture above) is the Analog Video Gateway Network Module (EV-IPVS-16A). It has a couple functions &#8211;
  </p>
  
  <ul>
    <li>
      It can take up to 16 analogue video inputs and encode them with MJPEG or MPEG4 codecs
    </li>
    <li>
      You can use the first two ports to output video to a external monitors
    </li>
    <li>
      If you are using MPEG4, it can be used as a motion detector (handy for fast forwarding to important events, or triggering alerts)
    </li>
    <li>
      It can control pan and tilt cameras. This is good for pointing the camera at the janitor unplugging your servers each night to vacuum 😉
    </li>
    <li>
      You can configure analogue contacts as an alarm. This can be bound to a door switch, or even temperature and water level monitors in a remote data center. This one will be very handy.
    </li>
  </ul>
  
  <p>
    <a class="thickbox" href="http://www.colinmcnamara.com/wp-content/gallery/cisco-surveillance/cisco-video-surveillance-manager.jpg"><img class="ngg-singlepic ngg-none" src="http://www.colinmcnamara.com/wp-content/gallery/cisco-surveillance/thumbs/thumbs_cisco-video-surveillance-manager.jpg" alt="cisco-video-surveillance-manager.jpg" /></a>
  </p>
  
  <p>
    The third part of this solution is Cisco&#8217;s Video Surveillance Operations Manager. It manages, archives, displays and distributes the content that was created and collected on the two previous modules. You would use this if you had many branches to aggregate, or needed to staff a video wall (e.g. casino gaming commission operations). Now, you can run each of these components individually. Buy run together as a whole, Cisco has an enterprise class security solution.
  </p>
  
  <p>
    <strong>Want to learn more ?</strong>
  </p>
  
  <p>
    Branch office security page on cisco.com <a href="http://www.cisco.com/en/US/products/ps9671/prod_module_series_home.html" target="_blank">http://www.cisco.com/en/US/products/ps9671/prod_module_series_home.html</a>
  </p>
  
  <p>
    Cisco&#8217;s product page for the Video Managment Module &#8211; <a href="http://www.cisco.com/en/US/prod/collateral/modules/ps9671/data_sheet_c78_462225.html" target="_blank">http://www.cisco.com/en/US/prod/collateral/modules/ps9671/data_sheet_c78_462225.html</a>
  </p>

 [1]: http://www.colinmcnamara.com/wp-content/gallery/cisco-surveillance/cisco-vmss-network-module-internal-view.jpg