---
id: 405
title: Enabling front speakers of MSI AE2050 on Ubuntu 11.10
date: 2011-11-11T20:11:09+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=405
permalink: /2011/11/enabling-front-speakers-of-msi-ae2050-on-ubuntu-11-10/
categories:
  - Computerz
---
With kernel 3.0 sound via speaker output stopped working on the all-in-one [MSI AE2050](http://www.msi.com/product/aio/Wind-Top-AE2050.html).

Output with headphone works OK, but the buildin speakers are never used.
  
When using and an 2.36 or above kernel it worked OK, with one small bug -> a connected headphone would leave the speakers on. 

I tried a couple of approaches to keep sound and touch, at last the solution was simple: install the latest ALSA release based on the nightly build as provided by the Ubuntu audio team.

It&#8217;s called DKMS Alsa driver you can download a .deb from [here](https://launchpad.net/~ubuntu-audio-dev/+archive/alsa-daily/+packages) or add it as ppa, instructions [here](https://launchpad.net/~ubuntu-audio-dev/+archive/alsa-daily/+index#).

One, small problem, the speakers are muted when the volume drops below 70%, and I&#8217;ll still need to test this on the BTP os.