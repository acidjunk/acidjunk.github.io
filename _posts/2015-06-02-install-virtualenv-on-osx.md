---
id: 1136
title: Install virtualenv and virtualenvwrapper on OSX
subtitle: Manage python dependencies with ease
date: 2015-06-02T08:14:14+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=1136
permalink: /2015/06/install-virtualenv-and-virtualenvwrapper-on-osx/
categories:
  - Computerz
  - OSX
comments: true
---
When running multiple python projects virtualenv is almost mandatory nowadays. It allows you to install python dependencies on a per project basis without screwing around with the OSX installed python. I especially like to install virtualenvwrapper also as it eases the way to create, used and delete virtual envs.


Choose whether you want OSX python or home brew version. When you choose home brew run:

<pre>brew install python</pre>

Then install virtualenv:

<pre>pip install virtualenv
pip install virtualenvwrapper
mkdir -p .virtualenvs</pre>

Add some conf stuff to your .bash_profile or .bash_rc

<pre>### Virtual envs
export WORKON_HOME=$HOME/.virtualenvs
export PROJECT_HOME=$HOME/GIT
source /usr/local/bin/virtualenvwrapper.sh
</pre>