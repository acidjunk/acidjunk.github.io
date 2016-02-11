---
id: 700
title: Zip only certain files and keep the directory structure intact
date: 2013-01-10T20:55:13+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=700
permalink: /2013/01/tar-only-certain-files-and-keep-the-directory-structure-intact/
categories:
  - Computerz
---
I needed a backup of only the C# sources in a big folder with Unity3d projects on a mac. It took me a while to find the correct syntax. Instead of copying; I let zip do the hard work; and then just unzip it somewhere else.

One folder above your UnityProjects folder:

<pre>find . -name "*.cs" -print| zip source -@</pre>