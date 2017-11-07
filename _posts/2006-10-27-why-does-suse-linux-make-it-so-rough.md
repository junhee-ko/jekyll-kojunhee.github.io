---
id: 22
title: Why does SUSE linux make it so rough?
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/2006/10/27/why-does-suse-linux-make-it-so-rough/
permalink: /why-does-suse-linux-make-it-so-rough/
blogger_blog:
  - colinmcnamara.blogspot.com
blogger_author:
  - Colin McNamara
blogger_permalink:
  - /2006/10/why-does-suse-linux-make-it-so-rough.html
categories:
  - linux
  - Technology
  - Uncategorized
tags:
  - blog
  - C
  - CCIE
  - Colin
  - linux
---
#!/bin/sh  
\# Figure out kernel source version & you server location, echo string to install  
\# Written by Colin McNamara 10/27/2006  
\# http://www.2cups.com  
\# &#8220;The impossible we do difficult we do immidiatly, the impossible just takes a little longer.&#8221;  
KERNELVER=\`uname -r | sed &#8216;s/-smp//g; s/-bigsmp//g&#8217;\`  
PLATFORM=\`uname -i\`

YOUSERVER=\`cat /var/lib/YaST2/you/config | grep LastServer= | sed &#8216;s/LastServer=&#8221;//g; s/;;&#8221;//g&#8217;\`  
YOU64=$YOUSERVER/$PLATFORM/update/SUSE-CORE/9/rpm/x86_64  
YOU32=$YOUSERVER/$PLATFORM/update/SUSE-CORE/9/rpm/i586

if [[ \`uname -i\` = x86_64 ]]; then  
echo $YOU64/kernel-source-$KERNELVER.x86_64.rpm

else  
echo $YOU32/kernel-source-$KERNELVER.i586.rpm  
fi

[Copyright ©2008 | Colin McNamara | CCIE 18233 | All Rights Reserved&#8221;][1]

<p class="blogger-post-footer">
  Colin McNamara<br /> CCIE #18233<br /> http://www.2cups.com<br /> &#8220;The difficult we do immediately, the impossible just takes a little longer.&#8221;
</p>

 [1]: http://www.colinmcnamara.com "Copyright ©2008 | Colin McNamara | CCIE 18233 | All Rights Reserved"