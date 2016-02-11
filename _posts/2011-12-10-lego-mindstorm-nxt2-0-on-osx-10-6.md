---
id: 410
title: Lego Mindstorm NXT2.0 on OSX 10.6
date: 2011-12-10T21:20:17+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=410
permalink: /2011/12/lego-mindstorm-nxt2-0-on-osx-10-6/
categories:
  - Computerz
---
Just as a quick reminder for myself. The Mindstorms NXT 2.0 doesn&#8217;t work out of the box on OS X 10.6. But with a quick hack it is possible to run it; this is how I did it:
  
To install LEGO MINDSTORMS NXT 2.0 on Mac OS 10.6 (Snow Leopard)
  
1. Copy all files from the MINDSTORMS CD to a folder on your desktop.
  
2. Open that folder and look under &#8220;Parts&#8221;.
  
3. Locate MindstormsUnivEdu.pkg or MindstormsUnivRet.pkg.
  
4. Right-click (control-click) and choose &#8220;Show Package Contents&#8221;.
  
5. Navigate into the Contents/Resources directory and delete the &#8220;preflight&#8221; file.
  
6. Close this package and run the meta-package (LEGOMindstormsEngRet.mpkg from the root of the copied installer folder) to install MINDSTORMS NXT