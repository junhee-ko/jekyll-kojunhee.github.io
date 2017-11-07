---
id: 1415
title: Setting up Cobbler PXE auto-deployment for Ubuntu Server 12.04 Precise
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/?p=1415
permalink: /setting-up-cobbler-pxe-auto-deployment-for-ubuntu-server-12-04-precise/
al2fb_facebook_link_id:
  - 667137287_10151310546757288
  - 667137287_10151310546862288
al2fb_facebook_link_time:
  - 2012-11-12T18:20:39+00:00
al2fb_facebook_link_picture:
  - media=http://www.colinmcnamara.com/wp-content/uploads/2012/11/NewImage8-300x192.png
categories:
  - OpenStack
  - Ubuntu
tags:
  - Cobbler
  - openstack
  - Puppet
  - PXE
  - Ubuntu
---
For those that don&#8217;t use it, Cobbler is a PXE installation manager for automating the deployment of systems and packages. It is an order of magnitude simpler then creating a custom PXE environment by hand.

In this case I am setting up my Cobbler environment to automatically deploy a base operating system and then hand off to Puppet for further configuration. After handoff Puppet will configure the systems in a multi-node OpenStack setup which will rebuild nightly.

The purpose of that entire system this is to do development testing of the Quantum Networking Service for the spring Grizzly release. I will document the process for that in a later blog post.

What we will do today, is get the base system up and running for deploying your server operating systems using Cobbler.

### Installing Cobbler

First thing you need to do is install your base operating system. In this case since we are building out a lab environment to test OpenStack builds we should download and install ubuntu server 12.04 (precise).

Once this is up and configured with a static IP address, we need to install and configure cobbler

> <pre>sudo apt-get install cobbler cobbler-web</pre>

This will install Cobbler, and the Cobbler web interface. Next we will run a sanity check of cobbler

> <pre>sudo cobbler check</pre>

You may get some notifications of items that need to be addressed. Address as needed and run the check command to verify.

Next, you can set the username and password that you will use to manage the cobbler web interface. You can replace these items with whatever user / password you would like. In this case we have the username Cobbler and the password cobbler.

> <pre>htdigest /etc/cobbler/users.digest "Cobbler" cobbler</pre>

After you have successfully run cobbler check you will need to synchronize cobbler by running the cobbler-sync command

> <pre>cobbler sync</pre>

### Importing Ubuntu Server ISO&#8217;s

Next thing we need to do is grab the ISO that we used to install the server we are on, and import it into cobbler. In this case we are making a folder to mount a NFS export called VMwareISO on a NAS at 10.0.76.2

> <pre>sudo mkdir /mnt/VMwareISO</pre>
> 
> <pre>sudo mount 10.0.76.2:/volume1/VMwareISO /mnt/VMwareISO</pre>

Next we have to create an ISO mount point and mount the Ubuntu 12.04 ISO

> <pre>sudo mkdir /mnt/iso</pre>
> 
> <pre>sudo mount -o loop ubuntu-12.04-server-amd64.iso /mnt/iso</pre>

You will get the following message, and that is all right.

> mount: warning: /mnt/iso seems to be mounted read-only.

Next, we will import the ISO we just mounted into Cobbler.

> <pre>sudo cobbler import --name=ubuntu-server --path=/mnt --breed=ubuntu</pre>

### Configuring DHCP to point to your PXE server

This part will vary based on your lab setup. If you already have a DHCP server setup, then you need to set the &#8220;next-server &#8221; option to the ip address of your Cobbler server.

If you want to run DHCP on the same server you are using for Cobbler you need to install and configure a DHCP server.

> <pre>sudo apt-get instal isc-dhcp-server</pre>

Next we have to edit the configuration file /etc/dhcp/dhcpd.conf

> <pre>sudo vim /etc/dhcp/dhcpd.conf</pre>

Now you need to add a statement configuring a DHCP scope on this server. In this case I am using the following options &#8211;

  * Subnet 10.0.76.0/24
  * IP Address range 100-254
  * Router 10.0.76.1
  * DNS Server 10.0.76.10
  * PXE server (cobbler) 10.0.76.30

<div>
  Configuration to be added to dhcpd.conf
</div>

