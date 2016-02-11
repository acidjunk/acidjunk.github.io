---
id: 1103
title: Install phpunit on windows
date: 2015-02-23T13:53:08+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=1103
permalink: /2015/02/install-phpunit-on-windows/
categories:
  - Computerz
---
You can use composer to install phpunit, for example, inside a Symfony2 project; but it&#8217;s better to install it as a separate binary as it allows you to run unit test on all php scripts and it integrates better in phpStorm.

#### Create folder to hold php bins

I used an Applications folder in my windows home; but you can also user C:\bin or something like that.
  
Add the folder to your Path: e.g. add &#8220;;C:\bin&#8221; to your PATH environment variable. In the Advanced System Properties, Environment variables:
  
[<img class="alignnone size-medium wp-image-1106" src="http://www.renedohmen.nl/blog/wp-content/uploads/2015/02/2015-02-23-13_35_17-Program-Manager-270x300.png" alt="2015-02-23 13_35_17-Program Manager" width="270" height="300" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2015/02/2015-02-23-13_35_17-Program-Manager-270x300.png 270w, http://www.renedohmen.nl/blog/wp-content/uploads/2015/02/2015-02-23-13_35_17-Program-Manager.png 428w" sizes="(max-width: 270px) 100vw, 270px" />](http://www.renedohmen.nl/blog/wp-content/uploads/2015/02/2015-02-23-13_35_17-Program-Manager.png)[<img class="alignnone size-medium wp-image-1107" src="http://www.renedohmen.nl/blog/wp-content/uploads/2015/02/2015-02-23-13_36_31-Program-Manager-271x300.png" alt="2015-02-23 13_36_31-Program Manager" width="271" height="300" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2015/02/2015-02-23-13_36_31-Program-Manager-271x300.png 271w, http://www.renedohmen.nl/blog/wp-content/uploads/2015/02/2015-02-23-13_36_31-Program-Manager.png 397w" sizes="(max-width: 271px) 100vw, 271px" />](http://www.renedohmen.nl/blog/wp-content/uploads/2015/02/2015-02-23-13_36_31-Program-Manager.png) 

#### Download the .phar file

Download https://phar.phpunit.de/phpunit.phar and save the file as C:\bin\phpunit.phar

#### Create a .bat wrapper

Open a command line (e.g., press Windows+R » type cmd » ENTER)

<pre>cd C:\bin
echo @php "%~dp0phpunit.phar" %* > phpunit.cmd
exit
</pre>

Verify that it worked by openening a new command line: type &#8220;phpunit&#8221; and press enter. It should show the phpunit options.