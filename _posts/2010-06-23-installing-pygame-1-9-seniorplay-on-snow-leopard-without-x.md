---
id: 59
title: Installing pygame 1.9 / seniorplay on snow leopard, without X
date: 2010-06-23T21:59:15+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=59
permalink: /2010/06/installing-pygame-1-9-seniorplay-on-snow-leopard-without-x/
categories:
  - Computerz
---
Getting pygame going on MAC OSX is not for the fainthearted; so be warned&#8230;.

It will also take a lot of time
  
One my first attempt I tried to use the OSX tools as much as possible. This didn&#8217;t work after trying all possible combi&#8217;s of SDL as OSX framework and SDL as unix lib I tried the mac ports approach.

This is what I did to get it running without having to use an Xserver window

1) Installed Mac Ports: <a href="http://www.macports.org/" target="_blank">http://www.macports.org/</a>

2) In terminal:
  
sudo port selfupdate
  
sudo port install py26-game
  
sudo port install py26-sqlalchemy

Now wait a very long time: almost 2 hours to compile all dependencies (if you didn&#8217;t use mac port before)

3) get seniorplay:
  
svn co [https://schoolsplay.svn.sourceforge.net/svnroot/schoolsplay/branches/sen&#8230;](https://schoolsplay.svn.sourceforge.net/svnroot/schoolsplay/branches/seniorplay "https://schoolsplay.svn.sourceforge.net/svnroot/schoolsplay/branches/seniorplay")

4) in SPConstants.py I changed: noGTK to true; I don&#8217;t need GTK now <img src="http://www.renedohmen.nl/blog/wp-includes/images/smilies/simple-smile.png" alt=":-)" class="wp-smiley" style="height: 1em; max-height: 1em;" />

5) started seniorplay with the mac ports python in /opt/local/bin/python2.6

/opt/local/bin/python2.6 seniorplay\_sp\_local.py -t seniorplay