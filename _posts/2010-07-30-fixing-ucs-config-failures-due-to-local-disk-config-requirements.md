---
id: 841
title: Fixing UCS Config Failures due to local disk config requirements
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/?p=841
permalink: /fixing-ucs-config-failures-due-to-local-disk-config-requirements/
categories:
  - CISCO
  - Cisco UCS
  - Cisco Unified Computing System
  - ESXi
  - vmware
tags:
  - application cycle
  - boring title
  - disk configuration
  - error message
  - firmware
  - little bug
  - physical server
  - profile section
  - pxe boot
  - service profile
  - UCS
  - ucsm
---
Boring title huh? Well, this isn&#8217;t what I wanted to be dealing with on a Friday afternoon either. My plan was to set up a PXE boot environment to create scripted installations of ESXi 4.1 on UCS. However when I shelled into the UCS lab at work, I was made aware of a little bug.

**The Problem**

Apparently when the UCS pod&#8217;s firmware was updated to 1.3(1c) an interesting bug was encountered. What happens is when you associate your service profile to a server which has had another service profile associated with it previously you a config failure error stating that the local disk config you are applying is destructive to the physical server and violates a requirement.

[singlepic id=140 w=420 h=340 float=]

I headed over to the local disk policies section of UCSM to see what was going on. Once I got there I noticed a new check box labeled &#8220;Protect Configuration&#8221;.

[singlepic id=157 w=420 h=340 float=]

It&#8217;s a lab, which means that change controls should be followed but rarely are. Following that mantra and went ahead and unchecked the &#8220;Protect Configuration&#8221; box on one of the commonly used local disk policies and saved my changed. A little background on HOW I am shelled into this lab. I am shelled in via a VMware View server that has component installed on blades 1 and 2 of this chassis. And, yes the local disk configuration that I made a change to was used by these profiles.

A little while later, after all the servers went through a reboot and settings application cycle and a coworker kicked a View server in the butt I was back in. The first thing I did was try to apply my service profile. I got the same error message.

I went back to the local disk config profile section to see if maybe the change hadn&#8217;t applied. But, when I edited the profile, it showed that the local disk config should not be in a protected configuration.

[singlepic id=137 w=420 h=340 float=]

However when I went into a service profile to change the same local disk policy, you will notice that this same local disk config was still showing up as a protected configuration.

[singlepic id=138 w=420 h=340 float=]

**The Solution**

When you encounter a bug, the first thing you do if the obvious isn&#8217;t working is check the release notes. This bug did show up int he 1.3 release notes, with a tag of &#8220;no workaround&#8221;. I don&#8217;t believe in not having workarounds so proceeded to bang my head up against a wall trying time consuming things like rediscovering servers, recovering bios&#8217;s, creating custom firmware packs and more.

After all that failed, I tried the simple things (you like the reverse order?). My excuse was that I assumed that TAC who had created the bug had already tried this. I guess I should assume less often&#8230;

The simple thing, that I should have done from the start was create a brand new local disk profile. I named this profile FIX-PERSIST-ANY, choosing to use any local disk config and expressly making it non-persistent. I then applied the same local disk policy that was on previously to my service profile, and then once applied changed it to FIX-PERSIST-ANY.

[singlepic id=139 w=420 h=340 float=]

At that point I whatever flag that had gotten stuck in the UCSM database got unstuck and I was able to get my service profile applied.

[singlepic id=142 w=420 h=340 float=]

**Moral of the story**

Just because a bug shows no workaround, it doesn&#8217;t mean you can&#8217;t fix it. It just means that the engineer who submitted the bug wasn&#8217;t able to.

Now I can finally get around to what I was originally trying to do today, getting scripted PXE installs of ESXi 4.1 working.