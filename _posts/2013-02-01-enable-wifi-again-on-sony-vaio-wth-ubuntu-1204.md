---
id: 751
title: Enable WIFI again on Sony Vaio with Ubuntu 12.04
date: 2013-02-01T20:56:23+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=751
permalink: /2013/02/enable-wifi-again-on-sony-vaio-wth-ubuntu-1204/
categories:
  - Computerz
---
After installing 12.04 on my vaio laptop everything was OK. But when I disabled the WIFI from the Ubuntu menu the wifi showed an message that it was turned off with the hardware switch.

[<img class="alignleft" alt="Schermafdruk van 2013-02-01 21:45:24" src="http://www.renedohmen.nl/blog/wp-content/uploads/2013/02/Schermafdruk-van-2013-02-01-214524.png" width="253" height="234" />](http://www.renedohmen.nl/blog/wp-content/uploads/2013/02/Schermafdruk-van-2013-02-01-214524.png)

[<img class="alignnone  wp-image-754" alt="Schermafdruk van 2013-02-01 21:40:57" src="http://www.renedohmen.nl/blog/wp-content/uploads/2013/02/Schermafdruk-van-2013-02-01-214057.png" width="291" height="336" style="padding-left:10px;" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2013/02/Schermafdruk-van-2013-02-01-214057-260x300.png 260w, http://www.renedohmen.nl/blog/wp-content/uploads/2013/02/Schermafdruk-van-2013-02-01-214057.png 364w" sizes="(max-width: 291px) 100vw, 291px" />](http://www.renedohmen.nl/blog/wp-content/uploads/2013/02/Schermafdruk-van-2013-02-01-214057.png)

&nbsp;

**The weird thing:** there is no hardware switch to turn off WIFI, neither does the BIOS have options for disabling the WIFI.

Doing a &#8220;rfkill list all&#8221;:

<pre>0: sony-wifi: Wireless LAN
Soft blocked: yes
Hard blocked: no
1: sony-bluetooth: Bluetooth
Soft blocked: no
Hard blocked: no
2: phy0: Wireless LAN
Soft blocked: yes
Hard blocked: yes
3: hci0: Bluetooth
Soft blocked: no
Hard blocked: no</pre>

After some searching I found a solution: 

<pre>rfkill unblock wifi
</pre>

Now your WIFI should work again.