---
id: 1803
title: Open letter to Cisco about DevNet
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/?p=1803
permalink: /open-letter-to-cisco-about-devnet/
categories:
  - CISCO
tags:
  - api
  - CISCO
  - devnet
  - nexus 9000
  - python
  - ucsm
---
What I wanted to do today is, show you some of the challenges, My teams and I are having interacting with DevNet.

This is the developer portal, that you guys put up. To help ease teams like mine and find access to API documentation, software development tool kits, and both closed and open source code.

### My perspective

I&#8217;m a CCIE. I have automated and some large data centers using a wide range of API&#8217;s. I&#8217;m not a great programmer, luckily I hire people who are. My software development teams and I are building our own application stacks.

They run and put on Amazon right now. Our goal is to make sure that they easily and automatically deploy onto UCS platforms. And Nexus 9000&#8217;s, 5000&#8217;s, 7000&#8217;s with cool open source projects like OpenStack and OpenDaylight get integrated with them.

### Feedback &#8211; DevNet is impossible to use

<img style="display: block; margin-left: auto; margin-right: auto;" title="CiscoDevnet.png" alt="Cisco Devnet" src="http://www.colinmcnamara.com/wp-content/uploads/2014/02/CiscoDevnet.png" width="500" height="250" border="0" />

I&#8217;m going to tell you something, that&#8217;s probably really hard to hear. It is near impossible, to use DevNet to find information that we need to be able to achieve our goal. I think that&#8217;s your goal, helping guys like us integrate our software with gear like yours.

### Example &#8211; Finding SDK&#8217;s and API Docs

The first thing, a really easy example, a basic thing that you&#8217;d want to do or that you&#8217;d want a developer to help a team be able to accomplish, is find SDK, find API documentation, and find software development tool kit. To allow us to hook into your gear.

However when me or anyone from my teams attempt to navigate to through devnet to find API / SDK&#8217;s the default is to pop us to a product page that has nothing to do with software development.

Instead of having my first and easiest navigation option go to the software that I&#8217;ve already made the decision to go ahead and integrate, I get sent to a product page that is trying to influence me to buy a server.

I&#8217;m looking for the information of, how I can integrate it. Why another product pitch? It makes no sense, absolutely no sense.

### The hardware is not important, the API and SDK&#8217;s are

<img style="display: block; margin-left: auto; margin-right: auto;" title="insieme-ifc-code.png" alt="insieme ifc code " src="http://www.colinmcnamara.com/wp-content/uploads/2014/02/insieme-ifc-code.png" width="500" height="230" border="0" />

I don&#8217;t care what hardware data sheets there are. It&#8217;s not important. I&#8217;m looking at programmatically integrated to my system.

Sorry if that&#8217;s very aggressive, but this is really, really frustrating. This feedback as I bring new developers into my team, they get me too. &#8220;You told me to integrate this stuff, but where is this stuff?&#8221; First question, where&#8217;s my SDK?

Normally what would happen, is I would go open up my local git clone and do a get/pull (this is a linked clone of a source code repository owned / hosted somwhere else). If found the SDK before, I normally wouldn&#8217;t navigate to a site to see an update. I would have that repo integrated not only with my my local dev setup, but it would also be integrated into any tooling that I have. (Listed as a dependency, and auto built by Jenkins)

### An example of what to do &#8211; Insieme and Webex on Github

One place that I love to go is http://www.github.com/CiscoSystem. This place is where the the WebEx team and some of the guys from, NOSTG push a lot of information. Kyle and Mark put a lot of stuff here too on GitHub. This is a place where developers collaborate.

This allows me, as someone who is integrating applications on their stuff to go ahead and, not only through a web page, go ahead and see some interesting stuff.

Very specifically, a great example, the Insieme team. Mike, an awesome guy on that team, has posted some interesting SDK&#8217;s information for the Nexus 5000.

It&#8217;s easy for me to find. I could Google it. I could search for it on GitHub. I can do a lot of cool things, things that are important to me, in my software development work flow.

### Nexus 9k API docs on Github

In this example I talk about Mike Cohen&#8217;s code for Nexus 9K. This is how it should be done. Example &#8211;

Over the years I&#8217;ve had to hack these stupid expect scripts and interactions with NetConf to do shut/no shuts and do network testing. You get 1,000, 2,000 nodes, and with four links each you&#8217;re going to have transceiver failure and cable failures all over the place.

You end up writing these scripts, to go ahead and exercise the network and start tests on either end. One, it takes forever. Two, it&#8217;s a giant pain in the rear, especially when you have to diverse platforms.

I was poking around, and I see, &#8220;Oh, wow, someone wrote some interesting code, which, if you look at it, goes in and provides a link test.&#8221; This is really, really cool. This is code that I can use. I can integrate it into my own stuff, my own operational procedures. Not so bad.

### Use of Developer Toolchains for collaboration

