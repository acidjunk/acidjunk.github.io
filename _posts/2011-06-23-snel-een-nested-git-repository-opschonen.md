---
id: 198
title: Snel een nested git repository opschonen
date: 2011-06-23T21:15:07+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=198
permalink: /2011/06/snel-een-nested-git-repository-opschonen/
categories:
  - Computerz
---
Als je snel in een hoop mappen en sub mappen alle git informatie wil opschonen, kun je dit doen:

$ find . -name &#8216;.git&#8217; -type d | xargs rm -rf
  
$ find . -name &#8216;.gitignore&#8217; | xargs rm -rf
  
$ find . -name &#8216;.gitmodules&#8217; | xargs rm -rf