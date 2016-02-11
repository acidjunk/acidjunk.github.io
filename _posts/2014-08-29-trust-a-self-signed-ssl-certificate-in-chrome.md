---
id: 1044
title: Trust a self signed SSL certificate in Chrome
date: 2014-08-29T22:51:41+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=1044
permalink: /2014/08/trust-a-self-signed-ssl-certificate-in-chrome/
categories:
  - Computerz
---
I&#8217;ve been using Google Chrome as my primary browser for the last few years. Sorry, Firefox, but with all the stuff I need to work installed, it&#8217;s to slow and almost unusable.

Let&#8217;s say you have a server with a self-signed HTTP SSL certificate. Every time you hit a page, you get a nasty error message. You ignore it once and it&#8217;s fine for that browsing session. But when you restart, it&#8217;s back. Unlike Firefox, there&#8217;s no easy way to say &#8220;yes, I know what I&#8217;m doing, ignore this.&#8221; This is an oversight I wish Chrome would correct, but until they do, we have to hack our way around it.

Caveat: these instructions are written for Mac OS X. PC instructions will be slightly different at PCs don&#8217;t have a keychain, and Google Chrome (unlike Firefox) uses the system keychain.

So here&#8217;s how to get Google Chrome to play nicely with your self-signed SSL certificate:

  1. In the address bar, click the little lock with the X. This will bring up a small information screen. Click the button that says &#8220;Certificate Information.&#8221;
  2. Click and drag the image to your desktop. It looks like a little certificate.
  3. Double-click it. This will bring up the Keychain Access utility. Enter your password to unlock it.
  4. Add the certificate to a keychain: I added my own certificates to the login keychain, not the System keychain. But if you want to trust the certificates for others users of the mac you should add it to System keychain.
  5. Click &#8220;Always Trust,&#8221; even though this doesn&#8217;t seem to do anything. And type your OSX user password.

[<img class="alignnone size-medium wp-image-1050" src="http://www.renedohmen.nl/blog/wp-content/uploads/2014/08/Schermafbeelding-2014-08-30-om-00.40.57-300x190.png" alt="Schermafbeelding 2014-08-30 om 00.40.57" width="300" height="190" />](http://www.renedohmen.nl/blog/wp-content/uploads/2014/08/Schermafbeelding-2014-08-30-om-00.40.57.png)

That&#8217;s it! Close Keychain Access and restart Chrome, and your self-signed certificate should be recognized now by the browser. Warning: it will only work for certificates that have a correct hostname.