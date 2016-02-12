---
id: 445
title: 'Using PS3 mediaserver to stream video&#8217;s to iPhone/iPad'
date: 2012-01-26T01:50:50+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=445
permalink: /2012/01/using-ps3-media-server-to-stream-videos-to-iphoneipad/
categories:
  - Computerz
---
The last [Playstation media server](https://code.google.com/p/ps3mediaserver/) has excellent support for streaming (transcoded) video straight to the iPad or Iphone. Because it uses upnp it can also stream to boxee, xbmc, VLC, Xbox 360 and of course the Play station 3. I used a commercial app, airplayer, on a iPhone 4 and a 3GS to test it and was very happy to find out that it can also open live streams from my network TV tuner, transcode it to mp4 and serve it on the fly to a iPhone 3GS.

Install PS3 Media Server: <https://code.google.com/p/ps3mediaserver/downloads/list>

[<img title="tv1" src="http://www.renedohmen.nl/blog/wp-content/uploads/2012/01/tv1-300x291.png" alt="" width="300" height="291" />](http://www.renedohmen.nl/blog/wp-content/uploads/2012/01/tv1.png)

I used PS3 Media Server 1.50.0 on Ubuntu 12.04. With the default settings all streams and conversion are done by VLC. I don&#8217;t know if you need to install VLC, mplayer and mencoder yourself but as a media geek I have them installed anyway. Then I added some shares with a couple of test videos in it. With most ,cheap or free, iPhone apps that can use a upnp/dnla mediaserver I was able to playback some .mp4 files (already in correct iPhone format), but it didn&#8217;t start transcoding for divx or xvid movies.

[<img class="alignnone size-medium wp-image-448" title="srces" src="http://www.renedohmen.nl/blog/wp-content/uploads/2012/01/srces1-300x291.png" alt="" width="300" height="291" />](http://www.renedohmen.nl/blog/wp-content/uploads/2012/01/srces1.png)

It seems that PS3 Mediaserver uses some HTTP User Agent detection mechanisme and tries to load the best transcoding profiles based on the expected video render platform. When  looked in the renderers folder (in the PS3 Mediaserver source) I discovered a profile with that name AirPlayer.conf. So I bought Airplayer in the app store and it discovered the media server in my network. Video playback works OK now for the files on disk, of course you need to have a decent computer for transcoding 720p or 1080p material on the fly to a format that the iPhone can play.

> **Next step: restream a live video stream to the iPhone.**

I have a N7 Network TV tuner that plays mpeg2 TS streams, Unfortunately that&#8217;s not playable with any apps that I know about in the app store.  So after some reading in the docs and config files I added my N7 streams to WEB.conf and copied the file to ~/.config/PMS/WEB.conf and restarted the media server.

My WEB.conf:

<pre># video feeds
#All in one folder
videostream.Web,TV=Nederland 1,http://tv:8080/chlist/0001,http://www.anyseedirect.eu/images/nederland_1.png
videostream.Web,TV=Nederland 2,http://tv:8080/chlist/0002,http://www.anyseedirect.eu/images/nederland_2.png
videostream.Web,TV=Nederland 3,http://tv:8080/chlist/0003,http://www.anyseedirect.eu/images/nederland_3.png
videostream.Web,TV=Comedy central,http://tv:8080/chlist/0014,http://www.anyseedirect.eu/images/comedy_central_kind.png
videostream.Web,TV=Discovery HD Showcase,http://tv:8080/chlist/0062,http://www.anyseedirect.eu/images/http://www.anyseedirect.eu/images/discovery_hd_showca.png

# video feeds
#All in seperate folder
videostream.N7,Nederland 1=Nederland 1,http://tv:8080/chlist/0001,http://www.anyseedirect.eu/images/nederland_1.png
videostream.N7,Nederland 2=Nederland 2,http://tv:8080/chlist/0002,http://www.anyseedirect.eu/images/nederland_2.png
videostream.N7,Nederland 3=Nederland 3,http://tv:8080/chlist/0003,http://www.anyseedirect.eu/images/nederland_3.png
videostream.N7,Comedy Central=Comedy central,http://tv:8080/chlist/0014,http://www.anyseedirect.eu/images/comedy_central_kind.png
videostream.N7,Discovery HD=Discovery HD Showcase,http://tv:8080/chlist/0062,http://www.anyseedirect.eu/images/http://www.anyseedirect.eu/images/discovery_hd_showca.png</pre>

the &#8220;http://tv&#8221; URL&#8217;s points to the N7 network tuner. (I like names, so yes I called it tv)

With the above setup I got some problems with the first part of the conf file: all TV channels in one folder (it looks like PMS is trying to make thumbnails or prefetches some stuff from the next channel, and yes I disabled thumbnails in the PMS settings). The last lines in the conf file are useable: it makes seperate folders for each channel.

Startup times are about 4 seconds for a channel switch for a channel with SD content.

**Photoos running Airplayer on iPhone:**
  
[<img class="alignnone size-medium wp-image-450" title="IMG_20120126_020104" src="http://www.renedohmen.nl/blog/wp-content/uploads/2012/01/IMG_20120126_020104-300x225.jpg" alt="" width="300" height="225" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2012/01/IMG_20120126_020104-300x225.jpg 300w, http://www.renedohmen.nl/blog/wp-content/uploads/2012/01/IMG_20120126_020104-1024x768.jpg 1024w" sizes="(max-width: 300px) 100vw, 300px" />](http://www.renedohmen.nl/blog/wp-content/uploads/2012/01/IMG_20120126_020104.jpg)  [<img class="alignnone size-medium wp-image-452" title="IMG_20120126_022845" src="http://www.renedohmen.nl/blog/wp-content/uploads/2012/01/IMG_20120126_022845-300x225.jpg" alt="" width="300" height="225" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2012/01/IMG_20120126_022845-300x225.jpg 300w, http://www.renedohmen.nl/blog/wp-content/uploads/2012/01/IMG_20120126_022845-1024x768.jpg 1024w" sizes="(max-width: 300px) 100vw, 300px" />](http://www.renedohmen.nl/blog/wp-content/uploads/2012/01/IMG_20120126_022845.jpg)

**Photoos running UPnPlay on Android (Nexus):**

[<img class="alignnone size-medium wp-image-458" title="foto (2)" src="http://www.renedohmen.nl/blog/wp-content/uploads/2012/01/foto-2-300x223.jpg" alt="" width="300" height="223" />](http://www.renedohmen.nl/blog/wp-content/uploads/2012/01/foto-2.jpg)&nbsp;&nbsp;[<img class="alignnone size-medium wp-image-459" title="foto (1)" src="http://www.renedohmen.nl/blog/wp-content/uploads/2012/01/foto-1-300x223.jpg" alt="" width="300" height="223" />](http://www.renedohmen.nl/blog/wp-content/uploads/2012/01/foto-1.jpg)