---
id: 1217
title: 'Netflix Pinterest Instagram outage is not Amazon&#8217;s fault'
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/?p=1217
permalink: /netflix-pinterest-instagram-outage-is-not-amazons-fault/
categories:
  - cloud computing
tags:
  - availability
  - cloud computing
  - DESIGN
  - Provider
---
Amazon had an extended outage last night in their Virginia data center. This outage was a resulted of power interruptions due to storms in the mid Atlantic area.

<center>
  <a href="http://photo.blogpressapp.com/show_photo.php?p=12/06/30/1741.jpg"><img style="margin: 5px;" src="http://photo.blogpressapp.com/photos/12/06/30/s_1741.jpg" alt="" width="281" height="170" border="0" /></a>
</center>

  
This outage created some very visible impact on public applications such as Netflix, Pinterest and Instagram. The first reaction by many on the Internet of course is to point out the flaws in a cloud computing model, specifically relying on Amazon EC2 and S3.

The funny thing is that these applications would have gone down whether they were hosted with Amazon, or delivered from a private infrastructure. The reason they went down is because key infrastructure needed to deliver these apps was all running in one place. Amazon would call this place an &#8220;availability zone&#8221;, in a private cloud you would call this a data center.

The key flaw here is not that these companies are utilizing a cloud provider. It is that where and how these applications are delivered is abstracted from development teams. In a private cloud offering, operations teams and sysadmins normally take into account segmentation of fault domains and do their best to ensure that a single outage will not take down a business critical application.

Now days, more and more application teams are requesting resources through an API. The same checks and balances that existed in the past, where a third party thought about how the system survives in an outage do not always exist. The result of this is systems that can easily scale programmatically to millions of uses in minutes, but cannot survive a simple power outage in one of many data centers in which the applications reside.

What is the lesson here? The lesson is not to avoid deploying apps in public clouds. The lesson is that the same application architecture flaws that caused Netflix, Pinterest and Instagram to go down are becoming prevalent in privately managed infrastructure (private clouds) also.

It is very easy to allow your development teams interaction with the IT infrastructure provider to completely devolve to interaction with an API as instances are created. What is needed is to training and education of development teams on aspects of high availability application design and/or integration of systems architects into these teams to ensure the applications will survive simple infrastructure outages like the ones that hit Amazon yesterday.