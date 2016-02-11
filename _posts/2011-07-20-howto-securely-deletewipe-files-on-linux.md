---
id: 243
title: howto securely delete/wipe files on linux
date: 2011-07-20T14:41:35+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=243
permalink: /2011/07/howto-securely-deletewipe-files-on-linux/
categories:
  - Computerz
---
For the BTP we needed a way to wipe data for returning broken comps to the manufacturer. After a search on Google I found wipe.sourceforge.net; but that seemed old and buggy. Then I found some tools in a suite called secure-delete. It&#8217;s in the default debian repo&#8217;s

So on Debian/Ubuntu:

    sudo apt-get install secure-delete

A quick howto:

packacge secure-delete has four tools:

srm &#8211; securely delete an existing file
  
smem &#8211; securely delete traces of a file from ram
  
sfill &#8211; wipe all the space marked as empty on your hard drive
  
sswap &#8211; wipe all the data from you swap space.

From the man page of srm

       srm  is  designed to delete data on mediums in a secure manner which can not be recovered by thiefs, law enforce‐ment or other threats.  The wipe algorythm is based on the paper "Secure  Deletion  of  Data  from  Magnetic  and Solid-State  Memory" presented at the 6th Usenix Security Symposium by Peter Gutmann, one of the leading civilian cryptographers.
    
       The secure data deletion process of srm goes like this:
    
       *      1 pass with 0xff
    
       *      5 random passes. /dev/urandom is used for a secure RNG if available.
    
       *      27 passes with special values defined by Peter Gutmann.
    
       *      5 random passes. /dev/urandom is used for a secure RNG if available.
    
       *      Rename the file to a random value
    
       *      Truncate the file
    
       As an additional measure of security, the file is opened in O_SYNC mode and after each pass an  fsync()  call  is done.   srm writes 32k blocks for the purpose of speed, filling buffers of disk caches to force them to flush and overwriting old data which belonged to the file.