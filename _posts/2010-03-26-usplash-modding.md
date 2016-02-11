---
id: 52
title: Usplash modding
date: 2010-03-26T21:51:45+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=52
permalink: /2010/03/usplash-modding/
categories:
  - Computerz
---
HOW-TO make custom usplash art

After only being able to find posts of people asking this question i decided to explore and find out how to do it. Great thanks to garry for his tuto at &#8211;http://ubuntusatanic.org/forum/comme&#8230;onID=21&page=1

So first things first, create an image you wont to use for usplash
  
try and keep the colours to a minimum

1.) Make the image 1024&#215;768.

2.) Flatten the image so it only has one layer.
  
&#8212; in GIMP do this by {Image&#8211;>flatten image}.

3.) Reduce the colours by doing
  
{Image&#8211;>Mode&#8211;>Indexed} Select &#8220;Generate optimum palette&#8221; and set the number of colours to 256.

4.) Play around with dithering to set optimum appearance, then save as a .png

5.) Repeat this for sizes &#8212; 800&#215;600, 1365&#215;768, 640&#215;480 & 640&#215;400

&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;section 2 &#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;

&#8211; Install some build utilities

1.)

Code:

sudo apt-get install cdbs debhelper dpkg-dev fakeroot devscripts autotools-dev

&#8211; Install the build dependencies for the usplash stuff

2.)

Code:

sudo apt-get build-dep usplash-theme-ubuntu

&#8211; Get the source code &#8211; I&#8217;d base it on the xubuntu usplash.

3.)

Code:

cd && apt-get source xubuntu-artwork-usplash

&#8211; Make sure you have permission to overwrite everything

4.)

Code:

user=$(whoami) ; sudo chmod -R 777 /home/$user/xubuntu-artwork-0.19*

&#8211; Build the package

5.)

Code:

user=$(whoami) ; cd /home/$user/xubuntu-artwork-0.19/ && dpkg-buildpackage -rfakeroot

Installation. The compilation process generates a .so file. Copy it
  
to /usr/lib/usplash. To install it, run

6.)

Code:

sudo update-alternatives &#8211;install /usr/lib/usplash/usplash-artwork.so usplash-artwork.so /usr/lib/usplash/usplash-theme-xubuntu.so 10

&#8211; Finally

7.)

Code:

sudo update-alternatives &#8211;config usplash-artwork.so && sudo update-initramfs -u

&#8211; Test it with

8.)

Code:

sudo usplash -c