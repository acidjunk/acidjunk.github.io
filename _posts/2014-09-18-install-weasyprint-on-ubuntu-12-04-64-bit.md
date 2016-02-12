---
id: 1045
title: Install Weasyprint on Ubuntu 12.04 64 bit
date: 2014-09-18T08:57:05+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=1045
permalink: /2014/09/install-weasyprint-on-ubuntu-12-04-64-bit/
categories:
  - Computerz
---
I had to tweak some stuff to get a running Weasyprint on one of our Ubuntu servers; just following the install instructions from the docs didn&#8217;t work:

<pre>sudo apt-get install python-dev python-pip python-lxml libcairo2 libpango1.0-0 libgdk-pixbuf2.0-0 libffi-dev shared-mime-info
apt-get install libxml2 libxml2-dev
apt-get install libxslt libxslt-dev
pip install WeasyPrint
pip install html5lib --upgrade
</pre>

Make sure your env is OK: in /etc/environment:
  
LC\_ALL=&#8221;en\_US.utf8&#8243;