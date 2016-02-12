---
id: 71
title: Converting iphone 4 movies to xvid with mplayer / mencoder
date: 2010-11-22T22:06:06+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=71
permalink: /2010/11/converting-iphone-4-movies-to-xvid-with-mplayer-mencoder/
categories:
  - Computerz
---
The iPhone 4 is capable of recording movies in 1280 x720p. When using the default .mov format they can get quite big.

When exporting with a default mencoder command the movies are upside down and 5 times to wide and up/side down.

After a lot of fiddling around with different mencoder paremeters i found a nice way to convert to xvid, while forcing the aspect and rotating the moviles also in a single pass; with good quality and low filesize:

<pre>mencoder IPHONE4.MOV -ovc xvid -aspect 16:9 -vf mirror,flip -oac mp3lame -xvidencopts bitrate=687 -o test.avi</pre>

I used mencoder on Ubuntu 10.04 for it; Debian has a crappy mecoder with no lame support by default..

It depends on how you recorder your movie if you have to flip or rotate&#8230;.