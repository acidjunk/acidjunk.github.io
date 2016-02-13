---
id: 1034
title: Determine sqlite table size on disk
date: 2014-05-28T19:58:48+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=1034
permalink: /2014/05/determine-sqlite-table-size-on-disk/
categories:
  - Computerz
header-img: "img/post-bg-01.jpg"
---
I took me a while to find out that it&#8217;s not very easy to find out how big a sqlite table is on disk. But luckily the sqlite creators have a simple tool for that. It&#8217;s called sqlite3_analyzer and is available in precompiled format for Linux, Windows and OSX on [SQLite&#8217;s Download section](http://www.sqlite.org/download.html)

Confusing: There also seems to be a commercial graphical sqlite tool in a windows only variant that has the same name, but it doesn&#8217;t have functionality to see how big tables are. http://www.kraslabs.com/sqlite_analyzer.php

When you run sqlite3_analyzer it will create a .sql file with info about the database. You can insert the .sql file in a new database to get more detailed info about the tables sizes and some other metrics.

<pre>./sqlite3_analyze path_to_db/database.sqlite > dbinfo.sql
</pre>

It will produce a sql file with a big sql comment on top. After the comment some SQL statements are printed that will create a table &#8220;space_used&#8221; with more detailed info.

Example:
  
the example DB is 381Mb on disk. The Binary table is used to store some binary data.

<pre>Page size in bytes................................ 1024      
Pages in the whole file (measured)................ 390022    
Pages in the whole file (calculated).............. 390022    
Pages that store data............................. 390022     100.0% 
Pages on the freelist (per header)................ 0            0.0% 
Pages on the freelist (calculated)................ 0            0.0% 
Pages of auto-vacuum overhead..................... 0            0.0% 
Number of tables in the database.................. 51        
Number of indices................................. 2         
Number of defined indices......................... 0         
Number of implied indices......................... 2         
Size of the file in bytes......................... 399382528 
Bytes of user payload stored...................... 390583107   97.8% 

*** Page counts for all tables with their indices *****************************

BINARY............................................ 301833      77.4% 
INSTALL........................................... 70156       18.0% 
MAIL_QUEUE........................................ 15847        4.1% 
ACCOUNT_INFO...................................... 602          0.15% 
NODE_info......................................... 591          0.15% 
etc.
</pre>

I used it to clean up some DB&#8217;s with a lot of tables. After deleting a lot of records I noticed that the file size didn&#8217;t shrink, so as a reminder for myself; you have to execute one SQLite SQL statement to free up disk space after a lot of delete statements: VACUUM;