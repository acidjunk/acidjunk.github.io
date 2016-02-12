---
id: 15
title: Cool stuff with Pyglet
date: 2010-09-27T21:30:00+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=15
permalink: /2010/09/cool-stuff-with-pyglet/
categories:
  - Computerz
---
﻿﻿

I installed pyglet with the installer for the mac to check out video support and some opengl performance tests.

After some struggling with 64 bit python on the mac i got the examples running by setting python to 32bit:

<pre>export VERSIONER_PYTHON_PREFER_32_BIT=yes</pre>

When you don&#8217;t do it you&#8217;ll get this error;

<pre>OSError: dlopen(/System/Library/Frameworks/QuickTime.framework/QuickTime, 6): no suitable image found.  Did find:
	/System/Library/Frameworks/QuickTime.framework/QuickTime: no matching architecture in universal wrapper
	/System/Library/Frameworks/QuickTime.framework/QuickTime: no matching architecture in universal wrapper</pre>

The examples are really cool and the python video player supports divx, mkv and h264; Performance is very good; only tested it on my imac so far