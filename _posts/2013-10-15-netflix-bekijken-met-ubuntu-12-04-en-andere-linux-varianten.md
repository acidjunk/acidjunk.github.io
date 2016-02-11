---
id: 894
title: Netflix bekijken met Ubuntu 12.04 en andere Linux varianten
date: 2013-10-15T23:36:08+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=894
permalink: /2013/10/netflix-bekijken-met-ubuntu-12-04-en-andere-linux-varianten/
categories:
  - Computerz
---
Met de komst van Netflix naar Nederland heb ik uiteraard een abonnement afgesloten om het het eens op mijn gemakt te gaan testen. Mac OSX, Windows -> werkt prima gewoon vanuit de browser. Door de DRM protectie en het gebruik van Microsoft Silverlight is het op dit moment echter onmogelijk met de standaard Linux browsers netflix te kijken. Met een klein beetje werk installeer je echter PipeLight; die dan weer een gepatchte versie van wine gebruikt om Netflix in Firefox en Chrome mogelijk te maken. Op mijn oude Quad core gebruikt dit wel redelijk permanent 1 volledige core.

Klinkt lastig? het valt gelukkig mee; er zijn 3th party builds beschikbaar in Ubuntu repo&#8217;s. Quick install:

<pre>sudo apt-add-repository ppa:ehoover/compholio
sudo apt-add-repository ppa:mqchael/pipelight
sudo apt-get update
sudo apt-get install pipelight-multi
sudo pipelight-plugin --enable silverlight</pre>

Dit werkt op Ubuntu 13.10 Saucy Salamander, Ubuntu 13.04 Raring Ringtail, Ubuntu 12.10 Quantal Quetzal, Ubuntu 12.04 Precise Pangolin, Linux Mint 16 Petra, Linux Mint 15 Olivia, Linux Mint 14 Nadia, Linux Mint 13 Maya en Elementary OS 0.2 Luna. Fullscreen werkt bij mij alleen op de primary monitor. Verder werkt het super <img src="http://www.renedohmen.nl/blog/wp-includes/images/smilies/simple-smile.png" alt=":)" class="wp-smiley" style="height: 1em; max-height: 1em;" />

[<img class="alignnone size-medium wp-image-918" alt="Netflix in Chrome on Ubuntu 12.04" src="http://www.renedohmen.nl/blog/wp-content/uploads/2013/10/Screenshot-from-2013-10-16-020726-300x189.png" width="300" height="189" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2013/10/Screenshot-from-2013-10-16-020726-300x189.png 300w, http://www.renedohmen.nl/blog/wp-content/uploads/2013/10/Screenshot-from-2013-10-16-020726-1024x645.png 1024w" sizes="(max-width: 300px) 100vw, 300px" />](http://www.renedohmen.nl/blog/wp-content/uploads/2013/10/Screenshot-from-2013-10-16-020726.png)  [<img class="alignnone size-medium wp-image-921" alt="Fullscreen Netflix in Chrome on Linux" src="http://www.renedohmen.nl/blog/wp-content/uploads/2013/10/Screenshot-from-2013-10-16-023021-300x163.png" width="300" height="163" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2013/10/Screenshot-from-2013-10-16-023021-300x163.png 300w, http://www.renedohmen.nl/blog/wp-content/uploads/2013/10/Screenshot-from-2013-10-16-023021-1024x557.png 1024w" sizes="(max-width: 300px) 100vw, 300px" />](http://www.renedohmen.nl/blog/wp-content/uploads/2013/10/Screenshot-from-2013-10-16-023021.png)