As a developer, Git provides a set of the tools that are used to track, communicate and collaborate. We use this to answer questions like &#8211; &#8220;who the heck wrote this?&#8221; The first thing we would do was go ahead and check the log.

  * Who wrote this stuff? OK, I see Mike Cohen. I&#8217;ve got his email address.
  * I can even go so far as to see when he did it. OK, that was at the end of December, December 19th.
  * I can see exactly what was added each day. Now there&#8217;s a log for the entire repository, Mike from Nexus repository.
  * I can see that there&#8217;s another developer who was contributing early on to the repository.
  * I can see that if I need to get clarity or have a question about utilization of this code, I can ping Mike Cohen.

### Collaborating on code via Pull Requests

Say I improve the code. I find something unique and novel that I can use in my own networks, but I&#8217;m not in the business of maintaining a small patch to this.

I can go ahead and make my patch. Then I can submit a pull request back to Mike. Mike just gets an email that says, &#8220;Hey, please merge this. I found this useful. Inspect the code, test it, validate it. If it&#8217;s good, merge it.&#8221;

That makes it something that all the community can use. I&#8217;m not in the business of maintaining these minor patches. They distract from the effectiveness of me and my team. I want to be able to submit that.

### My experience trying to do this with the UCS SDK on Communities

I downloaded it from some community&#8217;s page. I don&#8217;t know who wrote it. I don&#8217;t know who to contact. I can extend it. I can keep that private. It&#8217;s a top down community. It doesn&#8217;t support the community development, that&#8217;s been really key to the growth of open source.

### Collaboration between Manufacturer, Integrator and Customer in OpenSource

We saw a move of Open Source projects from SourceForge to GitHub. It&#8217;s been real. GitHub has allowed this interaction between us that&#8217;s key to our development collaboration on OpenStack and OpenDaylight, SDN controller.

My team is one use case. Our company is not huge, but not small. We do about a half billion in revenues, but we&#8217;re big enough that we&#8217;ve been contributing for OpenStack for two years now and OpenDaylight since mid 2013.

We can push code back. We can contribute into the community. Where we find things that support an unfair advantage market, a new secret sauce, things that support it, we can share the burden, we can be good stewards.

We collaborate with Cisco, with Red Hat, with IBM, with HP in the open domain. What I&#8217;m pointing out here is there is no method enabled within DevNet to support that collaboration.

### Cisco DevNet needs to support that collaboration

There&#8217;s a huge opportunity to do that. I&#8217;m hoping you take that chance. It&#8217;s not about tools. It&#8217;s about the back-end. It&#8217;s about the collaboration in the community.

### My Recommendations

#### Don&#8217;t point me to product.

If I&#8217;m already looking for software integration information, I have made my purchasing decision. Shoving product in my face just gets in the way of my job.

If I&#8217;m so frustrated where I can&#8217;t find the API documentation and, very specifically, SDK&#8217;s, as a developer. I&#8217;m going to go to the competition and try to find theirs. It&#8217;s all about the software integration, not the tin can that we wrap a CPU in. We call that a server, right?

#### Please, please consolidate information onto GitHub

In the open source domain right now it&#8217;s not only where we collaborate, but it&#8217;s a tool chain that allows us to collaborate. It is the standard for open source communication and collaboration.

Linus Torvald invented it for a reason. The guys at GitHub have been really doing a great job in enabling this innovative community. That breaks down the barriers between manufacturer, integrator, and customer.

#### Set up a IRC channel in this community

Every day OpenStack, OpenDaylight, my own internal development teams&#8217; use IRC channel&#8217;s to collaborate. You can see all my teams up on the public open source channels. Get Cisco channel up there. Make it so it&#8217;s integrated with DevNet. It&#8217;s not that technically challenge. That&#8217;s a huge opportunity.

### What you should take away from this

Fundamentally you need to communicate and collaborate. DevNet should not only be we can be pointed to the software but a tool to encourage that collaboration.

Make sure that we know very clearly who is maintaining that repo, that there&#8217;s someone dedicated to evaluating emerging pull requests. Use us as a tool.

There are a lot of people that use Cisco gear out there, Cisco routers, phones, servers. There&#8217;s a small number of people there that, for many, many years, have been writing code that configures it.

If you can enable DevNet to be what it can truly become, which is a collaboration point, integrated with the common open source collaboration tools and platforms, GitHub&#8230;Maybe I&#8217;m dreaming of this day ,when I don&#8217;t have to re-factor my code every three years.

You can really start to create that community. Frankly there are a lot of us that are just waiting for it to happen. I&#8217;m looking forward to you creating a conversation and seeing this become what it could be.

### Resources

<http://developer.cisco.com> &#8211; Cisco DevNet  
<http://www.github.com/CiscoSystems> &#8211; Cisco Webex and NOSTG dumping ground for code  
<http://www.github.com/DATACENTER> &#8211; Nexus 9k / ACI org on GitHub

<http://pcottle.github.io/learnGitBranching/> &#8211; Learn about GIT

&nbsp;