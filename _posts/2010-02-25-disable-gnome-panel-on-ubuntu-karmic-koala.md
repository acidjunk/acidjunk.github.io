---
id: 22
title: Disable Gnome-Panel on Ubuntu Karmic Koala
date: 2010-02-25T21:35:31+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=22
permalink: /2010/02/disable-gnome-panel-on-ubuntu-karmic-koala/
categories:
  - Computerz
---
Still customizing our new hardware for the braintrainer. Now I added Cairo Dock to have a really fancy menu for launching our apps. It was actually rather complicated to remove my last gnome panel, to make the most efficient use of Cairo Dock on Ubuntu 9.10 Karmic.

This is done by running gconf-editor (either from a run dialog or from CLI), and navigating to Desktop –> Gnome –> Session –> Required-Components. Now you will have three values in the panel on the right. Change the value of “Panel” from “gnome-panel” to “” (blank). Note that in order for this to work, you’ll need to have another panel application (e.g. AWN or CAIRO DOCK) running and in your startup programs folder.

I removed &#8216;panel&#8217; from the list, but still have the panel->gnome-panel key. Logging out and logging in again was all that&#8217;s needed. No more gnome-panel, just a nice and cool cairo dock.

However, if you ever had the option &#8220;automatically remember&#8230;&#8221; in gnome-session-properties aka &#8216;Startup Applications&#8217; switched on you may have an entry referring to gnome-panel in ~/.config/gnome-session/saved-session. Keep this option off for now, clean out the saved-session directory and try again.Just a quick one. Took me bloody ages to find this out, so hope this has made things easier for some of you!