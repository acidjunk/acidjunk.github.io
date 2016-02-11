---
id: 857
title: Configure multicast network traffic to go over a specific network interface on linux
date: 2013-08-24T23:47:20+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=857
permalink: /2013/08/configure-multicast-network-traffic-to-go-over-a-specific-network-interface/
categories:
  - Computerz
---
I&#8217;m using eth2 to connect to a seperate LAN with only some multicast video streams on it. On my linux comp I have to force listening for multicast to eth2; here is how to do it.

<pre>route add -net 224.0.0.0 netmask 240.0.0.0 dev eth2
</pre>