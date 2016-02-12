---
id: 333
title: Spotify voor linux !
date: 2011-11-01T23:48:41+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=333
permalink: /2011/11/spotify-voor-linux/
categories:
  - Computerz
  - Muziek
---
Er was eerst een niet werkende manier om via wine onder ubuntu de spotify client te gebruiken. Dat leverde na veel gepiel een crashende player op.

Nu is er gelukkig een beta preview:
  
http://www.spotify.com/nl/download/previews/

Quick install:
  
1. Add this line to your list of repositories in /etc/apt/sources.list

<pre>deb http://repository.spotify.com stable non-free</pre>

2. Add public key 

<pre>sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 4E9CFF4E</pre>

\# 3. Run apt-get update

<pre>sudo apt-get update</pre>

\# 4. Install spotify!

<pre>sudo apt-get install spotify-client-qt</pre>