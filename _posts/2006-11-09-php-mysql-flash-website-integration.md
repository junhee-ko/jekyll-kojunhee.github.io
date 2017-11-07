---
id: 23
title: PHP / MySQL / FLASH website integration
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/2006/11/09/php-mysql-flash-website-integration/
permalink: /php-mysql-flash-website-integration/
blogger_blog:
  - colinmcnamara.blogspot.com
blogger_author:
  - Colin McNamara
blogger_permalink:
  - /2006/11/php-mysql-flash-website-integration.html
categories:
  - photographer
  - photography
  - san diego
  - Technology
  - Uncategorized
tags:
  - blog
  - C
  - CCIE
  - Colin
  - DESIGN
  - HP
  - photography
  - Pic
---
First I have to say, check out the new Ashley McNamara Photography website at http://www.ashleymcnamara.com/

We had it designed by Bludomain.com. At first I was a little reticent about using them, but now I am very happy about the move. The interface for maintaining gallery&#8217;s is superior to how I was doing them before. In the past Ashley would bug me to update her pictures, and I would bug her to provide them in for proper format. Now she just logs onto a web interface and uploads her pictures, updates her content, and whaam.. the site is updated. All this happens without one honey do this. I say that is worth its price in gold

Once I saw this &#8220;seamless&#8221; interface I had to figure out how they are doing it. After a little pocking around their source code I found out that they were using PHP to pull information out of a MySQL database, and use that for dynamic content insertion into a flash template. From what I can tell, the first thing that happens is the base flash template loads. Each button shape is hard coded in flash, and an actionscript is bound to each button.  
This actionscript runs a PHP web application that logs into a local MySQL database, selects from a table, creates an array, then runs a for loop to populate each submenu for items in each drop down.

The net net of this is that you can have a few default templates, and just populate unique configuration options a MySQL db. This simplifies the whole content management issue while still providing the Content Protection that flash gives you.

&#8211;Colin McNamara  
[Copyright ©2008 | Colin McNamara | CCIE 18233 | All Rights Reserved&#8221;][1]

<p class="blogger-post-footer">
  Colin McNamara<br /> CCIE #18233<br /> http://www.2cups.com<br /> &#8220;The difficult we do immediately, the impossible just takes a little longer.&#8221;
</p>

 [1]: http://www.colinmcnamara.com "Copyright ©2008 | Colin McNamara | CCIE 18233 | All Rights Reserved"