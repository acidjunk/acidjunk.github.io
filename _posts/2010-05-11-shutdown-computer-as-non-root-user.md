---
id: 36
title: Shutdown computer as non root user
date: 2010-05-11T21:42:33+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=36
permalink: /2010/05/shutdown-computer-as-non-root-user/
categories:
  - Computerz
---
**sudo** 

The program sudo allows normal users to execute certain root-only commands. Which users are authorized to run which commands is specified in the /etc/sudoers file. This should only be edited with the command visudo. For example, suppose I wanted to add a group of users who are allowed to shut down the machine.

So I first want to add a group called &#8220;shutdown&#8221; (run these commands while root) groupadd shutdown

Then I need to edit the /etc/group file to add users to the &#8220;shutdown&#8221; group. I just tack the usernames at the end of the shutdown line, separated by commas, e.g. shutdown:x:407:user1,user2,&#8230; Whatever users I put there will be able to shut down the computer (so choose wisely). Now I need to configure sudo to allow members of the &#8220;shutdown&#8221; group to actually invoke the assorted shutdown commands provided in linux. Run visudo and add the following lines

%shutdown ALL=(root) NOPASSWD: /sbin/reboot %shutdown ALL=(root) NOPASSWD: /sbin/halt %shutdown ALL=(root) NOPASSWD: /sbin/shutdown

This allows the &#8220;shutdown&#8221; group to run /sbin/reboot, /sbin/halt, and /sbin/shutdown AS IF THEY WERE ROOT.

The only caveat is that the users must run the commands with the command sudo in front, e.g. sudo /sbin/halt This is always a bit of a pain (and users never remember), so I can create the following script called &#8220;/usr/bin/reboot&#8221; (and similar scripts for halt and shutdown)

#! /bin/sh sudo /sbin/reboot

Set script executable and ownership of these scripts to the &#8220;shutdown&#8221; group chgrp shutdown. Then make them executable only for the group &#8220;shutdown&#8221; chmod g+x /usr/bin/reboot /usr/bin/halt /usr/bin/shutdown