---
id: 1136
title: Install virtualenv on OSX
date: 2015-06-02T08:14:14+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=1136
permalink: /2015/06/install-virtualenv-on-osx/
categories:
  - Computerz
---
Choose whether you want OSX python or home brew version. When you choose home brew run:

<pre>brew install python</pre>

Then install virtualenv:

<pre>pip install virtualenv
pip install virtualenvwrapper
mkdir -p .virtualenvs</pre>

Add some conf stuff to your .bash\_profile or .bash\_rc

<pre>### Virtual envs
export WORKON_HOME=$HOME/.virtualenvs
export PROJECT_HOME=$HOME/GIT
source /usr/local/bin/virtualenvwrapper.sh
</pre>