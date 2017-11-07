---
id: 1767
title: Fixing Git Rebase failure on Mac OS X
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/?p=1767
permalink: /fixing-git-rebase-failure-on-mac-os-x/
categories:
  - devops
tags:
  - git
  - mac
  - rebase
---
I just got done pulling my hair out for a couple hours chasing down random rebase errors for some simple commits to OpenDaylight from my Mac laptop.

For those that haven&#8217;t made the jump from network engineering to network development, a rebase is when you take a number of commits (saves) to your local working branch and squash them together into one large commit to push up to your Git or Gerrit server.

Apparently what is happening &#8211; (as highlighted on StackOverflow &#8211; http://stackoverflow.com/questions/5074136/git-rebase-fails-your-local-changes-to-the-following-files-would-be-overwritte ) is that the Mac file revision tracker &#8211; RevisionD is changing the timestamps of local files. This causes git to think that you have changed a file that has no changes in it&#8217;s content.

## Solution to git rebase error on Mac OS X

In your terminal execute the following command telling git to stop relying on file system information alone &#8211;

git config &#8211;global core.trustctime false

Hope this helps others save a bit more hair then me.

&#8211;Colin