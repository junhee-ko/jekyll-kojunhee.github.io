---
id: 1772
title: 'Fixing your WordPress Blog &#8211; MySQL failing due to corrupted tables'
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/?p=1772
permalink: /fixing-your-wordpress-blog-mysql-failing-due-to-corrupted-tables/
categories:
  - devops
tags:
  - crash
  - mysql
  - wordpress
---
It is 6am in the morning, and I am fixing my self hosted WordPress blog. All I wanted to do was post a simple note about my first merge into OpenDaylight. Instead I’m fixing WordPress and MySQL&#8230;..

## What do I see this morning &#8211; Error establishing a database connection

My site keeps going down because the MySQL instance on the backend keeps failing.

<img style="display: block; margin-left: auto; margin-right: auto;" title="broke-blog.png" alt="broke blog" src="http://www.colinmcnamara.com/wp-content/uploads/2013/12/broke-blog.png" width="500" height="154" border="0" />

When i log in I check MySQL status, see that it is locked up and restart it to get things working again

> [cmcnamara@www2 ~]$ sudo /etc/init.d/mysqld status [sudo] password for cmcnamara:  
> mysqld dead but subsys locked  
> [cmcnamara@www2 ~]$ sudo /etc/init.d/mysqld restart  
> Stopping mysqld: [ OK ]  
> Starting mysqld: [ OK ]

Why is it failing? Because the cobblers son has no shoes. In real world terms my personal Linux instances aren&#8217;t exactly taken care of. Specifically I had a WordPress backup job that ran my system out of space. This caused tables in MySQL to get corrupted, evidenced my tailing /var/log/mysqld.log

> [cmcnamara@www2 ~]$ sudo tail -10f /var/log/mysqld.log [sudo] password for cmcnamara: 131230 14:23:54 [ERROR] /usr/libexec/mysqld: Table &#8216;./wpblog\_cmcnamara/securewp\_fs\_visits&#8217; is marked as crashed and should be repaired 131230 14:23:54 [ERROR] /usr/libexec/mysqld: Table &#8216;./wpblog\_cmcnamara/securewp\_fs\_visits&#8217; is marked as crashed and should be repaired 131230 14:23:54 [ERROR] /usr/libexec/mysqld: Table &#8216;./wpblog\_cmcnamara/securewp\_fs\_visits&#8217; is marked as crashed and should be repaired 131230 14:23:54 [ERROR] /usr/libexec/mysqld: Table &#8216;./wpblog\_cmcnamara/securewp\_fs\_visits&#8217; is marked as crashed and should be repaired 131230 14:23:54 [ERROR] /usr/libexec/mysqld: Table &#8216;./wpblog\_cmcnamara/securewp\_fs\_visits&#8217; is marked as crashed and should be repaired 131230 14:23:54 [ERROR] /usr/libexec/mysqld: Table &#8216;./wpblog\_cmcnamara/securewp\_fs\_visits&#8217; is marked as crashed and should be repaired 131230 14:24:29 [ERROR] /usr/libexec/mysqld: Table &#8216;./openchimpphpbb/phpbb\_sessions&#8217; is marked as crashed and should be repaired 131230 14:24:29 [ERROR] /usr/libexec/mysqld: Table &#8216;./openchimpphpbb/phpbb\_sessions&#8217; is marked as crashed and should be repaired 131230 14:25:56 [ERROR] /usr/libexec/mysqld: Table &#8216;./openchimpphpbb/phpbb\_sessions&#8217; is marked as crashed and should be repaired 131230 14:25:56 [ERROR] /usr/libexec/mysqld: Table &#8216;./openchimpphpbb/phpbb\_sessions&#8217; is marked as crashed and should be repaired

## Fixing the MySQL crash

### Taking a snapshot of your system

Ok, let&#8217;s fix this crap. First things first, when working on systems that are non-ephemeral (that have state) I always like to trigger a snapshot. In this case I use RimuHosting for my blog (and a bunch of other blogs). So I am going to log into the console and trigger a snapshot.

<img style="display: block; margin-left: auto; margin-right: auto;" title="rimuhosting-backup.png" alt="rimuhosting-backup" src="http://www.colinmcnamara.com/wp-content/uploads/2013/12/rimuhosting-backup.png" width="500" height="335" border="0" />

That takes a couple minutes to run, get some coffee, bang your head into the table, whatever makes you feel good. When it is done,

### Using mysqlcheck

Now let’s get down to the root of the problem, corrupted MySQL tables. There are a couple ways that you can fix them. Some are super complicated, some are super easy. In this case we are going to check our MySQL database using mysqlcheck —all-databases

