---
id: 1545
title: Puppet syntax highlighting using TextMate2
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/?p=1545
permalink: /puppet-syntax-highlighting-using-textmate2/
categories:
  - chef
  - continuous integration
  - devops
  - puppet
tags:
  - chef
  - DevOps
  - Puppet
  - textmate
  - textmate2
  - tmbundle
---
Do you use Puppet to manage your infrastructure? Are you like me and absolutely love TextMate2? If so you are probably pulling your hair out getting syntax highlighting working with TextMate2.

<img style="display: block; margin-left: auto; margin-right: auto;" title="Frustrated-Engineer-Puppet-TextMate.jpg" alt="Frustrated Engineer Puppet TextMate" src="http://www.colinmcnamara.com/wp-content/uploads/2013/06/Frustrated-Engineer-Puppet-TextMate.jpg" width="500" height="333" border="0" />

&nbsp;

The original version of TextMate had a very wide array of bundles (called tmbundles) that extended its functionality. When TextMate2 was released, it did not have the ability to import older bundles written for version 1.

It does ship with a large amount of built in bundles, however Puppet and Chef don&#8217;t ship by default. So, instead of pretty highlighting calling out syntax errors that you have made (or showing how awesome as job you have done) you get a bland white output show below.

<img style="display: block; margin-left: auto; margin-right: auto;" title="textmate-puppet-plain.png" alt="textmate-puppet-plain" src="http://www.colinmcnamara.com/wp-content/uploads/2013/06/textmate-puppet-plain.png" width="500" height="225" border="0" />

&nbsp;

Enter in Matthew Barr and is super awesome Puppet CI work. Very specifically, his puppet TextMate Bundle that works with TextMate2 &#8211; <https://github.com/matthewbarr/puppet-textmate.tmbundle>

<img style="display: block; margin-left: auto; margin-right: auto;" title="puppet-textmate2-bundle.png" alt="puppet textmate2 bundle" src="http://www.colinmcnamara.com/wp-content/uploads/2013/06/puppet-textmate2-bundle.png" width="500" height="318" border="0" />

Installation is pretty simple (you don&#8217;t have to use git if you don&#8217;t want).

  1. Click on the ZIP button to download
  2. Unzip the file puppet-textmate.tmbundle-master.zip
  3. Rename the resulting folder from puppet-textmate.tmbundle-master  to puppet-textmate.tmbundle
  4. Double click on the file puppet-textmate.tmbundle to import

Now that you have that installed. You now can choose puppet the puppet module instead of plain yet and you end up with beautifully highlighted code.

<img title="hightlighted-puppet-textmate.png" alt="hightlighted puppett extmate" src="http://www.colinmcnamara.com/wp-content/uploads/2013/06/hightlighted-puppet-textmate.png" width="500" height="224" border="0" />

&nbsp;

Resources &#8211;

TextMate2 &#8211; Open Source Text Editor  &#8211; <http://macromates.com/>

Matthew Barr&#8217;s TextMate2 Puppet bundle &#8211; <https://github.com/matthewbarr/puppet-textmate.tmbundle>

&nbsp;

&nbsp;

&nbsp;