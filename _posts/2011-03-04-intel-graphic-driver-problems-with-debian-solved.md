---
id: 144
title: Intel graphic driver problems with debian solved
date: 2011-03-04T23:09:48+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=144
permalink: /2011/03/intel-graphic-driver-problems-with-debian-solved/
categories:
  - Computerz
---
The OS we use in our appliances is based on Debian. We switched from ubuntu to debian mainly for it&#8217;s stability.

The ubuntu rapid changes are sometimes not good for the stability and released to soon, resulting in Black Screen of Dead (BOD) for example for a lot of intel graphic card users after the update from ubuntu 9.10 to 10.04. Video in pygame for example is very unstable with ubuntu; almost stable with the last debian testing.

So we switched to Debian Squeeze (testing) a while ago. And so far we have a clean, small and fast OS, with some nice boot splash artwork. We can rapidly clone it to all kinds of hardware starting with a 8Gb clonezilla image.

On some older intel graphic cards we ran into trouble; BOD&#8217;s when switching to fullscreen in SDL apps, weird artefact&#8217;s when moving the mouse, couple of xServer crashes when playing fullscreen youtube video etc.

It only happended on: Intel Corporation 82945G/GZ Integrated Graphics Controller (rev 02) and Intel Corporation 82852/855GM Integrated Graphics Device (rev 02).

It took a while to discover where the problems originated from. On some forums if found descriptions of the same problem, and they seemed to be solved in the last releases. So i edited the sources.list file and did a _apt-get dist-upgrade_ to get in sync with the latest debian unstable. I removed the xorg.conf files to start fresh and had working GDM, with hardware acceleration. I tested it for some weeks now and didn&#8217;t have one single crash. We tested it with; SDL fullscreen switching with a couple of games, openGL cairo dock, playing youtube HD videos in fullscreen firefox for a couple of hours. The only thing which still crashes are videos in pygame (nothing new there&#8230;).

I just found a possible solution for our crashing video problem also, from the pygame site:

<pre>If your movies play slow or occasionally freeze, 
setting a limit to framerates seems to resolve the problem. 
See the documentation on Clock.tick(framerate) on how to limit framerates:
http://www.pygame.org/docs/ref/time.html#Clock.tick</pre>