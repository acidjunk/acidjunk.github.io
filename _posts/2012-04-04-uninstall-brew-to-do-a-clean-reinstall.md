---
id: 510
title: Uninstall brew, to do a clean reinstall
date: 2012-04-04T16:26:40+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=510
permalink: /2012/04/uninstall-brew-to-do-a-clean-reinstall/
categories:
  - Computerz
---
In the last year I switched from macports/fink to brew; it has a lot of advantages. It also doesn&#8217;t ruin your system because it keeps it stuff inside /usr/local

But if you want to update a rather complex brew environment you&#8217;re in trouble. Some maintainers like the Riverwind guys only provide the last pyqt for download making it impossible to install an older version with homebrew. So in some cases it&#8217;s best to just completly remove the homebrew install and start over from scratch with the latest homebrew.

<pre>$ brew --prefix</pre>

In most cases it wil output: /usr/local

<pre>$ cd /usr/local
$ rm -rf Cellar
$ brew prune
$ rm -rf Library .git .gitignore bin/brew README.md share/man/man1/brew
$ rm -rf ~/Library/Caches/Homebrew</pre>

Then reinstall it with the next command, or better yet ; copy it from the brew site again at https://github.com/mxcl/homebrew/wiki/installation:

<pre>$ /usr/bin/ruby -e "$(/usr/bin/curl -fksSL https://raw.github.com/mxcl/homebrew/master/Library/Contributions/install_homebrew.rb)"</pre>