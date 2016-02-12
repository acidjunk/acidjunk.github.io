---
id: 661
title: Using the web2py scheduler for long running jobs
date: 2012-12-08T02:58:51+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=661
permalink: /2012/12/using-the-web2py-scheduler-for-long-running-jobs/
categories:
  - Computerz
---
The info in the book describes the scheduler and favors it over cron; So I decided to use it for fetching the RSS feeds in one of our web apps.

Create a new model tasks.py

<pre>def doTask():
     return dict(result="done")

from gluon.scheduler import Scheduler
Scheduler(db,dict(testtask=doTask))</pre>

Now web2py will notice the call to Scheduler and it will create the needed tables. You can now use the app admin to enter the first task.

[<img class="alignnone size-full wp-image-672" title="Screenshot from 2012-12-08 00:29:04" src="http://www.renedohmen.nl/blog/wp-content/uploads/2012/12/Screenshot-from-2012-12-08-002904.png" alt="" width="482" height="145" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2012/12/Screenshot-from-2012-12-08-002904-300x90.png 300w, http://www.renedohmen.nl/blog/wp-content/uploads/2012/12/Screenshot-from-2012-12-08-002904.png 482w" sizes="(max-width: 482px) 100vw, 482px" />](http://www.renedohmen.nl/blog/wp-content/uploads/2012/12/Screenshot-from-2012-12-08-002904.png)

With your new task in there; you are almost ready. You can now start a new web2py instance that will run the tasks for you:

<pre>python web2py.py --nogui -K APP_NAME -D15</pre>

_The -D15 indicates Debug loglevel-> 15 is info</> </p> 

### Output

<pre>web2py Web Framework
Created by Massimo Di Pierro, Copyright 2007-2012
Version 2.3.0 (2012-12-07 10:57:44) rc1
Database drivers available: SQLite(sqlite3), MySQL(pymysql), MySQL(MySQLdb), PostgreSQL(pg8000), IMAP(imaplib)
starting single-scheduler for "APP_NAME"...</pre>

You will see your tasks being scheduled; it will look like this:

[<img class="alignnone size-medium wp-image-674" title="Screenshot from 2012-12-08 01:03:43" src="http://www.renedohmen.nl/blog/wp-content/uploads/2012/12/Screenshot-from-2012-12-08-010343-300x17.png" alt="" width="300" height="17" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2012/12/Screenshot-from-2012-12-08-010343-300x17.png 300w, http://www.renedohmen.nl/blog/wp-content/uploads/2012/12/Screenshot-from-2012-12-08-010343.png 718w" sizes="(max-width: 300px) 100vw, 300px" />](http://www.renedohmen.nl/blog/wp-content/uploads/2012/12/Screenshot-from-2012-12-08-010343.png)

### Some quick links

<pre>## schedule jobs using
http://127.0.0.1:8000/APP_NAME/appadmin/insert/db/scheduler_task
## monitor scheduled jobs
http://127.0.0.1:8000/APP_NAME/appadmin/select/db?query=db.scheduler_task.id&gt;0
## view completed jobs
http://127.0.0.1:8000/APP_NAME/appadmin/select/db?query=db.scheduler_run.id&gt;0
## view workers
http://127.0.0.1:8000/APP_NAME/appadmin/select/db?query=db.scheduler_worker.id&gt;0</pre>

### More info

You will find a test case and some code [here](https://github.com/niphlod/w2p_scheduler_tests)