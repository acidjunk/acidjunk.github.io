---
id: 1018
title: Install Ruby on Rails on Ubuntu 14.04 with RVM
date: 2014-03-28T14:52:06+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=1018
permalink: /2014/03/install-ruby-on-rails-on-ubuntu-14-04-with-rvm/
categories:
  - Computerz
header-img: "img/post-bg-01.jpg"
---
Installing Ruby on Rails on Ubuntu is quite easy, but the Ubuntu packages install an outdated Ruby. The following instruction will probably work on older Ubuntu versions also, I just used the 14.04 test release to get a preview on the next LTS version of Ubuntu.

This is just a quick install without RVM. If you want a more flexible and sipler setup, where you more easily switch between Ruby and Rails version, you can follow the instructions [here](http://gorails.com/setup/ubuntu/14.04) to install it with rbenv.

For a quick comparison between rbenv en RVM you can read [this](http://jonathan-jackson.net/rvm-and-rbenv)

## Install latest ruby from source

First install some debs.

<pre>sudo apt-get install curl
curl -L https://get.rvm.io | bash -s stable --ruby
source /home/acidjunk/.rvm/scripts/rvm
sudo apt-get install nodejs</pre>

Optionally you can install a newer version of nodejs by using a non Ubuntu repo:

<pre>sudo apt-get install python-software-properties
sudo apt-add-repository -y ppa:chris-lea/node.js
sudo apt-get update
sudo apt-get nodejs</pre>

Then install Ruby itself and let RVM do the hard lifting. Check if you have a working gem by running &#8220;gem -v&#8221;; expected output:

<pre>2.2.2</pre>

Note: you probably want to add the new gem path to your profile. This session it will work because you runned: &#8220;source /home/acidjunk/.rvm/scripts/rvm&#8221;
  
Install latest ruby and Rails itself

<pre>rvm use ruby-2.1.1@rails4.0 --create
gem install rails</pre>

## Test your install

<pre>mkdir rails_projects
cd rails_projects
mkdir helloworld
cd helloworld
rails new .
rails server</pre>

Expected output:

<pre>=&gt; Booting WEBrick
=&gt; Rails 4.0.4 application starting in development on http://0.0.0.0:3000
=&gt; Run `rails server -h` for more startup options
=&gt; Ctrl-C to shutdown server
[2014-04-05 17:40:12] INFO  WEBrick 1.3.1
[2014-04-05 17:40:12] INFO  ruby 2.1.1 (2014-02-24) [x86_64-linux]
[2014-04-05 17:40:12] INFO  WEBrick::HTTPServer#start: pid=3497 port=3000</pre>

## A screenshot of the running Rails install

[<img class="alignnone size-medium wp-image-1019" alt="Rails on Ubuntu 14.04" src="http://www.renedohmen.nl/blog/wp-content/uploads/2014/04/Screenshot-from-2014-04-05-174156-300x260.png" width="300" height="260" />](http://www.renedohmen.nl/blog/wp-content/uploads/2014/04/Screenshot-from-2014-04-05-174156.png)

## rbenv

Installing Rails with rbenv is also easy: just follow the instructions [here](http://timwise.blogspot.nl/2013/05/installing-ruby-2-rails-4-on-ubuntu.html).