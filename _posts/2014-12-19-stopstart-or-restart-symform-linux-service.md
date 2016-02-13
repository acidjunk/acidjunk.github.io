---
id: 1076
title: Stop/Start or Restart Symform linux service
date: 2014-12-19T14:04:37+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=1076
permalink: /2014/12/stopstart-or-restart-symform-linux-service/
categories:
  - Computerz
header-img: "img/post-bg-06.jpg"
---
The Symform daemon is not a default Linux service so it took me a while to figure out how to start and stop it.

Linux and NAS Devices:
  
Run command &#8220;/opt/symform/SymformNode.sh restart&#8221; from the ssh terminal window connected to your device to restart all services except (Updater service) on your device. You can also use the following commands:

To start:

<pre>/opt/symform/SymformNode.sh start sync
/opt/symform/SymformNode.sh start contrib
/opt/symform/SymformNode.sh start web
</pre>

To stop:

<pre>/opt/symform/SymformNode.sh stop sync
/opt/symform/SymformNode.sh stop contrib
/opt/symform/SymformNode.sh stop web
</pre>

To start updater service:

<pre>sh /opt/symform/scripts/SymformUpdater.sh
</pre>