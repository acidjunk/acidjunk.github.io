---
id: 210
title: Dual screen setup with gnome shell
date: 2011-06-29T13:59:54+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=210
permalink: /2011/06/dual-screen-setup-with-gnome-shell/
categories:
  - Computerz
---
I just switched to gnome 3 AKA gnome-shell. It works nice but there is one problem. For some reason my second monitor is fixed to workspace 1. For me this feels like one of my monitors is crippled.

After googling the internet for answers I found that a lot of people have the same problem.

At last I found a solution that works just fine for me:

  * start gconf-editor
  * navigate to /desktop/gnome/shell/windows
  * deactivate the option: workspaces\_only\_on_primary
  * log out and log in again

You should have a working dualscreen setup now, just like it was in the old days. So when I switch to workspace 2 (with CTRL + ALT + ARROW DOWN) then both monitors go to workspace 2.

I also found another solution for the problem, but that didn&#8217;t work well for me (this could be related to me not logging out and in again):

  * start gconf-editor
  * navigate to /apps/mutter/general
  * disable: workspace\_only\_on_primary

&nbsp;

&nbsp;