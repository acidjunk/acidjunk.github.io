---
id: 28
title: Full screen plugin for firefox, linux
date: 2010-02-25T21:38:45+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=28
permalink: /2010/02/full-screen-plugin-for-firefox-linux/
categories:
  - Computerz
---
For one of our KiosK appz we needed a full screen plugin. The idea is to make a icon on the desktop (or in our cairo dock) starting a browser, loading the webpage and do this in fullscreen mode.

I found a couple of pages which do almost the same thing, like: [this one](http://ramblings.narrabilis.com/wp/firefox-fullscreen-kiosk-machine/)

The solution I used is based on a mix of extensions: first install the Full Fullscreen extension, this gets rid of the toolbars and statusbar while in fullscreen modus. I used version 3.3 on Ubuntu Karmic, found [here](https://addons.mozilla.org/nl/firefox/addon/1568)

Next problem: the command line option -fullscreen doesnt work on ubuntu.
  
At last I solved it with this very nice plugin: [R-Kiosk](https://addons.mozilla.org/en-US/firefox/addon/1659) version 0.7.4