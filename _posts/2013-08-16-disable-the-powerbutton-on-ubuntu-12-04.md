---
id: 853
title: Disable the powerbutton on Ubuntu 12.04
date: 2013-08-16T21:23:19+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=853
permalink: /2013/08/disable-the-powerbutton-on-ubuntu-12-04/
categories:
  - Computerz
---
In Debian or Ubuntu minimal disabling the power button is quite easy. Just remove the contents of /etc/acpi/powerbtn.sh. That doesn&#8217;t work in Ubuntu with Gnome/Unity. The shutdown procedure is quite complex; acpid, gnome-power-manager, polkit all play some kind of role in it. After a lot of reading I stumbled upon a post in the ubuntu forums where someone kindly analysed the Ubuntu shutdown button proces: http://ubuntuforums.org/showthread.php?t=2020630

What I did to disable the power button completely, was eventually very easy:

<pre>gsettings set org.gnome.settings-daemon.plugins.power button-power nothing</pre>