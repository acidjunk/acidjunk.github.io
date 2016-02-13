---
id: 733
title: Remove a python dependency by hand
date: 2013-05-29T17:47:42+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=733
permalink: /2013/05/remove-a-python-dependency-by-hand/
categories:
  - Computerz
header-img: "img/post-bg-01.jpg"
---
If you are on a system without pip or easyinstall, and you can&#8217;t use the OS package system: You need to remove all installed files manually, and also undo any other stuff that the installation did manually. Changes are that you don&#8217;t know the list of all files it installed, you can reinstall it with the &#8211;record option, and take a look at the list this produces.

<pre>python setup.py install --record files.txt</pre>

And when you think the list is complete: 

<pre>cat files.txt | xargs rm -rf</pre>