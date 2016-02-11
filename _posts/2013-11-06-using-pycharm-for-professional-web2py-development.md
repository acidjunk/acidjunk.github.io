---
id: 938
title: Using PyCharm for professional web2py development
date: 2013-11-06T20:56:41+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=938
permalink: /2013/11/using-pycharm-for-professional-web2py-development/
categories:
  - Computerz
---
Our current IDE, Eclipse with PyDEV has some nice features but feels rather slow and clumsy. You also have to install a lot of plugins to get a reasonably working development environment. If you also install egit you will need a fast computer with lots of RAM. Having a good IDE will boost productivity, especially in web2py projects were navigating between controllers and views involves a lot of files an folders.

[<img class="alignnone size-medium wp-image-941" alt="Screenshot from 2013-11-06 21:55:00" src="http://www.renedohmen.nl/blog/wp-content/uploads/2013/11/Screenshot-from-2013-11-06-215500-300x169.png" width="300" height="169" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2013/11/Screenshot-from-2013-11-06-215500-300x169.png 300w, http://www.renedohmen.nl/blog/wp-content/uploads/2013/11/Screenshot-from-2013-11-06-215500-1024x577.png 1024w" sizes="(max-width: 300px) 100vw, 300px" />](http://www.renedohmen.nl/blog/wp-content/uploads/2013/11/Screenshot-from-2013-11-06-215500.png)

PyCharm has a lot of cool features:
  
&#8211; navigate from controller to view with one click (see the little &#8220;h&#8221; in my screenshot)
  
&#8211; autocomplete nearly everything you type
  
&#8211; refactor variables in controller and automatically rename the same variables in the views
  
&#8211; run web2py from inside PyCharm
  
&#8211; open multiple terminals in PyCharm
  
&#8211; excellent Vim support with ideaVim plugin

Read an older detailed independant review [here](http://andrewbrookins.com/tech/one-year-later-an-epic-review-of-pycharm-2-7-from-a-vim-users-perspective/).[Our current IDE, Eclipse with PyDEV has some nice features but feels rather slow and clumsy. You also have to install a lot of plugins to get a reasonably working development environment. If you also install egit you will need a fast computer with lots of RAM. Having a good IDE will boost productivity, especially in web2py projects were navigating between controllers and views involves a lot of files an folders.

[<img class="alignnone size-medium wp-image-941" alt="Screenshot from 2013-11-06 21:55:00" src="http://www.renedohmen.nl/blog/wp-content/uploads/2013/11/Screenshot-from-2013-11-06-215500-300x169.png" width="300" height="169" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2013/11/Screenshot-from-2013-11-06-215500-300x169.png 300w, http://www.renedohmen.nl/blog/wp-content/uploads/2013/11/Screenshot-from-2013-11-06-215500-1024x577.png 1024w" sizes="(max-width: 300px) 100vw, 300px" />](http://www.renedohmen.nl/blog/wp-content/uploads/2013/11/Screenshot-from-2013-11-06-215500.png)

PyCharm has a lot of cool features:
  
&#8211; navigate from controller to view with one click (see the little &#8220;h&#8221; in my screenshot)
  
&#8211; autocomplete nearly everything you type
  
&#8211; refactor variables in controller and automatically rename the same variables in the views
  
&#8211; run web2py from inside PyCharm
  
&#8211; open multiple terminals in PyCharm
  
&#8211; excellent Vim support with ideaVim plugin

Read an older detailed independant review [here](http://andrewbrookins.com/tech/one-year-later-an-epic-review-of-pycharm-2-7-from-a-vim-users-perspective/).](http://andrewbrookins.com/tech/one-year-later-an-epic-review-of-pycharm-2-7-from-a-vim-users-perspective/) 

### Install on Ubuntu

Step 1 and 2 can be skipped if you are already using Eclipse; it also works with openjdk; but only Sun Java is Supported by JetBrains.
  
1) Download the Sun/Oracle JRE from http://www.oracle.com/technetwork/java/javase/downloads/jre7-downloads-1880261.html and unzip it to /opt/
  
2) Make sure PyCharm can find JAVA_HOME: add this to your /etc/profile/

<pre>#Added for pycharm so it launches from the Ubuntu Unity menu
#Note: just adding JAVA_HOME to ~/.bashrc doesn't work as expected.
export JAVA_HOME=/opt/jre1.7.0_45
export PATH=$JAVA_HOME/bin:$PATH</pre>

3) Install PyCharm from: http://download.jetbrains.com/python/pycharm-professional-3.0.1.tar.gz. I just unzipped it to ~/Applications/
  
4) Reboot to make the changes in /etc/profile permanent and available; other wise launching it form the Ubuntu Unity menu might not work.