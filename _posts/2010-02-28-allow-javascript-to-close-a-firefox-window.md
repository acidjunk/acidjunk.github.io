---
id: 26
title: Allow javascript to close a firefox window
date: 2010-02-28T21:38:09+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=26
permalink: /2010/02/allow-javascript-to-close-a-firefox-window/
categories:
  - Computerz
---
Just as a quick reminder for myself; firefox diasallows closing the window with javascript, sometimes, e.g. on a kiosk comp, it&#8217;s very handy to have the browser closed by javascript.

1. Type **about:config** in the address bar and press **Enter**.

2. Find the setting **dom.allow\_scripts\_to\_close\_windows.**

3. Double-click on the setting to set it to **true** to enable scripts to close the browser window via **close()**. Set it to **false** to prevent scripts from closing windows via **close()**.

Note: This setting is available in Firefox 3 and Firefox 2.