---
id: 1003
title: Rebuilding the nvidia kernel module for Ubuntu
date: 2014-09-29T12:02:33+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=1003
permalink: /2014/09/rebuilding-the-nvidia-kernel-module-for-ubuntu/
categories:
  - Computerz
header-img: "img/post-bg-08.jpg"
---
I recently bought a GTX 750Ti which isn&#8217;t supported by Ubuntu&#8217;s drivers yet. So I installed the drivers from Nvidia itself. They work great, the card is very quiet and operates without getting hot at all. One problem: after running an Ubuntu update that updates your kernel it won&#8217;t work anymore.

<pre>sudo su
cd /usr/src
ls
</pre>

Examine the output:
  
My nvidia driver src location: /usr/src/nvidia-334.21

<pre>dkms build -m nvidia -v 334.21
dkms install -m nvidia -v 334.21
</pre>

If the commands fail on missing linux headers, install them:

<pre>sudo apt-get install linux-headers-$(uname -r)
</pre>

Now you have 2 options: Reboot or do a modprobe nvidia and restart X

Enjoy fancy Nvidia graphics again