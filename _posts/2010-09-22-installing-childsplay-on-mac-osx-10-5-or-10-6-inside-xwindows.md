---
id: 13
title: Installing childsplay on MAC OSX 10.5 or 10.6 inside Xwindows
date: 2010-09-22T21:28:59+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=13
permalink: /2010/09/installing-childsplay-on-mac-osx-10-5-or-10-6-inside-xwindows/
categories:
  - Computerz
---
﻿﻿This is what I did to get a recent childsplay from SVN running on the mac.

1) Install xCode

2) Installed Mac Ports: <a href="http://www.macports.org/" target="_blank">http://www.macports.org/</a>

2) Install the dependencies with the follwing console commands; be warned it takes a very long time&#8230;

<pre>sudo port  selfupdate
sudo port install py26-game
sudo port install py26-sqlalchemy
sudo port install py26-gtk</pre>

Optionally install python_select and activate python2.6 as default with

<pre>sudo python_select python26</pre>