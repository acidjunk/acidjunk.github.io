---
id: 5
title: 'Debian : howto use pinning'
date: 2010-12-11T21:19:15+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=5
permalink: /2010/12/debian-howto-use-pinning/
categories:
  - Computerz
---
In a recent attempt to use the latest intel driver on my debian squeeze testing box to avoid a problem which is most likely described here:

[https://bugs.freedesktop.org//show_bug.cgi?id=31367](https://bugs.freedesktop.org//show_bug.cgi?id=31367 "https://bugs.freedesktop.org//show_bug.cgi?id=31367")

So I needed only Xorg from the unstable repo; this is what I did:

The first step is to set up your <tt>/etc/apt/sources.list</tt> to include your typical Stable, plus the Testing/Unstable sources that you want.

<pre>#Testing
deb <a title="http://ftp.nl.debian.org/debian" href="http://ftp.nl.debian.org/debian">http://ftp.nl.debian.org/debian</a> testing main contrib non-free
deb-src <a title="http://ftp.nl.debian.org/debian" href="http://ftp.nl.debian.org/debian">http://ftp.nl.debian.org/debian</a> testing main contrib non-free

deb <a title="http://security.debian.org/" href="http://security.debian.org/">http://security.debian.org/</a> testing/updates main contrib non-free
deb-src <a title="http://security.debian.org/" href="http://security.debian.org/">http://security.debian.org/</a> testing/updates main contrib non-free

#Unstable
deb <a title="http://ftp.nl.debian.org/debian" href="http://ftp.nl.debian.org/debian">http://ftp.nl.debian.org/debian</a> unstable main non-free contrib</pre>

Then edited /etc/apt/preferences:

 <span style="font-size: 15px; color: #222222; font-family: 'Courier 10 Pitch', Courier, monospace; line-height: 21px; white-space: pre;"></span>

<pre><pre>Package: *</pre>


<p>
  Pin: release a=testing  Pin-Priority: 650  Package: * Pin: release a=unstable Pin-Priority: 600<br />
  Then I learned that debian also has an experimental branche, and the package i wanted existed in experimental only. When I started buidling on thes debian machine i used squeeze, so my apt file contained references to squeeze. From reading the apt en the debian docs I found that squeeze == testing, sid == unstable. So i had to rename all references of &#8220;squeeze&#8221; in the /etc/apt/sources.list to &#8220;testing&#8221;<br />
  Ended up with this /etc/apt/sources.list:
</p>


<pre># ACID: apt file, pinning preference can be found in /etc/apt/preferences

#Testing
deb <a title="http://ftp.nl.debian.org/debian/" href="http://ftp.nl.debian.org/debian/">http://ftp.nl.debian.org/debian/</a> testing main contrib non-free
deb-src <a title="http://ftp.nl.debian.org/debian/" href="http://ftp.nl.debian.org/debian/">http://ftp.nl.debian.org/debian/</a> testing main contrib non-free

deb <a title="http://security.debian.org/" href="http://security.debian.org/">http://security.debian.org/</a> testing/updates main contrib non-free
deb-src <a title="http://security.debian.org/" href="http://security.debian.org/">http://security.debian.org/</a> testing/updates main contrib non-free

#Unstable
deb <a title="http://ftp.nl.debian.org/debian/" href="http://ftp.nl.debian.org/debian/">http://ftp.nl.debian.org/debian/</a> unstable main contrib non-free

#Experimental :
#ACID: Needed for xorg 2.14: 25-01-2011
deb <a title="http://ftp.nl.debian.org/debian/" href="http://ftp.nl.debian.org/debian/">http://ftp.nl.debian.org/debian/</a> experimental main contrib non-free</pre>


<p>
  /etc/apt/preferences:
</p>


<pre>Package: *
Pin: release a=testing
Priority: 650

Package: *
Pin: release a=unstable
Priority: 600

Package: *
Pin: release a=experimental
Priority: 500</pre>