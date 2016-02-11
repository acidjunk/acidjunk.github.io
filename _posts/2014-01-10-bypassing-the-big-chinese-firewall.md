---
id: 961
title: Bypassing the big Chinese firewall
date: 2014-01-10T21:52:58+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=961
permalink: /2014/01/bypassing-the-big-chinese-firewall/
categories:
  - Computerz
---
I made a couple of preparations to make sure I could use internet in China in a reliable way. I did some investigations on fora to find out what possible problems it could expect. Due to the new Google Profiles policy users seem to have problems with Google apps and Gmail login. Youtube and Facebook are impossible to use without some preparation. Downloading attachments in Gmail won&#8217;t work in a reliable way.

So I decided to install some OpenVPN addons on one of my pfsense firewalls, purchased a month&#8217;s license to BreakWall VPN Pro Pack Medium for a fallback and created some handy SSH scripts so I could use a SSH tunnel as a SOCK based webproxy. Here we go.

### BreakWall

Breakwall claims to give me access to Facebook an Youtube if my own VPN solution fails. http://blog.stefcho.eu/?p=492
  
I think you should only use this if you don&#8217;t have access to servers outside China.

### OpenVPN

Although ipsec is better OpenVPN is easier and very stable. With the coolness of pfsense you can configure it via a wizard.
  
[<img class="alignnone size-medium wp-image-964" alt="Schermafbeelding 2013-12-24 om 04.05.33" src="http://www.renedohmen.nl/blog/wp-content/uploads/2013/12/Schermafbeelding-2013-12-24-om-04.05.33-300x197.png" width="300" height="197" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2013/12/Schermafbeelding-2013-12-24-om-04.05.33-300x197.png 300w, http://www.renedohmen.nl/blog/wp-content/uploads/2013/12/Schermafbeelding-2013-12-24-om-04.05.33.png 584w" sizes="(max-width: 300px) 100vw, 300px" />](http://www.renedohmen.nl/blog/wp-content/uploads/2013/12/Schermafbeelding-2013-12-24-om-04.05.33.png)

It can be configured in 2 ways: normal OpenVPN and Redirect OpenVPN; the last one is ideal for this situation; it will, once it&#8217;s active, send all network traffic of your laptop or other internet device over the VPN tunnel so you can visit Youtube and Facebook from a dutch IP number. The problem with OpenVPN is that it can be detected. I did find some articles about VPN being illegal in China. I was able to use this in 80% of the cases.

### SSH Tunneling

SSH tunneling allows you to securely route traffic through a SSH server you own using an encrypted tunnel. SSH tunnels can be used to prevent network monitors on your local network from monitoring what sites you visit, or to bypass overly restrictive web filters. They are also useful for trackers that require users to log in from an IP before being able to seed from it. The nice thing about SSH tunnels is that the traffic looks almost the same as normal https traffic making it almost impossible to detect especially when connecting to a 443 port. It&#8217;s also easy to setup when you know what you are doing. SOCKS is built in to OpenSSH, so it&#8217;s a trivial matter to set up a local SOCKS proxy with the -D flag. For example

<pre>ssh -D 5222 user@myhomelinuxserver.com -N
</pre>

Or when using a non standard SSH port (to avoid script kiddies from brute force probing your port 22 all the time):

<pre>ssh -D 5222 -p 1234 user@myhomelinuxserver.com -N
</pre>

In Chrome you can use the excellent Falcon proxy extension to setup the SOCKS proxy; so you switch proxies fast:
  
[<img src="http://www.renedohmen.nl/blog/wp-content/uploads/2014/01/Screenshot-from-2014-01-10-223059-300x285.png" alt="Screenshot from 2014-01-10 22:30:59" width="300" height="285" class="alignnone size-medium wp-image-974" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2014/01/Screenshot-from-2014-01-10-223059-300x285.png 300w, http://www.renedohmen.nl/blog/wp-content/uploads/2014/01/Screenshot-from-2014-01-10-223059.png 388w" sizes="(max-width: 300px) 100vw, 300px" />](http://www.renedohmen.nl/blog/wp-content/uploads/2014/01/Screenshot-from-2014-01-10-223059.png)

In Firefox you can use the buildin proxy support with setting to manual:
  
[<img src="http://www.renedohmen.nl/blog/wp-content/uploads/2014/01/Screenshot-from-2014-01-10-223959-300x278.png" alt="Screenshot from 2014-01-10 22:39:59" width="300" height="278" class="alignnone size-medium wp-image-975" />](http://www.renedohmen.nl/blog/wp-content/uploads/2014/01/Screenshot-from-2014-01-10-223959.png)

For a more permanent setting you can use the systems settings for a proxy; at least this is working fine on Ubuntu:
  
[<img src="http://www.renedohmen.nl/blog/wp-content/uploads/2014/01/Screenshot-from-2014-01-10-223716-300x171.png" alt="Screenshot from 2014-01-10 22:37:16" width="300" height="171" class="alignnone size-medium wp-image-976" />](http://www.renedohmen.nl/blog/wp-content/uploads/2014/01/Screenshot-from-2014-01-10-223716.png)

### Conclusion

I didn&#8217;t need the BreakWall but if you don&#8217;t own any fancy VPN boxes outside of China; it&#8217;s would probably be the only way to have decent internet. The VPN solution is the easiest one; as it tunnels all traffic trough the VPN connection without further setup. The SSH tunnel is also very easy; but you need a good OS, and some SSH knowledge to get it going.