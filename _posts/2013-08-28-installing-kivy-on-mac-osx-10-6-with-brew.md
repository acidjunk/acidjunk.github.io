---
id: 863
title: Installing kivy on Mac OSX 10.6 with brew
date: 2013-08-28T00:19:14+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=863
permalink: /2013/08/installing-kivy-on-mac-osx-10-6-with-brew/
categories:
  - Computerz
---
We are doing more and more cool kivy stuff so it&#8217;s time to get the designers happy and let it run from src on their workstations for easy access to the graphics and .kv files.

## Step 1: Remove previous homebrew stuff and get a new one

Because I had an already F#ck up OS X with brew installed python, PyQt etc I decided to start over almost clean. I followed the instruction from: [here](http://superuser.com/questions/203707/how-to-uninstall-homebrew-osx-package-manager) to remove the older installed packages, although there could be better places; like the home brew FAQ it seems.
  
**Please skip this if you have a decent and recent homebrew, it will remove all installed packages**

<pre>cd `brew --prefix`
rm -rf Cellar
brew prune
rm `git ls-files`
rm -r Library/Homebrew Library/Aliases Library/Formula Library/Contributions
rm -rf .git
rm -rf ~/Library/Caches/Homebrew</pre>

I also reverted the PATH in my .profile back to normal (e.g. /usr/local/bin is loaded after the other bin paths).

The reinstall or install brew with:

<pre>ruby -e "$(curl -fsSL https://raw.github.com/mxcl/homebrew/go)"</pre>

<div>
</div>

## Step2: get a decent python

<pre>brew install python</pre>

I had some left overs from previous Cellar: linking failed, this is how I solved it.

<pre>brew link --overwrite python</pre>

Then I changed back the paths in my ~/.profile so /usr/local/bin preceeds the other bin paths in the PATH environment variabele: PATH=/usr/local/bin:$PATH

I restarted my terminal to verify that running python returns something like this:

<pre>Python 2.7.5 (default, Aug 23 2013, 03:07:24) 
[GCC 4.2.1 (Based on Apple Inc. build 5658) (LLVM build 2336.1.00)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
&gt;&gt;&gt;</pre>

## Step 3: install kivy based on the homebrew python

<pre>brew install mercurial</pre>

I had some left overs from previous Cellar: linking failed, this is how I solved it.

<pre>brew link --overwrite mercurial</pre>

Install SDL and other libs needed for pygame etc:

<pre>brew install sdl sdl_image sdl_mixer sdl_ttf portmidi</pre>

<pre>pip install cython
pip install pil
pip install hg+http://bitbucket.org/pygame/pygame
pip install kivy</pre>

I tested it with the kivy examples and they run really nice. Resizing of screen works, all examples seem to start ok.
  
[<img class="alignnone  wp-image-866" alt="Kivy examples 1.7.2 running on Mac OSX 10.6" src="http://www.renedohmen.nl/blog/wp-content/uploads/2013/08/Schermafbeelding-2013-08-28-om-02.17.02.png" width="1023" height="621" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2013/08/Schermafbeelding-2013-08-28-om-02.17.02-300x182.png 300w, http://www.renedohmen.nl/blog/wp-content/uploads/2013/08/Schermafbeelding-2013-08-28-om-02.17.02-1024x621.png 1024w, http://www.renedohmen.nl/blog/wp-content/uploads/2013/08/Schermafbeelding-2013-08-28-om-02.17.02.png 1279w" sizes="(max-width: 1023px) 100vw, 1023px" />](http://www.renedohmen.nl/blog/wp-content/uploads/2013/08/Schermafbeelding-2013-08-28-om-02.17.02.png)