---
title: Switch from wordpress to jekyll
subtitle: How to export data from a wordpress to a Jekyll site
date: 2016-02-12
author: acidjunk
layout: post
permalink: /2016/02/switch-from-wordpress-to-jekyll/
categories:
  - Computerz
header-img: "img/header-dev-01.jpg"
comments: true
---
As I don't do a lot with PHP nowadays the constant upgrading and other maintenance stuff for my old wordpress site 
became a pain in the ass. So, as you can see, I decided to create a static site powered by Jekyll. Not only does this 
setup get rid of the need to have a database, hosting it is free on github itself.

The github-pages setup itself is simple and [documented well](https://pages.github.com/)
Adding jekyll is [not hard either](http://jekyllrb.com/docs/quickstart/), most time was lost in choosing a nice template 
that will continue to receive some support and setting up required Ruby gems on my OSX El Capitan workstations. As I 
don't use ruby a lot I decided to stay with the system Ruby and installed gem files by hand with -n /usr/local/bin
Probably better though to use a homebrew variant. You only need the Ruby/Jekyll stuff when you want to preview you page locally.

For the theme I used the excellent Bootstrap compliant blog: 
[https://github.com/BlackrockDigital/startbootstrap-clean-blog-jekyll](https://github.com/BlackrockDigital/startbootstrap-clean-blog-jekyll)
The only downside seems to be a rather old Jekyll version: 2.4 as we speak.

I explored 2 ways to get my old wordpress content in my new blog: A [jekyll based importer](http://import.jekyllrb.com/docs/installation/) that 
uses a connection to the database to get content and converts this to .md files in your _posts folder. And a 
[wordpress plugin](https://github.com/benbalter/wordpress-to-jekyll-exporter). The biggest advantage of the wordpress plugin is how easy it 
worked and that it can even export content that is post processed by wordpress plugins. It will produce a .zip with a _posts folder and folder that 
contain uploaded media and other stuff. I still have some work to do with the image assets and cleanup of content, but a least no more crappy marked-up HTML.