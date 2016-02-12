---
id: 1049
title: Some handy ls and find tricks with dates
date: 2014-09-03T18:55:09+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=1049
permalink: /2014/09/some-handy-ls-and-find-tricks-with-dates/
categories:
  - Computerz
---
As a quick reminder for myself; some ls and find variations to do stuff with files and dates.

ls sort on date:

<pre>ls -t
</pre>

ls reverse sort on date:

<pre>ls -tr
</pre>

ls reverse sort on modifed date, show hidden files, showdetails and print it in human readable form

<pre>ls -alhtr
</pre>

find all files in current dirs and subdirs (e.g. recursively) that are changed in the last 5 minutes:

<pre>find . -type f -mmin -5 -print0 | xargs -0 /bin/ls -ltr
</pre>

Find all files on filesystem that were modified maximally 3 * 24 hours (3 days) ago till now:

<pre>find / -ctime 3
</pre>