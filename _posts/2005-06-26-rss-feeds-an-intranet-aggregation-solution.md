---
id: 5
title: 'RSS feeds &#8211; an intranet aggregation solution?'
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/2005/06/26/rss-feeds-an-intranet-aggregation-solution/
permalink: /rss-feeds-an-intranet-aggregation-solution/
blogger_blog:
  - colinmcnamara.blogspot.com
blogger_author:
  - Colin McNamara
blogger_permalink:
  - /2005/06/rss-feeds-intranet-aggregation.html
categories:
  - Technology
tags:
  - blog
  - C
  - CCIE
  - Colin
  - communication
  - NDA
  - Provider
---
So I am sitting at work last week, and the boss suggests that everyone on my team starts a blog. He has valid reasons &#8211; Communication of random ideas, encouraging collaboration, etc etc. So this gets me thinking of challenges that are faced aggregating information within corporate intranets, file stores, and databases. One of the large challenges I face day in day out is &#8220;where is that file on X&#8221;. Most of the time, I really have no clue. I may hit up our legacy intranet search app. Or maybe search a share point index, assuming that the users actually published the information. Maybe next hit up Docman. This continues on and on, until I finally give up and start asking around.

This highlights a pretty fundamental trend. Vendors imbed search functionality inside their own apps, or at least they attempt to. But god forbid you want to search across multiple applications or repositories.

In the past the solution was to expose a http interface into your repository, then use a spider to index said interface. This presents one problem &#8211; documents placed into repositories have horribly non-descriptive url&#8217;s. So as I am running my intranet search I hope and pray that someone put descriptive comments that are indexed by the spider. Sadly, I rarely have luck.

That highlights the second problem. Users are horrible about populating metadata within their documents. I am as guilty as anybody. I have been known to publish files with a less then descriptive name, and then leave my metadata blank. Recently however, I have improved my behavior. This behavior modification was brought on by using M$ SharePoint. Its basically a wiki front end to a SQL database, which is good and bad. What it does do good is encourage end users like me to utilize metadata for organizational structures instead of the classic folder method. It seems that as time goes on, metadata becomes more and more important in data classification. And it seems like both end users and large sites are catching on.

One thing I have noticed, is that pretty much every content provider is publishing their information via RSS feeds. It is about freaking time. Now end users just like me can have all their favorite information sources presented to them in one aggregated view.

This tactic is being used on the large user sites, because that is exactly what they want. If they make it easy for end users to get to content, they sell more product / show adds. This same tactic seems valid for corporate intranets. I can see an RSS feed of a project site you are working on, or coworkers site. Communicating status without adding to meeting burdens. Or to expand on that idea, RSS feeds doing keyword searches for patterns that you are interested in. I think there is true value is gathering information relevant to your job, without working to hard to do it.

This would be quite an accomplishment. Classically corporate apps seem to be architected to focus on capturing files and data. And on the flipside, they are pretty bad at expressing said information outside or themselves. You might call it a black hole of corporate data. So by combining RSS output of disparate corporate applications, with a RSS spider engine you should be able to get a nice summary pushed from disparate applications with links to extended metadata contained in these feeds. Maybe now I can find that file…

&#8211;Colin McNamara  
[Copyright ©2008 | Colin McNamara | CCIE 18233 | All Rights Reserved&#8221;][1]

<p class="blogger-post-footer">
  &nbsp;
</p>

<p class="blogger-post-footer">
  &nbsp;
</p>

 [1]: http://www.colinmcnamara.com "Copyright ©2008 | Colin McNamara | CCIE 18233 | All Rights Reserved"