---
id: 119
title: Encrypting your backup tapes with Cisco Storage Media Encryption (SME)
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/?p=119
permalink: /encrypting-your-backup-tapes-with-cisco-storage-media-encryption-sme/
categories:
  - CCIE Storage
  - CISCO
  - DC3.0
  - photography
  - sme
tags:
  - andiamo
  - breach
  - C
  - CISCO
  - Colin
  - encryption
  - GLBA
  - HIPPA
  - legal
  - mds
  - NDA
  - Provider
  - san
  - Sarbanes Oxley
  - security
  - sme
  - SOX
  - storage
  - storage media encryption
  - switch
  - tape
  - Technology
---
<p style="text-align: left;">
  IT staff at the University of Miami are having a <a href="http://www.storagenewsletter.com/news/tapes/university-miami-tapes-stolen" target="_blank">very bad week</a>. They are having to deal with the fact that two million private health records were stolen from from them. While it wasn&#8217;t directly their fault that their backup tapes were stolen from a off site storage providers transport van. The responsibility does fall on their shoulders to protect sensitive data no matter who has access to the physical media.
</p>

<img style="vertical-align: middle;" src="http://www.colinmcnamara.com/wp-content/gallery/breach/istock_000003413901xsmall.jpg" alt="" width="425" height="282" />

**Legal implications of a breach**

Losing control of personal data means means more then just replacing a tape in your backup rotation. Laws vary from state to state, however generally you are required to contact the identity holders who were breached, as well as fund some sort of remediation. This has huge implications on consumer confidence, and at the end of the day stock price of your company. In some cases, such as ChoicePoint a company can be completely decimated by a breach.

**Data protection regulations**

There are an ever increasing number of regulations that concern the control of sensitive data. These can vary from laws focused on patient data, to financial data, to personal identification data. The most most well known laws are HIPPA, GLBA, and Sarbanes Oxley (SOX). Past that there are laws that pop up every day at the state and municipality level that further increase the requirements and expense of dealing with a breach. In short, it is becoming an expensive and in some cases criminal offense to lose control of your sensitive.

**What you can do to protect your backup tapes**

First things first, putting a lock on that Iron Mountain box is just not good enough. You must assume that no matter what, a determined attacker will get physical access to your tapes. So many times companies thing that just because their data format is unique or proprietary that an attacker won&#8217;t be able to access it. The cold reality is that any format can be read, and yours is not that special.

The only way to be assured that your data is safe is to encrypt it with a complex cipher. In short, you need to treat your data the same way on tape as you would if it was sitting on a public ftp site (with anonymous access enabled). Luckily Cisco has a technology that allows you to encrypt and decrypt your data coming on and off tape. This technology is storage media encryption.

**Cisco Storage Media Encryption (SME)**

Cisco&#8217;s Storage Media Encryption (SME) technology allows for the seamless encryption of your data flows on and off your backup tapes using AES256 standard encryption. Whether you have VSANS segregating your data, a core / edge architecture, or Virtual Tape Libraries (VTL), you can use SME to protect your data at rest, removing the possibility of an attacker getting access to your critical data.<a href="http://www.cisco.com/en/US/products/ps8502/index.html" target="_blank"><br /> </a>

<a href="http://www.cisco.com/en/US/products/ps8502/index.html" target="_blank">Storage Media Encryption</a> works by leveraging a multifunction chipset available in the <a title="18/4 module" href="http://www.cisco.com/en/US/products/ps8425/index.html" target="_blank">18/4 module</a> that comes default with the 9222i and is an option for the 9500 series director class SAN switches. Chipset has a couple functions, including line rate encryption of iSCSI and FCIP data streams at gigabit speeds, as well as line rate encryption of data as it streams your tape or virtual tape library&#8217;s (VTL).

**Want to learn more ?**

<a title="SAN and NAS" href="http://www.amazon.com/gp/product/0596001533?ie=UTF8&tag=wwwcolinmcnam-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0596001533" target="_blank">SAN and NAS, Oreilly Press</a> &#8211; In the classic Oreilly style by W. Curtis Preston, this book is a great starting place to understanding the fundamentals of San and Nas architectures that many people are likely to face.

Storage Media Encryption for Cisco MDS SAN Switches &#8211; <a href="http://www.cisco.com/en/US/products/ps8502/index.html" target="_blank">http://www.cisco.com/en/US/products/ps8502/index.html</a> . Cisco has lumped together a couple good data sheets here, though I may have to write a future article taking a deap dive on what really drives SME.