---
id: 987
title: Running Unity3D webplayer on your linux box
date: 2014-03-11T00:35:32+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=987
permalink: /2014/03/running-unity3d-webplayer-on-your-linux-box/
categories:
  - Computerz
header-img: "img/post-bg-01.jpg"
---
As NaCl builds are not working at all in Unity4.3 and Flash is most likely to be removed from future Unity versions the only native way to play Unity games on your Linux box is via a standalone game. But with the same technique that enables watching Netflix on Ubuntu it&#8217;s also possible to install the Unity Webplayer plguin for Chrome and Firefox.

First remove previous PPA as they will no be updated anymore. You can skip this step if you didn&#8217;t install older compholio/pipelight versions.

<pre>sudo add-apt-repository --remove ppa:mqchael/pipelight
sudo add-apt-repository --remove ppa:mqchael/pipelight
</pre>

Now you are ready to add the new multiplugin pipelight PPA&#8217;s:

<pre>sudo add-apt-repository ppa:pipelight/stable
sudo apt-get update
sudo apt-get install --install-recommends pipelight-multi
sudo pipelight-plugin --update
</pre>

Note: you will see a dialog asking you to confirm the install of the Microsoft core-fonts; this is a package form the Ubuntu multiverse repository. It&#8217;s enabled by default on recent Ubuntu distro&#8217;s. Instructions to enable it on older distro&#8217;s can be found [here](http://askubuntu.com/questions/89096/how-do-i-enable-the-multiverse-repository).

Go ahead and enable silverlight, this is not needed for Unity webplayer, but watching Netflix is relaxing and it can be used to test the whole system. 

<pre>sudo pipelight-plugin --enable silverlight
</pre>

(wait for wine to finish installing)

Now you need an Chrome extension called &#8220;User-Agent Switcher for Chrome&#8221; so you can force the user agent to &#8220;Windows Firefox 15&#8221;. You can even spoof it on a permanent basis for the domain netflix.com.
  
[<img src="http://www.renedohmen.nl/blog/wp-content/uploads/2014/03/Schermafdruk-van-2014-03-11-005155-300x105.png" alt="Schermafdruk van 2014-03-11 00:51:55" width="300" height="105" class="alignnone size-medium wp-image-990" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2014/03/Schermafdruk-van-2014-03-11-005155-300x105.png 300w, http://www.renedohmen.nl/blog/wp-content/uploads/2014/03/Schermafdruk-van-2014-03-11-005155.png 890w" sizes="(max-width: 300px) 100vw, 300px" />](http://www.renedohmen.nl/blog/wp-content/uploads/2014/03/Schermafdruk-van-2014-03-11-005155.png)

After that enable the Unity3d plugin:

<pre>sudo pipelight-plugin --enable unity3d
</pre>

(wait for wine to finish installing)

Important: set you user agent to Safari5, OSX; this is the only user-agent that worked for me!

Now try it with some games:
  
http://www.kongregate.com/games/flippfly/race-the-sun
  
http://dev.formatics.nl/tictactoe

[<img src="http://www.renedohmen.nl/blog/wp-content/uploads/2014/03/Schermafdruk-van-2014-03-11-011958-300x168.png" alt="Schermafdruk van 2014-03-11 01:19:58" width="300" height="168" class="alignnone size-medium wp-image-993" />](http://www.renedohmen.nl/blog/wp-content/uploads/2014/03/Schermafdruk-van-2014-03-11-011958.png)