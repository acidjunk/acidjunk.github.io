---
id: 1140
title: Setup a windows comp for Django1.8 with Python 3.4 and Psycopg2
date: 2015-07-09T07:59:30+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=1140
permalink: /2015/07/setup-a-windows-comp-for-django1-8-with-python-3-4-and-psycopg2/
categories:
  - Computerz
comments: true
header-img: "img/post-bg-01.jpg"
---
As a Linux user the installation of all deps is rather easy; you run a couple of apt-get installs and some pip installs inside a virtual env and your are good to go. On windows there are some steps you need to do by hand. Normally I like to compile my own C extensions where possible, but after 2 tries I gave up on that as you need to have a rather complex setup. Python 3.5 seems to solve this by allowing you to compile C extensions with another compiler versions then the one used to compile the used python version itself. So for now I sticked to using some binaries.

## Step 1: Install Python3.4

I used the 64-bit MSI installer from [python.org](https://www.python.org/downloads/release/python-343/). You can use the installer to add Python to your Path or do it by hand:
  
<pre>
C:\Python34\;C:\Python34\Scripts\;
</pre>

## Step 2: Create a virtualenv

As of Python3.3 venv is part of Python itself! So go ahead and create a virtualenv for your django project somewhere. I personally like to have my virtualenvs in a folder in my home dir: .virtualenvs ->

<pre>mkdir .virtualenvs
cd .virtualenvs
python -m venv django1.8-project
</pre>

You can now activate your virtual env by navigating to 
<pre>.virtualenvs/django1.8-project/bin</pre>
and run activate.bat

## Step 3: Download a Psycopg2 binary

Psycopg2 is one of the difficult packages in modern django stack. With python27 you could compile it yourself relatively easy by using the Microsofot Visual Studio Python Redistributable; but this is bound to python 2.7.

Download the version you want: [latest at the moment of writing](http://www.stickpeople.com/projects/python/win-psycopg/2.6.1/psycopg2-2.6.1.win-amd64-py3.4-pg9.4.4-release.exe) or choose your own version: http://www.stickpeople.com/projects/python/win-psycopg/

Look inside the requirements.txt for a given project if you want to know which PSycopg version you need.

Now activate your virtualenv and install it with: 

<pre>easy_install package.exe</pre>

You can now proceed installing other packages, assuming no further C extensions are listed in the requirement.txt 

## Step 4: Install other deps

When working on another project you&#8217;ll probably have and requirements.txt. Go ahead and install the other deps. From an activated venv: 

<pre>pip install -r requirements.txt</pre>

If you just want an empty Django project: you can save you virtualenv.

<pre>pip install django
pip freeze > requirements.txt
</pre>