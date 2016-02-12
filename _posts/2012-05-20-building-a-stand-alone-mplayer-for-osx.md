---
id: 416
title: Building a stand alone Mplayer for OSX
date: 2012-05-20T00:50:28+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=416
permalink: /2012/05/building-a-stand-alone-mplayer-for-osx/
categories:
  - Computerz
---
I needed a recent mplayer for OS X; the current homebrew version has a memory leak when playing MPEG2 TS SD channels. This is how I compiled the svn HEAD trunk of mplayer for OSX 10.7 and the steps needed to get an app that you can deploy on other macs. I used a virgin OSX with only xCode installed running in VMWare Fusion to eliminate all sort of problems that could arise with already installed libs.

<pre>#Override default tools with Cellar ones if available
#This makes sure homebrew stuff is used
export PATH=/usr/local/bin:$PATH
#Enable extra room in my own libs
export LDFLAGS="-headerpad_max_install_names"</pre>

I cheated a little bit and didn&#8217;t install all deps by hand. So I installed homebrew and installed the SVN version of mplayer with:

<pre>$ brew install --HEAD mplayer</pre>

Maybe I had some luck; but this worked beautifully and left me with the latest mplayer (1 March 2012). It also builded all the necessary deps. From here on there are 2 options; use the compiled homebrew version or build your own version with a fresh mplayer checkout. I like to have some control about the build proces so I downloaded the mplayer from SVN. With the previous steps it&#8217;s now very straight forward to get a working mplayer;

<pre>$ svn checkout svn://svn.mplayerhq.hu/mplayer/trunk mplayer
$ cd mplayer
$ ./configure --disable-x11 --disable-gl --disable-mencoder --enable-macosx-bundle --enable-macosx-finder --target=x86_64-Darwin [--disable-fontconfig]
$ make</pre>

Then I used the instructions and scripts provided by Hermi from http://tracker.mplayerosx.ch/boards/1/topics/1444
  
to change the dylibs to work from inside the mplayer lib/
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;

<pre>mkdir mplayer_dist
cp mplayer mplayer_dist/
cd mplayer_dist
mkdir lib
cp /usr/local/lib/libfribidi.0.dylib lib/
cp /usr/local/lib/libass.4.dylib lib/
cp /usr/local/lib/libtheora.0.dylib lib/
cp /usr/local/lib/libogg.0.dylib lib/
cp /usr/local/lib/libbs2b.0.0.0.dylib lib/
cp /usr/local/lib/libSDL-1.2.0.dylib lib/
cp /usr/local/lib/libfaac.0.0.0.dylib lib/
cp /usr/local/lib/libmp3lame.0.0.0.dylib lib/</pre>

install\_name\_tool -change /usr/local/lib/libfribidi.0.dylib @executable_path/lib/libfribidi.0.dylib mplayer
  
install\_name\_tool -change /usr/local/lib/libass.4.dylib @executable_path/lib/libass.4.dylib mplayer
  
install\_name\_tool -change /usr/local/lib/libtheora.0.dylib @executable_path/lib/libtheora.0.dylib mplayer
  
install\_name\_tool -change /usr/local/lib/libogg.0.dylib @executable_path/lib/libogg.0.dylib mplayer
  
install\_name\_tool -change /usr/local/lib/libbs2b.0.0.0.dylib @executable_path/lib/libbs2b.0.0.0.dylib mplayer
  
install\_name\_tool -change /usr/local/lib/libSDL-1.2.0.dylib @executable_path/lib/libSDL-1.2.0.dylib mplayer
  
install\_name\_tool -change /usr/local/lib/libfaac.0.0.0.dylib @executable_path/lib/libfaac.0.0.0.dylib mplayer

#LIBS
  
sudo install\_name\_tool -change /usr/local/lib/libfribidi.0.dylib @executable_path/lib/libfribidi.0.dylib libass.4.dylib
  
sudo install\_name\_tool -change /usr/local/lib/libogg.0.dylib @executable_path/lib/libogg.0.dylib libtheora.0.dylib