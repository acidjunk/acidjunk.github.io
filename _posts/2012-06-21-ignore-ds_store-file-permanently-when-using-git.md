---
id: 584
title: Ignore .DS_Store file permanently when using Git
date: 2012-06-21T22:45:27+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=584
permalink: /2012/06/ignore-ds_store-file-permanently-when-using-git/
categories:
  - Computerz
---
With a couple of little commands, you’ll be able to ignore the .DS_Store files forever from your git repositories on mac!

Create (or append) the .DS_Store to a .gitignore file in your homedir.

<pre>echo .DS_Store >> ~/.gitignore
</pre>

The following command will add the .gitignore file to the git configuration

<pre>git config --global core.excludesfile ~/.gitignore
</pre>