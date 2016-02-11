---
id: 779
title: Recording Studio Brussel at Friday from crontab with python and mplayer
date: 2013-03-02T03:44:00+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=779
permalink: /2013/03/studio-brussel-at-friday/
categories:
  - Computerz
  - Muziek
---
When I do my part of the code I like doing it on Friday night with some nice uptempo music. That&#8217;s if i&#8217;m not in a bar drinking beer or playing my sax.

So I wrote a little script to record the Studio Brussel stream in the evening when they broadcast some very nice mixes music. Progressive drumnbass, dub step, minimalistic, techno acid combinations, very very nice for long marathon coding sessions, at times coffee doesnt&#8217; work anymore <img src="http://www.renedohmen.nl/blog/wp-includes/images/smilies/simple-smile.png" alt=":)" class="wp-smiley" style="height: 1em; max-height: 1em;" />

Basically the command is:

<pre>mplayer http://mp3.streampower.be/stubru-high -cache 4096 --dumpstream
mv http://mp3.streampower.be/stubru-high stubru_WEEKNUMBER_TAKENUMBER.mp3</pre>

Some code to automate it in python (for easy crontab deployment)

<pre class="prettyprint"># Script to record Studio Brussel at Friday
# Default record time = 60 minutes
# Best run from crontab
DEBUG=True

import os,sys
from datetime import *
import time

MINUTES=59
#Default to current week
WEEK_NUMBER=datetime.date(datetime.now()).isocalendar()[1]
TAKE_NUMBER=1 #No argumnet given? it wil use take1 and overwrite it. 

try:
    TAKE_NUMBER=sys.argv[1]
except:
    print 'No take number provided: using default: %s' % TAKE_NUMBER
cmd='mplayer http://mp3.streampower.be/stubru-high -cache 4096 -dumpstream -dumpfile %s/studio_brussel_%s_day_%s_take_%s.mp3 &amp;' % (os.path.expanduser('~'), WEEK_NUMBER,datetime.today().isoweekday(),TAKE_NUMBER)
if DEBUG: print 'Executing cmd: %s' % cmd
os.system(cmd)
time.sleep(60*MINUTES)
os.system('killall mplayer')</pre>

Trigger it from cron for ultimate ease of mind.

<pre>#Crontab file for Friday night from 21:01 - Saturday morning 02:01 in 5 takes
1 21 * * 5 /usr/local/bin/record_studio_brussel.sh 1 &gt; studio_brussel.log
1 22 * * 5 /usr/local/bin/record_studio_brussel.sh 2 &gt; studio_brussel.log
1 23 * * 5 /usr/local/bin/record_studio_brussel.sh 3 &gt; studio_brussel.log
1 0 * * 6 /usr/local/bin/record_studio_brussel.sh 4 &gt; studio_brussel.log
1 1 * * 6 /usr/local/bin/record_studio_brussel.sh 5 &gt; studio_brussel.log</pre>

Now all you have to do is copy or symlink a shell script that launches it to your /usr/local/bin and make it executable.

<pre>#!/bin/bash
/usr/bin/python /usr/local/bin/record_studio_brussel.py $1</pre>

[<img class="alignnone size-medium wp-image-784" alt="liveismusic" src="http://www.renedohmen.nl/blog/wp-content/uploads/2013/03/liveismusic-300x223.png" width="300" height="223" />](http://www.renedohmen.nl/blog/wp-content/uploads/2013/03/liveismusic.png)

[<img class="alignnone size-medium wp-image-812" alt="screenie_ brussel" src="http://www.renedohmen.nl/blog/wp-content/uploads/2013/03/screenie_-brussel-300x27.png" width="300" height="27" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2013/03/screenie_-brussel-300x27.png 300w, http://www.renedohmen.nl/blog/wp-content/uploads/2013/03/screenie_-brussel.png 911w" sizes="(max-width: 300px) 100vw, 300px" />](http://www.renedohmen.nl/blog/wp-content/uploads/2013/03/screenie_-brussel.png)
  
Have a nice one.