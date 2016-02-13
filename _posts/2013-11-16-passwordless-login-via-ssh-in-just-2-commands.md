---
id: 950
title: Passwordless login via ssh in just 2 commands!
date: 2013-11-16T20:00:44+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=950
permalink: /2013/11/passwordless-login-via-ssh-in-just-2-commands/
categories:
  - Computerz
header-img: "img/post-bg-01.jpg"
---
I already wrote some earlier posts on this topic; but I found a new command: ssh-copy-id; it&#8217;s brilliant.

First create your SSH Keypair by running ssh-keygen this will create an id\_rsa and id\_rsa.pub file. The pub file is what goes on the servers, the private key (id_rsa) is what stays with you and is how you identify yourself.

Next copy the public key to your server with ssh-copy-id user@server replacing user with your remote user and server with the machine DNS name or IP address. It&#8217;ll prompt for your SSH password, enter it and if all completes successfully you&#8217;ll be able to access the machine via ssh user@server without needing a password.

<pre>ssh-keygen
ssh-copy-id user@server
</pre>

It will create a authorized_keys if needed; or add an entry to it.