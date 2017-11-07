---
id: 51
title: Routers can email you when they go down
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/2007/10/28/routers-can-email-you-when-they-go-down/
permalink: /routers-can-email-you-when-they-go-down/
blogger_blog:
  - colinmcnamara.blogspot.com
blogger_author:
  - Colin McNamara
blogger_permalink:
  - /2007/10/routers-can-email-you-when-they-go-down.html
categories:
  - cisco router eem email scripting ccie
tags:
  - blog
  - C
  - CCIE
  - CISCO
  - Colin
  - john
  - Network
  - Router
---
[Cisco IOS tips and tricks][1] had a great post on how to use EEM to send emails when interfaces go down.

&#8221;

<p class="author">
  By Ivan Pepelnjak
</p>

John S. Pumphrey recently asked an interesting question: “Can the router send an e-mail when an interface goes down?” The <a href="http://en.wikipedia.org/wiki/Enterprise_software#Criticisms" target="_blank">enterprisey</a> solution is obvious: deploy a high-end <acronym title="Element Management System">EMS</acronym> to collect <acronym title="Simple Network Management Protocol">SNMP</acronym> traps and use its <acronym title="Application Program Interface">API</acronym> to write a custom module that would use a <acronym title="Message Queue">MQ</acronym> interface to alert the operator. Fortunately, Event Manager applets in Cisco IOS provide <a href="http://www.cisco.com/univercd/cc/td/doc/product/software/ios124/124tcr/tnm_r/nmg_01ht.htm#wp1253694" target="_blank">action mail</a> command (available in 12.3(14)T and 12.4) that can send an e-mail to a <acronym title="Simple Mail Transfer Protocol">SMTP</acronym> server straight from the router.

There are two ways you can detect that an interface went down with EEM: either you track the interface status with a **track** object and start an EEM applet when the track object changes state or you catch the *syslog* messages reporting that the interface line protocol changed state to down. The second approach is obviously more generic, as a single applet can act on multiple interfaces.

<pre class="code">event manager applet MailOnIfDown event syslog occurs 1 →    pattern "LINEPROTO-5-UPDOWN.*to down" →    period 1</pre>

<p class="note">
  <span>Notes:</span>
</p>

  * If you want to limit the applet to serial interfaces only, you could change the pattern to **LINEPROTO-5-UPDOWN.\*Serial.\*to down**.
  * The → continuation character is used to indicate that a single configuration line has been split to increase readability.

The **action mail** command specifies the mail **server**&#8216;s address (use a hostname and DNS lookup or **ip host** configuration command to make the EEM applet more generic), **from** and **to** address, message **subject** and **body**. In each of these fields, you can use EEM environment variables that you can define with the **event manager environment** configuration command. Each EEM event also defines a few environment variables that you can use (see the <a href="http://www.cisco.com/univercd/cc/td/doc/product/software/ios124/124cg/hnm_c/ch05/heem21.htm#wp1047028" target="_blank">table of EEM system-defined variables on CCO</a>). For example, you can define the e-mail recipient in the router&#8217;s configuration and use the **\_syslog\_msg** variable to include the *syslog* message in the e-mail body:

<pre class="code">event manager environment _ifDown_rcpt admin@lab.com!event manager applet MailOnIfDown event syslog occurs 1 →    pattern "LINEPROTO-5-UPDOWN.*to down" →    period 1 action 1.0 mail server "mail-gw" →    to "<span class="high">$_ifDown_rcpt</span>" from "R1@lab.com" →    subject "Interface down on R1" →    body "$_syslog_msg"</pre>

You can make the applet even more generic with the help of **action info type routername** command, which stores the current router&#8217;s name into the $\_info\_routername environment variable:

<pre class="code">event manager environment _ifDown_rcpt admin@lab.com!event manager applet MailOnIfDown event syslog occurs 1 →    pattern "LINEPROTO-5-UPDOWN.*to down" →    period 1 action 1.0 info type routername action 2.0 mail server "mail-gw" →    to "$_ifDown_rcpt" from "<span class="high">$_info_routername</span>@lab.com" →    subject "Interface down on $_info_routername" →    body "$_syslog_msg"

"</pre>

<p class="blogger-post-footer">
  Colin McNamara<br /> CCIE #18233<br /> http://www.2cups.com<br /> &#8220;The difficult we do immediately, the impossible just takes a little longer.&#8221;
</p>

 [1]: http://ioshints.blogspot.com/