> <p style="margin: 0px; font-size: 11px; font-family: Menlo;">
>   [cmcnamara@www2 ~]$ <strong>sudo mysqlcheck &#8211;all-databases</strong>
> </p>
> 
> <p style="margin: 0px; font-size: 11px; font-family: Menlo;">
>   [sudo] password for cmcnamara:
> </p>
> 
> <p style="margin: 0px; font-size: 11px; font-family: Menlo;">
>   actionsoscom.address_book                          OK
> </p>
> 
> <p style="margin: 0px; font-size: 11px; font-family: Menlo;">
>   actionsoscom.address_format                        OK
> </p>
> 
> <p style="margin: 0px; font-size: 11px; font-family: Menlo;">
>   actionsoscom.administrators                        OK
> </p>
> 
> <p style="margin: 0px; font-size: 11px; font-family: Menlo;">
>   …. (removed a bunch of redundant messages —
> </p>
> 
> <p style="margin: 0px; font-size: 11px; font-family: Menlo;">
>   status   : OK
> </p>
> 
> <p style="margin: 0px; font-size: 11px; font-family: Menlo;">
>   <strong>wpblog_cmcnamara.securewp_fs_visits</strong>
> </p>
> 
> <p style="margin: 0px; font-size: 11px; font-family: Menlo;">
>   <strong>warning  : Table is marked as crashed</strong>
> </p>
> 
> <p style="margin: 0px; font-size: 11px; font-family: Menlo;">
>   <strong>warning  : 25 clients are using or haven&#8217;t closed the table properly</strong>
> </p>
> 
> <p style="margin: 0px; font-size: 11px; font-family: Menlo;">
>   <strong>error    : Checksum for key:  2 doesn&#8217;t match checksum for records</strong>
> </p>
> 
> <p style="margin: 0px; font-size: 11px; font-family: Menlo;">
>   <strong>error    : Checksum for key:  4 doesn&#8217;t match checksum for records</strong>
> </p>
> 
> <p style="margin: 0px; font-size: 11px; font-family: Menlo;">
>   <strong>error    : Corrupt</strong>
> </p>
> 
> <p style="margin: 0px; font-size: 11px; font-family: Menlo;">
>   wpblog_cmcnamara.securewp_in_series_3_0_11_auth    OK
> </p>
> 
> <p style="margin: 0px; font-size: 11px; font-family: Menlo;">
>   wpblog_cmcnamara.securewp_in_series_3_0_11_entries OK
> </p>

As you can see in the bold items, I have some corrupt tables. What to do?

  1. You can drop the table if it is from a plugin that you don’t care about.
  2. You can fix the table

Let’s fix the table &#8211;

> <p style="margin: 0px; font-size: 11px; font-family: Menlo;">
>   [cmcnamara@www2 ~]$ <strong>sudo mysqlcheck &#8211;repair &#8211;all-databases</strong>
> </p>
> 
> <p style="margin: 0px; font-size: 11px; font-family: Menlo;">
>   [sudo] password for cmcnamara:
> </p>
> 
> <p style="margin: 0px; font-size: 11px; font-family: Menlo;">
>   actionsoscom.address_book                          OK
> </p>
> 
> <p style="margin: 0px; font-size: 11px; font-family: Menlo;">
>   actionsoscom.address_format                        OK
> </p>
> 
> <p style="margin: 0px; font-size: 11px; font-family: Menlo;">
>   actionsoscom.administrators                        OK
> </p>
> 
> <p style="margin: 0px; font-size: 11px; font-family: Menlo;">
>   openchimpphpbb.phpbb_search_wordlist               OK
> </p>
> 
> <p style="margin: 0px; font-size: 11px; font-family: Menlo;">
>   <strong>openchimpphpbb.phpbb_search_wordmatch              OK</strong>
> </p>
> 
> <p style="margin: 0px; font-size: 11px; font-family: Menlo;">
>   <strong>openchimpphpbb.phpbb_sessions</strong>
> </p>
> 
> <p style="margin: 0px; font-size: 11px; font-family: Menlo;">
>   <strong>warning  : Number of rows changed from 20137 to 20197</strong>
> </p>
> 
> <p style="margin: 0px; font-size: 11px; font-family: Menlo;">
>   <strong>status   : OK</strong>
> </p>

<p style="margin: 0px; font-size: 11px; font-family: Menlo;">
  <strong> </strong>
</p>

<p style="margin: 0px; font-size: 11px; font-family: Menlo;">
  As you can see, the number of rows in <strong style="font-family: Menlo; font-size: 11px;">openchimpphpbb.phpbb_sessions </strong><span style="font-family: Menlo; font-size: 11px;">changed form 20137 to 20197. and when I run </span>
</p>

<p style="margin: 0px; font-size: 11px; font-family: Menlo; padding-left: 30px;">
  sudo mysqlcheck &#8211;all-databases again, everything shows up as ok.
</p>

Next, I’m going to restart MySQL. This not necessary to repair the DB. However sometimes error’s creep up on restart. It’s best to observe those when you have just made some changes and they are fresh in your mind. So lets restart MySQL and verify everything still works.

> <p style="margin: 0px; font-size: 11px; font-family: Menlo;">
>   [cmcnamara@www2 ~]$ sudo /etc/init.d/mysqld restart
> </p>
> 
> <p style="margin: 0px; font-size: 11px; font-family: Menlo;">
>   Stopping mysqld:                                           [<span style="color: #34bd26;">  OK  </span>]
> </p>
> 
> <p style="margin: 0px; font-size: 11px; font-family: Menlo;">
>   Starting mysqld:                                           [<span style="color: #34bd26;">  OK  </span>]
> </p>
> 
> <p style="margin: 0px; font-size: 11px; font-family: Menlo;">
>   [cmcnamara@www2 ~]$
> </p>
> 
> <p style="margin: 0px; font-size: 11px; font-family: Menlo;">
>   </blockquote> 
>   
>   <h2>
>     WIN!!
>   </h2>
>   
>   <p>
>     There you have it, if your WordPress blog keeps crashing. It may be because of a borked MySQL instance. You can use mysqcheck to check and repair corrupted tables in your database, and get back to blogging.
>   </p>
>   
>   <h2>
>     Resources
>   </h2>
>   
>   <p>
>     MySQL Dev Docs &#8211; <a href="http://dev.mysql.com/doc/refman/5.0/en/rebuilding-tables.html">Rebuilding or Repairing Tables or Indexes</a>
>   </p>
>   
>   <p>
>     RimuHosting &#8211; <a href="http://rimuhosting.com/?r=6053414aa51e6c7a2d97931a7cf85e88">RimuHosting Virtual Servers &#8211; Awesome Sysadmins</a>
>   </p>
>   
>   <p>
>     &nbsp;
>   </p>
>   
>   <p>
>     &nbsp;
>   </p>