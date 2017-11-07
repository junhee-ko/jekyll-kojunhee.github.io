---
id: 1731
title: Diverging from IETF and IEEE specifications at the northbound AS boundary of OpenStack
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/?p=1731
permalink: /diverging-from-ietf-and-ieee-specifications-at-the-northbound-as-boundary-of-openstack/
categories:
  - OpenStack
tags:
  - IETF
  - Neutron
  - openstack
---
<p style="margin: 24px 0px 0px; font-size: 14px; font-family: Cambria;">
  <span style="letter-spacing: 0.2px;">I have a couple concerns that I don’t feel I clearly communicated during the L3 advanced features session. I’d like to take this opportunity to both clearly communicate my thoughts, as well as start a discussion around them.</span>
</p>

<p style="margin: 0px; font-size: 14px; font-family: Cochin; min-height: 17px;">
  <strong style="letter-spacing: 0.2px; font-family: Cambria; font-size: 13px;"> </strong>
</p>

<p style="margin: 0px; font-size: 14px; font-family: Cochin; min-height: 17px;">
  <strong style="letter-spacing: 0.2px; font-family: Cambria; font-size: 13px;">Building to the edge of the &#8220;autonomous system&#8221;</strong>
</p>

<p style="margin: 24px 0px 0px; font-size: 14px; font-family: Cambria;">
  <span style="letter-spacing: 0.2px;">The current state of neutron implementation is functionally the l2 domain and simple l3 services that are part of a larger autonomous system. The routers and switches northbound of the OpenStack networking layer handled the abstraction and integration of the components.</span>
</p>

<p style="margin: 24px 0px 0px; font-size: 14px; font-family: Cambria;">
  <span style="letter-spacing: 0.2px;">Note, I use the term “Autonomous System” to describe more then the notion of BGP AS, but more broadly in the term of a system that is controlled within a common framework and methodology, and integrates with a peer system that doesn’t not share that same scope or method of control</span>
</p>

<p style="margin: 24px 0px 0px; font-size: 14px; font-family: Cambria;">
  <span style="letter-spacing: 0.2px;">These components that composed the autonomous system boundary implement protocols and standards that map into IETF and IEEE standards. The reasoning for this is interoperability. Before vendors utilize IETF for interoperability at this layer, the provider experience was horrible (this was my personal experience in the late 90’s).</span>
</p>

