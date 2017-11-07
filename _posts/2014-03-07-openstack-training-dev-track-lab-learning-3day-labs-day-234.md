---
id: 1844
title: 'OpenStack Training &#8211; Dev Track &#8211; Lab Learning &#8211; 3day Labs (day 2,3,4)'
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/?p=1844
permalink: /openstack-training-dev-track-lab-learning-3day-labs-day-234/
categories:
  - OpenStack
tags:
  - openstack
  - OpenStack Training
---
### <span style="background-color: transparent; font-family: Arial; font-size: 15px; white-space: pre-wrap; line-height: 1.15;">Overview &#8211; Developer Training for OpenStack</span>

<span style="background-color: transparent; font-family: Arial; font-size: 15px; white-space: pre-wrap; line-height: 1.15;">All us bearded (and virtually bearded) OpenStack hippies are at it again, trying to change the world through training and enablement, and a little bit of code. In this current experiment we are biting of a big chunk and creating something very similar to the Amazon Architect Course. </span>

<span style="font-family: Arial;"><span style="font-size: 15px; line-height: 17px; white-space: pre-wrap;">The goal for this course (Building on the work done in OpenStack Training for the Associate and Operators Course &#8211; </span></span><a style="font-family: Arial; font-size: 15px; line-height: 17px; white-space: pre-wrap;" href="http://docs.openstack.org/training-guides/content/">http://docs.openstack.org/training-guides/content/</a><span style="font-family: Arial;"><span style="font-size: 15px; line-height: 17px; white-space: pre-wrap;"> ) is to have a developer armed with understanding and experience building applications on the core components of OpenStack.</span></span>

<p dir="ltr" style="line-height: 1.15; margin-top: 0pt; margin-bottom: 0pt;">
  <p dir="ltr" style="line-height: 1.15; margin-top: 0pt; margin-bottom: 0pt;">
    <span style="font-size: 15px; font-family: Arial; background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"><strong>User Archetype</strong> &#8211; Web Application Developer, current or future developer of Apps to be run on Amazon Web Services (AWS).</span>
  </p>
  
  <p dir="ltr" style="line-height: 1.15; margin-top: 0pt; margin-bottom: 0pt;">
    <span style="font-size: 15px; font-family: Arial; background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"><strong>Method</strong> &#8211; Step by step lab learning taking student developer through structured app dev example</span>
  </p>
  
  <h3>
    <span style="background-color: transparent; font-family: Arial; font-size: 15px; white-space: pre-wrap; line-height: 1.15;">Goal &#8211; Developer will be able to build applications that interact with key services</span>
  </h3>
  
  <ul style="margin-top: 0pt; margin-bottom: 0pt;">
    <li dir="ltr" style="list-style-type: disc; font-size: 15px; font-family: Arial; background-color: transparent; vertical-align: baseline;">
      <p dir="ltr" style="line-height: 1.15; margin-top: 0pt; margin-bottom: 0pt;">
        <span style="background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Git, Gerrit, Jenkins, Config Mgmt &#8211; Puppet  (pre-canned within Glance Image)</span>
      </p>
    </li>
    
    <li dir="ltr" style="list-style-type: disc; font-size: 15px; font-family: Arial; background-color: transparent; vertical-align: baseline;">
      <p dir="ltr" style="line-height: 1.15; margin-top: 0pt; margin-bottom: 0pt;">
        <span style="background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Glance (Deploy instance image from &#8211; Puppet )</span>
      </p>
    </li>
    
    <li dir="ltr" style="list-style-type: disc; font-size: 15px; font-family: Arial; background-color: transparent; vertical-align: baseline;">
      <p dir="ltr" style="line-height: 1.15; margin-top: 0pt; margin-bottom: 0pt;">
        <span style="background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Nova (instance  deployed too)</span>
      </p>
    </li>
    
    <li dir="ltr" style="list-style-type: disc; font-size: 15px; font-family: Arial; background-color: transparent; vertical-align: baseline;">
      <p dir="ltr" style="line-height: 1.15; margin-top: 0pt; margin-bottom: 0pt;">
        <span style="background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Swift (Display Image in web app from, set meta-information about)</span>
      </p>
    </li>
    
    <li dir="ltr" style="list-style-type: disc; font-size: 15px; font-family: Arial; background-color: transparent; vertical-align: baseline;">
      <p dir="ltr" style="line-height: 1.15; margin-top: 0pt; margin-bottom: 0pt;">
        <span style="background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Keystone &#8211; User with authenticate into web app into Keystone API</span>
      </p>
    </li>
  </ul>
  
  <h3>
    <span style="background-color: transparent; font-family: Arial; font-size: 15px; white-space: pre-wrap; line-height: 1.15;">Future Goal &#8211;  Advanced Topics for super star dev &#8211; Thoughts Captured Here, </span>
  </h3>
  
  <ul style="margin-top: 0pt; margin-bottom: 0pt;">
    <li dir="ltr" style="list-style-type: disc; font-size: 15px; font-family: Arial; background-color: transparent; vertical-align: baseline;">
      <p dir="ltr" style="line-height: 1.15; margin-top: 0pt; margin-bottom: 0pt;">
        <span style="background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Telemetry &#8211; Pull performance information and display it in webapp</span>
      </p>
    </li>
    
    <li dir="ltr" style="list-style-type: disc; font-size: 15px; font-family: Arial; background-color: transparent; vertical-align: baseline;">
      <p dir="ltr" style="line-height: 1.15; margin-top: 0pt; margin-bottom: 0pt;">
        <span style="background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Heat &#8211; Create set of templates for supporting services</span>
      </p>
      
      <ul style="margin-top: 0pt; margin-bottom: 0pt;">
        <li dir="ltr" style="list-style-type: circle; font-size: 15px; font-family: Arial; background-color: transparent; vertical-align: baseline;">
          <p dir="ltr" style="line-height: 1.15; margin-top: 0pt; margin-bottom: 0pt;">
            <span style="background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Create orchestration template for DBaaS (Trove)</span>
          </p>
        </li>
        
        <li dir="ltr" style="list-style-type: circle; font-size: 15px; font-family: Arial; background-color: transparent; vertical-align: baseline;">
          <p dir="ltr" style="line-height: 1.15; margin-top: 0pt; margin-bottom: 0pt;">
            <span style="background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Trigger creation of extra services using Heat Template</span>
          </p>
        </li>
      </ul>
    </li>
    
    <li dir="ltr" style="list-style-type: disc; font-size: 15px; font-family: Arial; background-color: transparent; vertical-align: baseline;">
      <p dir="ltr" style="line-height: 1.15; margin-top: 0pt; margin-bottom: 0pt;">
        <span style="background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Trove &#8211; Pull content from DBaaS, Need to push content in</span>
      </p>
    </li>
    
    <li dir="ltr" style="list-style-type: disc; font-size: 15px; font-family: Arial; background-color: transparent; vertical-align: baseline;">
      <p dir="ltr" style="line-height: 1.15; margin-top: 0pt; margin-bottom: 0pt;">
        <span style="background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Networking &#8211; </span>
      </p>
      
      <ul style="margin-top: 0pt; margin-bottom: 0pt;">
        <li dir="ltr" style="list-style-type: circle; font-size: 15px; font-family: Arial; background-color: transparent; vertical-align: baseline;">
          <p dir="ltr" style="line-height: 1.15; margin-top: 0pt; margin-bottom: 0pt;">
            <span style="background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Neutron &#8211; Create security group between web app nodes and trove instances</span>
          </p>
        </li>
        
        <li dir="ltr" style="list-style-type: circle; font-size: 15px; font-family: Arial; background-color: transparent; vertical-align: baseline;">
          <p dir="ltr" style="line-height: 1.15; margin-top: 0pt; margin-bottom: 0pt;">
            <span style="background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Neutron + ODL &#8211; Create App Policy Contract (super duper bonus points)</span>
          </p>
        </li>
      </ul>
    </li>
    
    <li dir="ltr" style="list-style-type: disc; font-size: 15px; font-family: Arial; background-color: transparent; vertical-align: baseline;">
      <p dir="ltr" style="line-height: 1.15; margin-top: 0pt; margin-bottom: 0pt;">
        <span style="background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Marconi (queueing) &#8211; Pass information between app instances using marconi message bus</span>
      </p>
      
      <ul style="margin-top: 0pt; margin-bottom: 0pt;">
        <li dir="ltr" style="list-style-type: circle; font-size: 15px; font-family: Arial; background-color: transparent; vertical-align: baseline;">
          <p dir="ltr" style="line-height: 1.15; margin-top: 0pt; margin-bottom: 0pt;">
            <span style="background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Pass user input to be displayed on all pages through form input to display on local instance, as well as secondary instance</span>
          </p>
        </li>
      </ul>
    </li>
    
    <li dir="ltr" style="list-style-type: disc; font-size: 15px; font-family: Arial; background-color: transparent; vertical-align: baseline;">
      <p dir="ltr" style="line-height: 1.15; margin-top: 0pt; margin-bottom: 0pt;">
        <span style="background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Savanna</span>
      </p>
      
      <ul style="margin-top: 0pt; margin-bottom: 0pt;">
        <li dir="ltr" style="list-style-type: circle; font-size: 15px; font-family: Arial; background-color: transparent; vertical-align: baseline;">
          <p dir="ltr" style="line-height: 1.15; margin-top: 0pt; margin-bottom: 0pt;">
            <span style="background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Integrated EDP portal page into web page</span>
          </p>
        </li>
        
        <li dir="ltr" style="list-style-type: circle; font-size: 15px; font-family: Arial; background-color: transparent; vertical-align: baseline;">
          <p dir="ltr" style="line-height: 1.15; margin-top: 0pt; margin-bottom: 0pt;">
            <span style="background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Pull user information from Trove / MySQL, push through pre-canned mapreduce file, output in Swift</span>
          </p>
        </li>
      </ul>
    </li>
    
    <li dir="ltr" style="list-style-type: disc; font-size: 15px; font-family: Arial; background-color: transparent; vertical-align: baseline;">
      <p dir="ltr" style="line-height: 1.15; margin-top: 0pt; margin-bottom: 0pt;">
        <span style="background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Docs &#8211; Create user documentation linked from web app using Docbooks pipeline</span>
      </p>
    </li>
  </ul>
  
  <h3>
    <span style="background-color: transparent; font-family: Arial; font-size: 15px; white-space: pre-wrap; line-height: 1.15;">Content Locations</span>
  </h3>
  
  <p dir="ltr" style="line-height: 1.15; margin-top: 0pt; margin-bottom: 0pt;">
    <span style="font-size: 15px; font-family: Arial; background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">Git Repo + Sub Folders</span>
  </p>
  
  <p dir="ltr" style="line-height: 1.15; margin-top: 0pt; margin-bottom: 0pt;">
    <span style="font-size: 15px; font-family: Arial; background-color: transparent; vertical-align: baseline; white-space: pre-wrap;"><a href="https://github.com/openstack/openstack-manuals/tree/master/doc/training-guides">https://github.com/openstack/openstack-manuals/tree/master/doc/training-guides</a></span>
  </p>
  
  <p dir="ltr" style="line-height: 1.15; margin-top: 0pt; margin-bottom: 0pt;">
    <p dir="ltr" style="line-height: 1.15; margin-top: 0pt; margin-bottom: 0pt;">
      <span style="font-family: Arial; font-size: 15px; line-height: 17px; white-space: pre-wrap;">Specific Files (day 2-4 of course)</span>
    </p>
    
    <p dir="ltr" style="line-height: 1.15; margin-top: 0pt; margin-bottom: 0pt;">
      <span style="font-size: 15px; font-family: Arial; background-color: transparent; vertical-align: baseline; white-space: pre-wrap;">bk003-ch005-developer-apis-day-two-lab.xml</span>
    </p>
    
    <p dir="ltr" style="line-height: 1.15; margin-top: 0pt; margin-bottom: 0pt;">
      <span style="background-color: transparent; font-family: Arial; font-size: 15px; white-space: pre-wrap; line-height: 1.15;">bk003-ch007-developer-apis-day-three-lab.xml</span>
    </p>
    
    <p dir="ltr" style="line-height: 1.15; margin-top: 0pt; margin-bottom: 0pt;">
      <span style="background-color: transparent; font-family: Arial; font-size: 15px; white-space: pre-wrap; line-height: 1.15;">bk003-ch009-developer-apis-day-four-lab.xml</span>
    </p>
    
    <h3>
      <span style="background-color: transparent; font-family: Arial; font-size: 15px; white-space: pre-wrap; line-height: 1.15;">Why I do this crazy stuff</span>
    </h3>
    
    <p dir="ltr" style="line-height: 1.15; margin-top: 0pt; margin-bottom: 0pt;">
      <span style="font-family: Arial;"><span style="font-size: 15px; line-height: 17px; white-space: pre-wrap;">I’m a core review on OpenStack docs, and co-founder of OpenStack training. My hippy streak runs strong, and I believe that by lowering barriers to adoption of platforms we will continue to get more Operators involved. Teaching developers to consume OpenStack is as important as teaching engineers to Operate and Install it. While this burns many nights and weekends, I absolutely love being a small part of this amazing community. And every once and a while what I do makes a difference. That is an epic win.</span></span>
    </p>
    
    <p dir="ltr" style="line-height: 1.15; margin-top: 0pt; margin-bottom: 0pt;">
      <span style="background-color: transparent; font-family: Arial; font-size: 15px; white-space: pre-wrap; line-height: 1.15;"> </span>
    </p>
    
    <h3>
    </h3>