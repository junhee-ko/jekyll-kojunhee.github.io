---
id: 10
title: Google Translate API and speech recognition
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/2005/07/07/google-translate-api-and-speech-recognition/
permalink: /google-translate-api-and-speech-recognition/
blogger_blog:
  - colinmcnamara.blogspot.com
blogger_author:
  - Colin McNamara
blogger_permalink:
  - /2005/07/google-translate-api-and-speech.html
categories:
  - google
  - Technology
tags:
  - blog
  - C
  - CCIE
  - Colin
---
Good morning,

It seems like the best idea&#8217;s always come in two places &#8211; The toilet and the shower. This morning I used both items, and had a pretty good idea bubble to the surface.

The idea, or should I say collection of ideas revolves around my inability to communicate in other languages. I try to work around this by using google translate, and texting back and forth. But even this fails in the event that I actually have to speek to someone. My only alternative then is to whip open my laptop, hop online, and type something out.

As I am writing this &#8230;. I just had a no crap eureka moment. My original direction and idea with this blog was to use speach recognition software to pipe text into a translation engine. This translated text would then be speach synthisysed back through your cell phone. This would be great, but I would think would have a long time to market.

So my no shit eureka moment &#8211; why not use SMS. The message is already in text format, limited to short sentances (reducing the likely hood of gross mistranslation). The idea being that whenever I need to speak spanish, it is generally short and to the point.

So the idea is to set up a sms server to collect sms messages. These messages would be piped into an API and sent off to google translate.  
The resulting text would then be sent back to the client handheld.

This text would then be sent back to the client, displayed on the handheld.  
The end user would read the response, alound. And hopefully communicate with the person.

This could build a working product user base, while a voice translation engine was being built from scratch.

Just my thoughts,  
&#8211;Colin  
[Copyright ©2008 | Colin McNamara | CCIE 18233 | All Rights Reserved&#8221;][1]

<p class="blogger-post-footer">
  Colin McNamara<br /> CCIE #18233<br /> http://www.2cups.com<br /> &#8220;The difficult we do immediately, the impossible just takes a little longer.&#8221;
</p>

 [1]: http://www.colinmcnamara.com "Copyright ©2008 | Colin McNamara | CCIE 18233 | All Rights Reserved"