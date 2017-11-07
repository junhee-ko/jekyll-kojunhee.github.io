---
id: 978
title: Tuning Hadoop and Hadoop driven applications
author: colinmcnamara
layout: post
guid: http://www.colinmcnamara.com/?p=978
permalink: /tuning-hadoop-and-hadoop-driven-applications/
categories:
  - Hadoop
tags:
  - analytics
  - chunks
  - commodity hardware
  - financial transactions
  - gfs
  - Hadoop
  - jeremy zawodny
  - latency requirements
  - open source framework
  - open source technologies
  - web search indexes
  - web service
---
<img class="alignnone" title="hadoop-nutch-1" src="http://www.colinmcnamara.com/wp-content/gallery/hadoop/hadoop-nutch-1.jpg" alt="" width="395" height="208" />

Hadoop is an open source framework for processing and querying big data on clusters of commodity hardware. It was originally developed by Yahoo in 2006 as a clone of Google File System (GFS) and MapReduce framework used to store web search indexes and crawl data for the search engine Nutch.

In the last few years however developers have embraced MapReduce (the ability to map key pairs, and reduce them into small byte size computing chunks to distribute across hybrid storage/processing nodes), and have begun developing a vast array of applications that can utilize the distributed storage and compute capacity.

### **My Background with Hadoop**

Back in 2006 I working for a startup in San Diego that did high dimensional mathematical analysis of financial transactions to quantify identity theft risk. Over the time I was there we went from an scale up batch system to serving 10,000 transactions a day to a scale out web service (today you would call it a cloud) that served millions of transactions a day all served under 250 milliseconds each.

To scale to that size under such strict latency requirements it was necessary to experiment with and implement some pretty cutting edge open source technologies. I cheated off the notes of Jeremy Zawodny at Yahoo almost daily (thanks Jeremy, your knowledge and tools totally saved my butt many times). At that same time Jeremy&#8217;s team started doing some interesting work around distributed computing with Hadoop. Needless to say this was a technology I had to try. Hadoop was extremely young at the time, however for certain analytics workloads I was able to use 10 PC&#8217;s to outperform a half million dollars in compute and fibre channel storage.

### **Flash forward 6 years &#8211; Hadoop is all grown up**

[singlepic id=169 w=320 h=240 float=]

Over the past six years not only has Hadoops file system (HDFS) and processing (MapReduce) capabilities matured, but a suite of applications has been developed. These include tools to managed Hadoop clusters, large scale log analysis tools, scale out analytics packages and large scale distributed database applications.

The list of clients using hadoop has grown too. This ranges from Yahoo, Ebay and Facebook to enterprise customers like Fox, TMobile, Equifax and the New York Stock Exchange using Greenplum (Project R running on Hadoop). No longer is Hadoop a tool for a select few, it is now the next logical extension of the standard web service LAMP stack, and increasingly useful for Data Warehouse workloads.

### **Tuning the foundation &#8211; Hadoop and MapReduce**

**[singlepic id=170 w=320 h=240 float=]**

Many times when people talk about tuning parallel compute clusters like Hadoop, SunGrid or LSF they forget the obvious. They forget that the squeezing performance is about managing the delicate balance between applications and infrastructure.  When tuning that balance, you have to first segregate applications that directly access the hardware resources, and applications that access these apps. To create a frame of reference think of the relationship between Apache, MySQL and Disks in a LAMP architecture.

When dealing with Hadoop Distributed File System (HDFS) and the MapReduce jobs that run on it there are three primary dimensions of tuning. These are dimensions are &#8211;

1. Tuning keystones in the infrastructure such as optimizing NameNode and Job Tracker server performance. (note memory sizing, tcp performance, cpu scaling)

2. Optimizing transfer of data between slave nodes in the HDFS cluster (note, bundled 1 gig / CPU)

3. Balancing I/O systems in slave nodes such as memory, server side flash, and spinning disk.

**Optimizing NameNode and Job Tracker server performance**

The NameNode in a Hadoop cluster is used to track the locations of the different file shards distributed across all slave nodes in the cluster. It is also used to house metadata for certain applications that reside in the Hadoop cluster. This puts specific strain on CPU, Memory and Network interfaces.

**CPU / Network Interface  
**

Certain processes inside of the name node do not take advantage of the multitude of cores available on today&#8217;s servers. The biggest offender in this case is the RPC server which processes network requests in a serial manner. Utilizing the fastest CPU as possible in conjunction with low latency network adapters such as Mellanox MNPH29D-XTR 10 Gig NIC, and low latency fabric switches such as the Nexus 5548. Optimizing the CPU and Network interface has significant effect on minimizing bottlenecks due to serialization delay of RPC requests.

**Memory**

NameNodes can use a lot of memory when servicing HDFS alone. The addition of layered applications on top of HDFS that utilize the NameNode as well as the increase in file numbers in HDFS only increase the importance of sufficient amounts of high speed memory.

**Optimizing transfers between nodes in the HDFS cluster**