<p style="margin: 0px; font-size: 14px; font-family: Cochin; min-height: 17px;">
  <p style="margin: 24px 0px 0px; font-size: 14px; font-family: Cambria;">
    <span style="letter-spacing: 0.2px;"><strong>Wednesdays discussions in the Neutron Design Sessions</strong></span>
  </p>
  
  <p style="margin: 24px 0px 0px; font-size: 14px; font-family: Cambria;">
    <span style="letter-spacing: 0.2px;">A couple of the discussions, most notably the extension of l3 functionality fell within the scope of starting the process of extending Neutron with functionality that will result (eventually) in the ability for an OpenStack installation to operate as it’s own Autonomous System.</span>
  </p>
  
  <p style="margin: 24px 0px 0px; font-size: 14px; font-family: Cambria;">
    <span style="letter-spacing: 0.2px;">The discussions that occurred to support L3 advanced functionality (northbound boundary), and the QOS extension functionality both fell into the scope of Northbound and Southbound boundaries of this system.</span>
  </p>
  
  <p style="margin: 10px 0px 0px; font-size: 13px; font-family: Cambria;">
    <span style="letter-spacing: 0.2px;"><strong>My comments in the session</strong></span>
  </p>
  
  <p style="margin: 10px 0px 0px; font-size: 13px; font-family: Cambria;">
    <span style="letter-spacing: 0.2px;">My comments in the session, while clouded with jet-lag were specifically around two concepts that are used when integrating other types of systems </span>
  </p>
  
  <p style="margin: 10px 0px 0px; font-size: 13px; font-family: Cambria;">
    <span style="letter-spacing: 0.2px;">1. In a simple (1-8) tenant environment integration with a northbound AS is normally done in a PE-CE model that generally centers around mapping dot1q tags into the appropriate northbound l3 segments and then handling the availability of the L2 path that traverses with port channeling, MLAG, STP, Etc.</span>
  </p>
  
  <p style="margin: 10px 0px 0px; font-size: 13px; font-family: Cambria;">
    <span style="letter-spacing: 0.2px;">2. In a complex environment (8+ for discussion) different Carrier Supporting Carrier (CSC) methods defined in IETF RFC 4364 Section 10 type A, B or C are used. These allow the mapping of segregated tenant networks together and synchronizing between distributed systems. This normally extends the tagging or tunneling mechanism and then allows for BGP to synchronize NLRI information between AS’s.</span>
  </p>
  
  <p style="margin: 10px 0px 0px; font-size: 13px; font-family: Cambria;">
    <span style="letter-spacing: 0.2px;">These are the standard ways of integrating between carriers, but also components of these implementations are used to integrate and scale inside of a single web scale data center. Commonly when you scale beyond a certain physical port boundary (1000is edge ports in many implementations, much larger in current implementations) the same designs for C2C integrations are used to create network availability zones inside a web scale data center. </span>
  </p>
  
  <p style="margin: 10px 0px 0px; font-size: 13px; font-family: Cambria;">
    <span style="letter-spacing: 0.2px;"><strong>Support of these IETF and IEEE standard integrations are necessary for brown field installations</strong></span>
  </p>
  
  <p style="margin: 10px 0px 0px; font-size: 13px; font-family: Cambria;">
    <span style="letter-spacing: 0.2px;">In a green field installation, diverging from IETF and IEEE standards on the north bound edge while not a great idea, can result in a functional implementation. In a brown field implementation where OpenStack Neutron will be integrated into an existing network core. This boundary layer is where we move from a controlled system into a distributed system. The cleanly integrate into this system, IETF and IEEE protocols and standards have to be followed. </span>
  </p>
  
  <p style="margin: 0px; font-size: 12px;">
    <p style="margin: 0px; font-size: 12px;">
      <img style="display: block; margin-left: auto; margin-right: auto;" title="neutron-as-boundary.png" alt="neutron-as-boundary" src="http://www.colinmcnamara.com/wp-content/uploads/2013/11/neutron-as-boundary.png" width="500" height="239" border="0" /><span style="font-family: Cambria; font-size: 13px; letter-spacing: 0.2px;">When we diverge from this standards based integration at the north edge of our autonomous system we lose the ability to integrate without introducing major changes (and risk), into our core. In my experience this is sufficient to either slow or stall adoption. This is a major risk, that I believe can be mitigated.</span>
    </p>
    
    <p style="margin: 10px 0px 0px; font-size: 11px; font-family: Cambria;">
      <span style="letter-spacing: 0.2px;"><strong>My thoughts on mitigating this risk</strong></span>
    </p>
    
    <p style="margin: 10px 0px 0px; font-size: 11px; font-family: Cambria;">
      <span style="letter-spacing: 0.2px;">We need to at least map and track the relevant IETF RFC’s that define the internet standards for integration at the AS boundary. I know that many of the network vendor developers that contribute to Neutron have access to people who both have deep knowledge of these standards, and also participate in the IETF working groups. I would hope that these resources could be leveraged to at least give a sanity check, at best ensure a compliant northbound interface to other systems.</span>
    </p>
    
    <p style="margin: 10px 0px 0px; font-size: 13px; font-family: Cambria;">
      <span style="letter-spacing: 0.2px;"><strong>Side benefit of engaging IETF members in this discussion</strong></span>
    </p>
    
    <p style="margin: 10px 0px 0px; font-size: 11px; font-family: Cambria;">
      <span style="letter-spacing: 0.2px;">The other side benefit of this is that inventions inside of Neutron can also be communicated as standards to the rest of the world in the form of net new RFC’s. In OVS this has already happened, as OVS has emerged to be a common component in many network devices, and the need to establish and reference a common standard has risen it’s head. I would think that inventions within Neutron would follow this same path.</span>
    </p>
    
    <p style="margin: 10px 0px 0px; font-size: 11px; font-family: Cambria;">
      <p style="margin: 10px 0px 0px; font-size: 13px; font-family: Cambria;">
        <div>
          <span style="letter-spacing: 0.2px;"> </span>
        </div>