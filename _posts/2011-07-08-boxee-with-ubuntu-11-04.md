---
id: 253
title: Boxee with Ubuntu 11.04
date: 2011-07-08T22:46:57+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=253
permalink: /2011/07/boxee-with-ubuntu-11-04/
categories:
  - Computerz
---
<div>
  The Ubuntu package for the current version of Boxee as of this writing, 0.9.22.13692M, does not install on the latest version of Ubuntu.  It throws an error &#8220;Dependency is not satisfiable: libxmlrpc-c3&#8221;  The problem arises because libxmlrpc-c3 has been renamed to libxmlprc-c3-0.  The solution is to modify the debian package and change its dependencies.  This is easier than it sounds, but you have to know how.  Download the debian installer from the Boxee website, and place it in your home directory and then open up a terminal.
</div>

> dpkg-deb -x boxee-0.9.22.13692.i486.modfied.deb boxee
  
> dpkg-deb &#8211;control boxee-0.9.22.13692.i486.modfied.deb
  
> cp -r DEBIAN boxee/

<div>
  Now we need to edit the file that lists the dependencies.  Run the first command to do it with a GUI, or the second to use vim.
</div>

> gedit boxee/DEBIAN/control
  
> vi boxee/DEBIAN/control

<div>
  Find libxmlrpc-c3 in this file and append -0 to the end of it and save the file.  Now we need to repackage our changes into a new debian package file.
</div>

> dpkg -b boxee boxee-works.deb

<div>
  When it is done simply double-click the newly created boxee-works.deb file and install it with Software Center.
</div>

<div>
  <a href="http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafdruk-Ubuntu-softwarecentrum.png"><img class="alignnone size-full wp-image-255" title="Schermafdruk-Ubuntu softwarecentrum" src="http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafdruk-Ubuntu-softwarecentrum.png" alt="" width="606" height="506" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafdruk-Ubuntu-softwarecentrum-300x250.png 300w, http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafdruk-Ubuntu-softwarecentrum.png 606w" sizes="(max-width: 606px) 100vw, 606px" /></a>
</div>

<div>
</div>