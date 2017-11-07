---
id: 9
title: 'User experience testing &#8211; enhanced'
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/2005/06/28/user-experience-testing-enhanced/
permalink: /user-experience-testing-enhanced/
blogger_blog:
  - colinmcnamara.blogspot.com
blogger_author:
  - Colin McNamara
blogger_permalink:
  - /2005/06/user-experience-testing-enhanced.html
categories:
  - Technology
tags:
  - blog
  - C
  - CCIE
  - Colin
  - error
  - HP
  - linux
  - NDA
  - Network
  - passed
  - Router
---
Good afternoon,  
Everyone who knows me, knows that I have special spot in my heart for user experience testing. My personal favorite platform is Nagios, formerly Netsaint. It&#8217;s a linux based monitoring system located at <http://www.nagios.com> . I have set it up at pretty much everywhere I have worked. Like many monitoring systems, Nagios uses a plugin based architecture for its service checks. These plugins classically either connect to the TCP port that a service runs on, or does basic protocol validation.. e.g. issue a http get, and pattern match the response string.

This is great information to have, however when you have a multi tiered application it becomes harder to get a true status of your application stack. Luckily most new applications nowadays incorporate a HTTP interfaces.  
However, this interface responding to a http get request generally does not indicate full application functionality. To get that level of information out you usually need to present some authentication to the web app, execute a click through, etc.

Now this has always presented a problem for me. I can check the availability of each level of the application stack. What I can&#8217;t do is verify that the application is truly working properly. This puts a major blind spot in my monitoring strategies. Luckily I just came across a very cool application. This sweet application is webinject &#8211; <http://www.webinject.org/>  
It can be configured to graph application performance to mrtg, or output to nagios network monitor. Below is some information about this project.

What is WebInject?  
WebInject is a free tool for automated testing of web applications and services. It can be used to test individual system components that have HTTP interfaces (JSP, ASP, CGI, PHP, Servlets, HTML Forms, etc), and can be used as a test harness to create a suite of [HTTP level] automated functional, acceptance, and regression tests. A test harness, also referred to as a test driver or a test framework, allows you to run many test cases and collect/report your results. WebInject offers real-time results display and may also be used for monitoring system response times.  
WebInject can be used as a complete test framework that is controlled by the WebInject User Interface (GUI). Optionally, it can be used as a standalone test runner (text/console application) which can be integrated and called from other test frameworks or applications.

Programming Language and Platforms  
WebInject uses an XML API (interface) for defining and loading test cases. You can use WebInject without ever seeing it&#8217;s internal implementation (no scripting or programming necessary to use it).  
WebInject is written in Perl and can run on any platform that a Perl interpreter can be installed on (MS Windows, GNU/Linux, BSD, Solaris, MAC OS, and many more). Currently, binary executables of WebInject are only available for MS Windows. If you would like to run on other platforms, you must have a Perl interpreter and run it from the Perl source code.

Test Cases  
Test cases are written in XML files, using XML elements and attributes, and passed to the WebInject engine for execution against the application/service under test. This abstracts the internals of WebInject&#8217;s implementation away from the non-technical tester, while using an open architecture [written in Perl] for those that require more customization or modifications.

Results/Reporting  
Result reports are generated in HTML (for viewing) and XML (for tranformation by external programs). These detailed results include pass/fail status, errors, response times, etc. Results are also displayed in a window on the User Interface if you are running the WebInject GUI, and are sent to the STDOUT channel if you are running the WebInject Engine as a standalone (console) application.

Service-Level Monitoring  
HTTP response times can be collected and monitored in real-time during test execution. Timer statistics are calculated and displayed in a monitor window during runtime. When used along with gnuplot (a plotting utility), a response time graph is generated and updated in real-time as the test runs. This is used to verify responses from the web application or web service under test are within an acceptable range (to meet your SLA or quality of service criteria). This also enables WebInject to be run as a performance probe for application/service monitoring.  
WebInject can also be integrated as a plugin for external monitoring systems. In this case, it is used in console mode as an intelligent test agent that returns status and response times to your external program.  
For real-time monitoring of your web applications or web services, WebInject is able to run in a mode that makes it compatible with Nagios. Nagios is an open source host, service, and network monitoring program.  
For graphical trending of web service-levels over a long period of time, WebInject is able to run in a mode that makes it compatible with MRTG. MRTG (Multi Router Traffic Grapher) is an open source tool for collecting, storing, and graphing time-series data.

&#8211;Colin  
[Copyright ©2008 | Colin McNamara | CCIE 18233 | All Rights Reserved&#8221;][1]

<p class="blogger-post-footer">
  Colin McNamara<br /> CCIE #18233<br /> http://www.2cups.com<br /> &#8220;The difficult we do immediately, the impossible just takes a little longer.&#8221;
</p>

 [1]: http://www.colinmcnamara.com "Copyright ©2008 | Colin McNamara | CCIE 18233 | All Rights Reserved"