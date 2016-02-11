---
id: 582
title: Basic authentication with apache modwsgi and web2py
date: 2012-08-06T00:30:30+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=582
permalink: /2012/08/basic-authentication-with-apache-modwsgi-and-web2py/
categories:
  - Computerz
---
I spent over an hour trying to figure out why I wasn&#8217;t able

to do basic authentication in a web2py service before I ran across a prior post that described this essential step.

If you&#8217;re using Apache with mod_wsgi and you want to use basic

authentication with a web2py service, don&#8217;t forget to add the line

&#8220;WSGIPassAuthorization On&#8221; to wsgi.conf under /etc/apache2/mods-

enabled.

Or in your vhost settings:

> ServerName www.mainserver.com
> 
> ServerAlias super.alias.nl mainserver.com
> 
> WSGIDaemonProcess mainserver user=appuser group=appuser \
> 
> display-name=%{GROUP}
> 
> WSGIProcessGroup mainserver
> 
> WSGIScriptAlias / /webapps/mainserver/wsgihandler.py
> 
> WSGIPassAuthorization On