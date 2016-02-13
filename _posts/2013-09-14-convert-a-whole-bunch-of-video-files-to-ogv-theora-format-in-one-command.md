---
id: 886
title: Convert a whole bunch of video files to .ogv theora format in one command
date: 2013-09-14T03:39:10+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=886
permalink: /2013/09/convert-a-whole-bunch-of-video-files-to-ogv-theora-format-in-one-command/
categories:
  - Computerz
header-img: "img/post-bg-01.jpg"
---
Just a short post as a reminder for myself. We do use a lot of ogv&#8217;s in our Narrow casting shows.
  
When you use ffmpeg2theora with a Linux or OSX kinda system you can convert a whole folder with video&#8217;s like this:

<pre>cd videofiles
for file in *.avi; do ffmpeg2theora "$file"; done
</pre>

Or with some more options, like video quality 9 (default 6, max 10), optimize files and put it some tag info:

<pre>for file in *.mov; do ffmpeg2theora --videoquality 9 --optimize --organization Formatics "$file"; done</pre>

Output:

<pre>Input #0, mov,mp4,m4a,3gp,3g2,mj2, from 'BTP mannetje en BTP3D model.mov':
  Metadata:
    major_brand     : qt  
    minor_version   : 537199360
    compatible_brands: qt  
    creation_time   : 2013-09-14 03:30:40
  Duration: 00:00:46.32, start: 0.000000, bitrate: 14213 kb/s
    Stream #0:0(eng): Video: mpeg4 (Advanced Simple Profile) (mp4v / 0x7634706D), yuv420p, 1920x1080 [SAR 1:1 DAR 16:9], 14211 kb/s, 25 fps, 25 tbr, 600 tbn, 1k tbc
    Metadata:
      creation_time   : 2013-09-14 03:30:40
      handler_name    : Apple Alias Data Handler
  Pixel Aspect Ratio: 1.00/1   Frame Aspect Ratio: 1.78/1

  0:00:45.79 audio: 0kbps video: 1743kbps, ET: 00:00:01, est. size: 9.6 MB    
  0:00:46.32 audio: 0kbps video: 1731kbps, time elapsed: 00:02:35
</pre>