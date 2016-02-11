---
id: 11
title: First attempt to get Wiimotes working with Ubuntu Lucid
date: 2010-08-23T21:27:01+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=11
permalink: /2010/08/first-attempt-to-get-wiimotes-working-with-ubuntu-lucid/
categories:
  - Computerz
---
On Ubuntu 10.10 you install the software with:

sudo apt-get install libcwiid1 lswm wmgui wminput

You can test as an normal user if it works with wmgui; It&#8217;s capable of finding the wiimote and showing current status, like which button is pressed etc.

After you confirmed it&#8217;s working; run:

lswm
  
Put Wiimotes in discoverable mode now (press 1+2)&#8230;
  
00:27:09:78:5F:F4

Use the address you found to get it working as a mouse:

sudo wminput 00:27:09:78:5F:F4