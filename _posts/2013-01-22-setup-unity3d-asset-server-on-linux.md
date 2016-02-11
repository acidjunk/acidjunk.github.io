---
id: 723
title: Setup Unity3d asset server on Linux
date: 2013-01-22T21:15:13+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=723
permalink: /2013/01/setup-unity3d-asset-server-on-linux/
categories:
  - Computerz
---
Working in a team on a Unity3d project with the Free and even the Pro version is almost impossible. We tried several methods involving GIT and complex .gitignore files but it&#8217;s all to complicated in the dynamic environment that we like to call work; It&#8217;s very easy to screw up.

So you&#8217;ll need an asset server license; Then Unity3D suddenly has a nice version control thingie <img src="http://www.renedohmen.nl/blog/wp-includes/images/smilies/simple-smile.png" alt=":-)" class="wp-smiley" style="height: 1em; max-height: 1em;" />

#### For users

You can find the asset server settings via the Windows, Asset Server option. Just make a new project and the set up your asset server connectoion. The easiest way is to login first, then click the &#8220;Show Projects&#8221; button. Click on the project en choose connect.

<a href="http://www.renedohmen.nl/blog/2013/01/setup-unity3d-asset-server-on-linux/asset-server1/" rel="attachment wp-att-741"><img class="alignnone size-full wp-image-741" alt="asset server1" src="http://www.renedohmen.nl/blog/wp-content/uploads/2013/01/asset-server1.png" width="607" height="294" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2013/01/asset-server1-300x145.png 300w, http://www.renedohmen.nl/blog/wp-content/uploads/2013/01/asset-server1.png 607w" sizes="(max-width: 607px) 100vw, 607px" /></a>

#### For administrators

I&#8217;ll describe how to set up the server and the steps involved to get the first clients in.
  
The server package is very straight forward-> on linux it&#8217;s a .rpm or a .deb: Install it

**RPM based OS:**

<pre>sudo rpm -Uvh http://download.unity3d.com/asset_server/unity_asset_server-2.0.1.i386.rpm</pre>

If this is a new installation, you will also have to supply an initial password for the admin user:

<pre>sudo /opt/unity_asset_server/bin/reset_admin_password</pre>

**DEB based OS:**

<pre>wget http://download.unity3d.com/asset_server/unity-asset-server_2.0.1_i386.deb
sudo dpkg -i unity-asset-server_2.0.1_i386.deb</pre>

Same password instructions as above.

#### 

#### History

Moving of scenes and assets did lead to conflicts. So a little planning of project structure is needed. The cool thing about the version stuff is that it integrates into the workflow. When you tried it there is no way back.
  
<a href="http://www.renedohmen.nl/blog/2013/01/setup-unity3d-asset-server-on-linux/schermafbeelding-2013-01-22-om-19-38-52/" rel="attachment wp-att-739"><img class="alignnone size-medium wp-image-739" alt="Asset history" src="http://www.renedohmen.nl/blog/wp-content/uploads/2013/01/Schermafbeelding-2013-01-22-om-19.38.52-295x300.png" width="295" height="300" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2013/01/Schermafbeelding-2013-01-22-om-19.38.52-295x300.png 295w, http://www.renedohmen.nl/blog/wp-content/uploads/2013/01/Schermafbeelding-2013-01-22-om-19.38.52.png 332w" sizes="(max-width: 295px) 100vw, 295px" /></a>