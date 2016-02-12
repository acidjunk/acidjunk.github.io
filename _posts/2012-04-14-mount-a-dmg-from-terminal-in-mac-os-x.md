---
id: 543
title: Mount a .dmg from Terminal in Mac OS X
date: 2012-04-14T18:25:56+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=543
permalink: /2012/04/mount-a-dmg-from-terminal-in-mac-os-x/
categories:
  - Computerz
---
If you are a Terminal user you might want to mount .dmg files from commandline.

Basically thats pretty easy:

**Attaching a DMG
  
** 

<pre>hdiutil attach /path/to/myDMGname.dmg
</pre>

If you want to see how it&#8217;s mounted: do a

<pre>mount
</pre>

Unmounting:

<pre>umount /Volumes/DiskImageName
</pre>

Thats it.