> subnet 10.0.76.0 netmask 255.255.255.0 { option routers 10.0.76.1; option domain-name-servers 10.0.76.10; option subnet-mask 255.255.255.0; range dynamic-bootp 10.0.76.100 10.0.76.254; filename &#8220;/pxelinux.0&#8243;; default-lease-time 21600; max-lease-time 43200; next-server 10.0.76.30;

Once this is added, restart the DHCP server to pick up your configuration

> <pre>sudo /etc/init.d/isc-dhcp-server restart</pre>

### Creating a custom seed file and pointing the Cobbler to it

FYI, this step may not be completely necessary in the future. However there is currently a bug open with Cobbler where when you are using it with a Ubuntu 12.04 file where the client installation will bomb out. You will get an error stating &#8220;Bad Archive Mirror An error has been detected while trying to use the specified archive mirror&#8221;

<img style="display: block; margin-left: auto; margin-right: auto; border: 0px none;" title="ubuntu-cobbler-error.png" src="http://www.colinmcnamara.com/wp-content/uploads/2012/11/ubuntu-cobbler-error.png" alt="ubuntu 12.04 cobbler error" width="480" height="365" border="0" />

If you dig through /var/log/syslog you will find a more descriptive error shown here below

> choose-mirror[3474] DEBUG command: wget -q <a href="http://gb.archive.ubuntu.com/ubuntu//dists/precise/Release" rel="nofollow">http://gb.archive.ubuntu.com/ubuntu//dists/precise/Release</a> -O &#8211; | grep -E &#8216;^(Suite|Codename):&#8217; choose-mirror[3474] WARNING **: broken mirror: invalid Suite or Codename in Release file for $suite

After a bit of digging I found a bug logged with Cobbler here &#8211; <https://bugs.launchpad.net/ubuntu/+source/cobbler/+bug/1000219>. the bug itself hasn&#8217;t been fixed. Luckily however there are a couple ways to work around this.

**Copying and Editing your new seed file**

Cobbler keeps it&#8217;s auto installation files for all different operating system types in /etc/cobbler/ in the next steps we explore this directory and create a new file based on a sample provided.

> <pre>cd /etc/cobbler</pre>
> 
> <pre>sudo cp ubuntu-server.preseed ubuntu-server.openstack.preseed</pre>

**Pointing cobbler to the new file**

The next  thing we need to do, is log into our Cobbler web interface to and make sure things are working.

> <pre>your favorite web browser - http://&lt;yourservername&gt;/cobbler_web/ with username Cobbler password cobbler (or whatever username and pass you provided)</pre>

&nbsp;

<img style="display: block; margin-left: auto; margin-right: auto; border: 0px none;" title="cobbler-web.png" src="http://www.colinmcnamara.com/wp-content/uploads/2012/11/NewImage8.png" alt="cobbler web login image" width="480" height="307" border="0" />

Next we need to navigate to **PROFILES **and click on **EDIT** to edit *ubuntu-server-x86_64 *instance

<img style="display: block; margin-left: auto; margin-right: auto; border: 0px none;" title="Cobbler-profiles.png" src="http://www.colinmcnamara.com/wp-content/uploads/2012/11/Cobbler-profiles.png" alt="cobbler profiles" width="480" height="269" border="0" />

You will see a screen with a bunch of form fields. You need to navigate down to the &#8220;Kickstart&#8221; option and change from

> <pre>/var/lib/cobbler/kickstarts/sample.seed</pre>

to the file we have just changed sample.seed.precise

> <pre>/etc/cobbler/ubuntu-server.openstack.preseed</pre>

As you can see, all we did was add .precise to the end of the sample.seed file name.

<img style="display: block; margin-left: auto; margin-right: auto; border: 0px none;" title="cobbler-preseed-location.png" src="http://www.colinmcnamara.com/wp-content/uploads/2012/11/cobbler-preseed-location.png" alt="cobbler preseed location" width="504" height="126" border="0" />

Click save, and now you should be ready to PXE install your first Ubuntu server. (if you use this file your username / pass will be ubuntu/ubuntu)

### **Whats Next?**

In the next blog post in this series we will configure Puppet Master on our server and do a super dangerous thing &#8211; optimize our seed files to blow away our file system without any user interaction necessary. Needless to say we will all need to use this next one with caution&#8230;.

&nbsp;