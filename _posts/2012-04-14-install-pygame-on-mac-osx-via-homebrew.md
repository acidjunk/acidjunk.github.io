---
id: 506
title: Install pygame on Mac OSX via homebrew
date: 2012-04-14T18:49:40+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=506
permalink: /2012/04/install-pygame-on-mac-osx-via-homebrew/
categories:
  - Computerz
---
The new and easy way is just use the package from pygame.org: as we speak ->

http://www.pygame.org/ftp/pygame-1.9.2pre-py2.7-macosx10.7.mpkg.zip

&nbsp;

If you want to build it yourself this are the steps on a virgin OSX 10.7 system:
  
_you &#8216;ll need Xcode 4.2_

Install mercurial from the .dmg from http://mercurial.selenic.com/ Or install mercurial via brew:

<pre>brew install mercurial</pre>

How to install to the brew supplied python.

<pre>brew install python
brew install sdl sdl_image sdl_mixer sdl_ttf smpeg portmidi
brew instal smpeg --HEAD
/usr/local/share/python/easy_install pip
/usr/local/share/python/pip install hg+http://bitbucket.org/pygame/pygame</pre>

With the brew installed python (2.7.3 as we speak) you can also install py2app. I had some problems with py2app 0.6.4 and reported it to the bugtracker, so I installed it with

<pre>/usr/local/share/python/easy_install py2app==0.6.3</pre>

<pre></pre>

<pre><a href="http://www.renedohmen.nl/blog/wp-content/uploads/2012/04/Screen-Shot-2012-04-14-at-7.56.30-PM.png"><img class="alignnone size-medium wp-image-550" title="Pygame on OSX mines" src="http://www.renedohmen.nl/blog/wp-content/uploads/2012/04/Screen-Shot-2012-04-14-at-7.56.30-PM-300x199.png" alt="" width="300" height="199" /></a></pre>