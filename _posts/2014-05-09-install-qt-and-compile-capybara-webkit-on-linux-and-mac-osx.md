---
id: 1029
title: Install Qt and compile Capybara webkit on Linux and mac OSX
date: 2014-05-09T23:03:06+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=1029
permalink: /2014/05/install-qt-and-compile-capybara-webkit-on-linux-and-mac-osx/
categories:
  - Computerz
---
To automate browser style testing in Ruby you can use Qt webkit caompatible browser with CapyBara.
  
When you try to install it you&#8217;ll get this error when qmake isn&#8217;t found:

<pre>An error occurred while installing capybara-webkit (1.1.0), and Bundler cannot
continue.
Make sure that `gem install capybara-webkit -v '1.1.0'` succeeds before
bundling.
</pre>

To solve this you have to install Qt.

Linux:

<pre>sudo apt-get install libqtwebkit-dev
</pre>

OSX with home brew

<pre>brew update
brew install qt
</pre>

Install capybara:

<pre>gem install capybara-webkit -v '1.1.0'
</pre>