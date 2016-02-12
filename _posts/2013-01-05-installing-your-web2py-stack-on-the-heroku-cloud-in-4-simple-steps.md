---
id: 690
title: Installing your web2py Stack on the Heroku cloud in 4 simple steps
date: 2013-01-05T22:26:32+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=690
permalink: /2013/01/installing-your-web2py-stack-on-the-heroku-cloud-in-4-simple-steps/
categories:
  - Computerz
---
One of the coolest things about web2py is it&#8217;s ability to run on most of the modern cloud solutions that are available on the web. It runs, without much modifications on Heroku, Amazon cloud, Google App Engine, Redhats OpenShift, Dotcloud and probably on some &#8220;do it yourself&#8221; cloud solutions. So on a cloudy and rainy day I started some tests to see what clouds would be cloudy enough for our purposes.

Here is what I did to get a testing environment on the Heroku App cloud on my Ubuntu 12.04 LTS Workstation:

  1. Sign up and [follow the instuctions](https://devcenter.heroku.com/articles/quickstart)in Heroku Quick start manual to get a Heroku toolchain for Ubuntu installed. You could copy paste the next command if you feel safe with me 😉 
    <pre>wget -qO- https://toolbelt.heroku.com/install-ubuntu.sh | sh</pre>

  2. Get a clean web2py: 
    <pre>git clone https://github.com/web2py/web2py.git heroku_root</pre>

  3. Copy Massimo&#8217;s &#8220;one script does it all&#8221; solution to the web2py root and run it: 
    <pre>cd heroku_root
cp scripts/setup-web2py-heroku.sh .
chmod +x setup-web2py-heroku.sh
./setup-web2py-heroku.sh</pre>

  4. That&#8217;s it; Your app is deployed and Heroku opened a browser showing you
  
    [<img class="alignnone size-medium wp-image-694" title="web2py welcome heroku" src="http://www.renedohmen.nl/blog/wp-content/uploads/2013/01/web2py-welcome-heroku-300x256.png" alt="" width="300" height="256" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2013/01/web2py-welcome-heroku-300x256.png 300w, http://www.renedohmen.nl/blog/wp-content/uploads/2013/01/web2py-welcome-heroku.png 805w" sizes="(max-width: 300px) 100vw, 300px" />](http://www.renedohmen.nl/blog/wp-content/uploads/2013/01/web2py-welcome-heroku.png)