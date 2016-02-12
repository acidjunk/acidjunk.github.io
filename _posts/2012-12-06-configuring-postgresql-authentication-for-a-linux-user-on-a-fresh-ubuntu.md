---
id: 646
title: Configuring postgresql authentication for a linux user on a fresh Ubuntu
date: 2012-12-06T18:04:44+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=646
permalink: /2012/12/configuring-postgresql-authentication-for-a-linux-user-on-a-fresh-ubuntu/
categories:
  - Computerz
---
By default in Ubuntu, postgresql is configured to use &#8216;ident sameuser&#8217; authentication for any connections from the same machine. Check out the excellent Postgresql documentation for more information, but essentially this means that if your Ubuntu username is &#8216;foo&#8217; and you add &#8216;foo&#8217; as a postgresql user then you can connect to the database without requiring a password. Obviously this is not something you would do on a server but for a workstation connecting locally to your postgres database it isn&#8217;t a problem.

<pre>sudo apt-get install postgres</pre>

Since the only user who can connect to a fresh install is the postgres user, here is how to create yourself a database account (which is in this case also a database superuser) with the same name as your login name and then create a password for the user:

<pre>sudo -u postgres createuser --superuser $USER
 sudo -u postgres psql</pre>

Then give the new postgres user a password with.

<pre>postgres=# \password $USER</pre>

You are done now. If you would try it out now on a default Ubuntu install it would complain about missing a database with the same username as your linux user. But a simple &#8220;psql -d postgres&#8221; would work without any errors.

### Some optional steps

Client programs, by default, connect to the local host using your Ubuntu login name and expect to find a database with that name too. So to make things REALLY easy, use your new superuser privileges granted above to create a database with the same name as your login name:

<pre>createdb $USER</pre>

Connecting to your own database to try out some SQL should now be as easy as:

<pre>psql</pre>

Creating additional database is just as easy: createdb mydb