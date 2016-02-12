---
id: 275
title: Some scripts to watch and record TV
date: 2011-08-18T01:04:00+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=275
permalink: /2011/08/some-scripts-to-watch-and-record-tv/
categories:
  - Computerz
---
With the new [N7 netwerktuner from anysee](http://www.anyseedirect.eu/en/Network-Tuners/View-all-products.html) you get an very flexible tv watching/streaming solution. It delivers it TV via the netwrok as an MPEG2 stream. You can watch television then for example with VLC or mplayer.

[<img class="alignnone size-medium wp-image-283" title="11 - 3" src="http://www.renedohmen.nl/blog/wp-content/uploads/2011/08/11-3-300x275.jpg" alt="" width="300" height="275" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2011/08/11-3-300x275.jpg 300w, http://www.renedohmen.nl/blog/wp-content/uploads/2011/08/11-3.jpg 480w" sizes="(max-width: 300px) 100vw, 300px" />](http://www.renedohmen.nl/blog/wp-content/uploads/2011/08/11-3.jpg)

Because I want to start watching and recording fast from my linux of mac boxes i wrote 2 handy shell scripts to launch a viewer or to start recording. I put them in /usr/local/bin and did a chmod +x

**Script 1
  
** _I called it: tv_

<pre>#!/bin/bash
killall mplayer
mplayer -nocache -ao sdl http://ip_number_of_n7:8080/chlist/$1</pre>

**Script 2
  
** _I called it record_

<pre>#!/bin/bash
mplayer -nocache -ao sdl http://ip_number_of_n7:8080/chlist/$1 -dumpstream -dumpfile ~/record.mpg</pre>

**
  
Usage:**

Of course you have to fill in the IP number of the N7 yourself. But after that it&#8217;s easy..

Now you can watch television by typing the following command in a console (without the $):

$ tv 0012

This starts mplayer and tunes to channel 12
  
or

$ record 0001
  
This records channel 1 into your home folder ->record.mpg
  
It&#8217;s even possible to open the dumpfile in mplayer while recording and watch it live. So record AND watching simultaneously <img src="http://www.renedohmen.nl/blog/wp-includes/images/smilies/simple-smile.png" alt=":)" class="wp-smiley" style="height: 1em; max-height: 1em;" />

I then added some items to my kde menu for the channels I watch most. I used the icons of the channels for it.
  
[<img class="alignnone size-medium wp-image-277" title="tv" src="http://www.renedohmen.nl/blog/wp-content/uploads/2011/08/tv-300x168.jpg" alt="" width="300" height="168" />](http://www.renedohmen.nl/blog/wp-content/uploads/2011/08/tv.jpg)[<img class="alignnone size-medium wp-image-280" title="snapshot2" src="http://www.renedohmen.nl/blog/wp-content/uploads/2011/08/snapshot2-300x168.jpg" alt="" width="300" height="168" />](http://www.renedohmen.nl/blog/wp-content/uploads/2011/08/snapshot2.jpg)

&nbsp;