---
id: 65
title: 'How do I verify how many CPU&#8217;s I have in the Terminal'
date: 2010-04-11T22:02:24+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=65
permalink: /2010/04/how-do-i-verify-how-many-cpus-i-have-in-the-terminal/
categories:
  - Computerz
---
When working with video encoders or single core / multi core licenses it&#8217;s handy to now how much cores a CPU has, with only a terminal available it&#8217;s not that hard <img src="http://www.renedohmen.nl/blog/wp-includes/images/smilies/simple-smile.png" alt=":-)" class="wp-smiley" style="height: 1em; max-height: 1em;" />
  
**Linux**
  
cat /proc/cpuinfo
  
**
  
OS X**
  
sysctl -n hw.ncpu