Certain types of jobs such as sorts and greps (the basis for index generation) move significant amounts of data between nodes in the Hadoop cluster. Since the inception of Intel&#8217;s Nehalem processor family, single gigabit interface have presented bottlenecks when transmitting and receiving data. This inserts &#8220;slack time&#8221; in the cluster minimizing the time that slave node is actually processing data. The net result of this equals either slower job completion / response times or the unnecessary addition of additional nodes to the cluster (increasing your cost per job/transaction).

**Impact of server bandwidth on job completion time  
**

**[singlepic id=171 w=500 h=420 float=]**

To illustrate this point please reference this test done by Intel on their own Hadoop cluster with a first generation Nehalem processor. Even then a single gigabit interface was not sufficient to service a node. In this case doubling the bandwidth to two gigabit by bonding interfaces together rebalanced the node. However if you follow Moore&#8217;s law, nodes utilizing Sandy Bridge CPU&#8217;s (due to release some time in 2012) will need four plus gigabit of network during a data transfer to avoid unnecessary wait times. Luckily this generation of server will have 10 Gig adapters built into the motherboard.

**Network bandwidth and design**

[singlepic id=172 w=500 h=400 float=]

HDFS and the many of the applications that reside on top of it have the notion of a Rack ID. This can be used for fault isolation. For example if you had A/B racks on different power feeds you could ensure that redundant data shards are stored on nodes in different racks, and therefore increase the systems tolerance of faults.

This Rack Id can also be queried by higher level applications to ensure that jobs requiring high bandwidth data transfers are localized within say a pair of Nexus 5500&#8217;s with 10 gig fabric extenders. This would minimize the utilization of typically oversubscribed uplinks north of the access layer ensuring again, that nodes are not sitting idle while receiving data.

If however your application requirements do force you to expand jobs beyond the scaling capacity of a pair of low latency fabric extended switches. Maximizing your active paths between pods (groupings with the same rack.id) utilizing tools like Fabric Path create a layer two mesh between your pods can help in minimizing the wait time that a node may experience.

**Minimizing I/O wait times in disk subsystems**

There are many places where RAID or higher performance disk systems can yield benefits in the Hadoop cluster. One place is the MapReduce local directory. This is the place that mapped files are stored locally, adding multiple disks to this mount is one option. A second option which is gaining more and more traction is utilizing Solid State Disk (SSD) or PCIe based flash cards to present optimal IO for certain functions.

[singlepic id=173 w=500 h=400 float=]

The graphic above, again from Intel demonstrates in a very simple fashion the impact of going from two to four disks in a node (doubling the IO). The result was completing the required job in one half the time. In simple terms, increasing the cost of the server by 10% increased its sort performance by 100%. Again performance increases vary by workload. However in a strict sense this increases the per server cost while decreasing the cost per job / transaction.

**Reducing the Impact of Disk Spill  
**

Disk spill is the result of the majority of the servers buffer being full of data during the map operation. Once a certain percentage of utilization is hit (normally 80%) a job is kicked off to write this data to disk, making room for more data. Adding more memory to the server to be used as a buffer for the Map operation minimizes disk spill ratio&#8217;s. This may increase the per server costs, but depending on your workload may end up your cost per job/transaction due to more efficient operation of your nodes. A second option, first explored by Intel in their chipset design clusters is to extend RAM into solid state cards inside of their servers.

**Bringing it all together**

Hadoop  supports a suite of applications that are used from the worlds largest web service providers to large enterprises. Uses include Data Warehousing, Analytics, Log analysis and large horizontally scaled databases.

Similar to other parallel compute systems such as Sun Grid Engine, or Platform LSF, a system wide approach to performance tuning must be used to ensure optimal performance as measured by cost per job / transaction. This system wide approach include server optimizations for specific server roles server roles such as large memory and PCIe Flash cards. As well as utilization of network equipment and topologies such as Nexus 5500 and fabric extenders to create low latency high bandwidth back planes ideally suited for Hadoop clusters.

**Want to learn more?**

Yahoo developers network Hadoop blog &#8211; <a href="http://developer.yahoo.com/hadoop/" target="_blank">http://developer.yahoo.com/hadoop/</a>

Hadoop Distributed File Systems Architecture Guide &#8211; <a href="http://hadoop.apache.org/common/docs/current/hdfs_design.html" target="_blank">http://hadoop.apache.org/common/docs/current/hdfs_design.html</a>

Big Data Network Design Considerations (Cisco) &#8211; <a href="http://www.cisco.com/en/US/prod/collateral/switches/ps9441/ps9670/white_paper_c11-690561.html" target="_blank">http://www.cisco.com/en/US/prod/collateral/switches/ps9441/ps9670/white_paper_c11-690561.html</a>

Hadoop and Hbase applications for read intensive search &#8211; <a href="http://software.intel.com/en-us/articles/hadoop-and-hbase-optimization-for-read-intensive-search-applications/" target="_blank">http://software.intel.com/en-us/articles/hadoop-and-hbase-optimization-for-read-intensive-search-applications/</a>

Evolution of Google File System &#8211; <a href="http://queue.acm.org/detail.cfm?id=1594206" target="_blank">http://queue.acm.org/detail.cfm?id=1594206</a>

&nbsp;

**  
**