---
id: 1130
title: Install python PIL or Pillow on Ubuntu 14.04 64 bit
date: 2015-05-19T09:37:36+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=1130
permalink: /2015/05/install-python-pil-or-pillow-on-ubuntu-14-04-64-bit/
categories:
  - Computerz
---
Every now and then I have to install Python PIL or Pillow on an Ubuntu server. I mostly end up with problems like no jpeg support or no compressed png support. After some googling you will find all kinds of info consisting of creating symlinks on some locations so it will work on 64 bit Ubuntu etc.

As it turns the install is quite easy, without the need to manually symlink stuff. First install deps:

<pre>sudo apt-get install libtiff5-dev libjpeg8-dev zlib1g-dev libfreetype6-dev liblcms2-dev libwebp-dev tcl8.6-dev tk8.6-dev python-tk
</pre>

Then you should be able to installing python imaging stuff with:

<pre>sudo pip install pillow
</pre>

If you already installed pillow before you installed all the needed deps; changes are that you don&#8217;t have jpeg support; you can then force a reinstall with:

<pre>sudo pip install -I Pillow
</pre>
