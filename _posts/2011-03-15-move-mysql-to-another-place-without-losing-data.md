---
id: 166
title: Move mysql to another place without losing data
date: 2011-03-15T15:50:29+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=166
permalink: /2011/03/move-mysql-to-another-place-without-losing-data/
categories:
  - Computerz
---
So you need to physically move around your mysql databases, typically because you want to put them on a another partition or hard drive, or on some network device ? This is how you can do it.

My comp runs debian unstable, but the following should apply to any recent Debian or Ubuntu distribution.   

  
First stop the mysql service :

<pre>root@comp:~/# /etc/init.d/mysql stop<br /> 
* Stopping MySQL database server mysqld                                 [ OK ]</pre>

Then go to your current mysql data directory, by default in Debian / Ubuntu it should be /var/lib/mysql. Check that your databases are there (in this example I have 2 bases &#8211; the default &#8216;mysql&#8217; base and a user-created &#8216;wpdb&#8217; base) :

<pre>root@comp:~/# cd /var/lib/mysql<br /> 
root@comp:~/# ls<br /> 
total 21M<br /> 
-rw-rw---- 1 mysql  10M 2008-05-01 14:39 ibdata1<br /> 
-rw-rw---- 1 mysql 5.0M 2008-05-01 14:39 ib_logfile0<br /> 
-rw-rw---- 1 mysql 5.0M 2008-04-27 20:57 ib_logfile1<br /> 
drwxr-xr-x 2 mysql 4.0K 2008-04-27 20:57 mysql<br /> 
-rw------- 1 root     6 2008-04-27 20:57 mysql_upgrade_info<br /> 
drwx------ 2 mysql 4.0K 2008-04-28 19:28 wpdb</pre>

Create a new directory for your data (in this example, the /var/www directory which is located on another partition) and give ownership on it to the mysql user :

<pre>root@comp:~/#  mkdir /var/www/mysql_datadir<br /> 
root@comp:~/#  chown -R mysql:mysql /var/www/mysql_datadir</pre>

Copy your databases to the new dir and update ownership if needed. Only move the databases dirs, don&#8217;t touch the other files.

<pre>root@comp:~/#  cp -r mysql /var/www/mysql_datadir/<br /> 
root@comp:~/#  cp -r wpdb /var/www/mysql_datadir/<br /> 
root@comp:~/#  chown -R mysql:mysql /var/www/mysql_datadir/*<br /> 
</pre>

Then update your my.conf file to make it point to the new dir :

<pre>root@comp:~/# vim /etc/mysql/my.conf</pre>

Find the following statement :

<pre>datadir         = /var/lib/mysql</pre>

and update with the new location :

<pre>datadir         = /var/www/mysql_datadir</pre>

And finally restart the mysql service

<pre>root@comp:~/# /etc/init.d/mysql start<br /> 
* Starting MySQL database server mysqld                                 [ OK ]<br /> 
</pre>

When restarting, mysql re-created files ibdata1, ib_logfile0, etc. in the new data dir.   

  
If everything went OK, you can now remove the original dir. Voilà !