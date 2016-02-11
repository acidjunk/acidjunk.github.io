---
id: 559
title: Ubuntu landscape??
date: 2012-05-05T19:50:59+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=559
permalink: /2012/05/ubuntu-landscape/
categories:
  - Computerz
---
I did have a look at the specs of Canonical&#8217;s Landscape. If you want to manage a bunch of (different) Linux systems with one unified interface you can&#8217;t work around it . It works with profiles and tags. Systems matching the tag in the profile can be automatically updated.

[<img class="alignnone size-full wp-image-571" title="C3.2.2_03_manageinfo_medium" src="http://www.renedohmen.nl/blog/wp-content/uploads/2012/05/C3.2.2_03_manageinfo_medium.png" alt="" width="525" height="383" />](http://www.renedohmen.nl/blog/wp-content/uploads/2012/05/C3.2.2_03_manageinfo_medium.png)

More interesting features:

  * Manage many machines at once. All operations in Landscape can be applied to one or more machines with the same ease.
  * Group machines to match your needs. You can split machines into multiple groups for different requirements while still administering through a single interface.
  * Manage packages across the network. View a package inventory for each computer and use Landscape to install, upgrade or remove packages from one or more computers.
  * Integrate custom software repositories. If you maintain your own repository, even internally, Landscape can report on and use the packages in it.
  * The ability to run custom scripts on command across multiple computers.
  * Manage users easily. Users from one or more systems are easy to manage with Landscape.
  * Handle security updates efficiently. Landscape highlights those package upgrades with security fixes (with links to detailed information) ensuring any vulnerabilities are dealt with as quickly as possible.
  * Support disconnected systems. Systems that are disconnected from the network will be properly handled when they next get online.

It can also be used for system monitoring. Landscape monitors systems through an agent installed on each machine. The agent communicates with Landscape to provide live status information. Data is securely collected and stored in the Landscape database. Administrators can use the data for performance analysis. Landscape&#8217;s graphical module makes it easy to plot trends of temperature, disk and memory usage, system load or custom metrics.



It would be the perfect office OS when used with Ubuntu One. Ubuntu&#8217;s the personal cloud service that syncs your digital life Music, bookmarks, contacts, files between your laptop, netbook and work desktop.

## Let&#8217;s try it

### Registering a computer

Landscape lets you manage Ubuntu systems securely from any web browser. The machines you want to manage need to first be registered with Landscape. Depending on which version of Ubuntu the machine you want to register is running, the registration procedure varies slightly. Please follow the appropriate instructions below.

Registering a computer was very easy, it just involved running two commands client side, plugging in my credentials and letting Landscape do the rest:

<pre>sudo apt-get install landscape-client
sudo landscape-config --computer-title "My Web Server" --account-name youraccountname</pre>

Of course, this will only work if you have a Landscape account.

### Accept the computer

Now that the machine is registered as a pending computer it can be accepted into your account. Log into landscape with your user account information and click on the [Pending Computers](https://landscape.canonical.com/account/qiosq/pending-computers) link. Accept the pending thingie. Then you will see the machine you just registered, as illustrated in this screen shot:

[<img class="alignnone size-full wp-image-578" title="Schermafbeelding 2012-05-05 om 21.35.17" src="http://www.renedohmen.nl/blog/wp-content/uploads/2012/05/Schermafbeelding-2012-05-05-om-21.35.17.png" alt="" width="507" height="294" />](http://www.renedohmen.nl/blog/wp-content/uploads/2012/05/Schermafbeelding-2012-05-05-om-21.35.17.png) [<img class="alignnone size-full wp-image-577" title="Schermafbeelding 2012-05-05 om 21.35.45" src="http://www.renedohmen.nl/blog/wp-content/uploads/2012/05/Schermafbeelding-2012-05-05-om-21.35.45.png" alt="" width="524" height="182" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2012/05/Schermafbeelding-2012-05-05-om-21.35.45-300x104.png 300w, http://www.renedohmen.nl/blog/wp-content/uploads/2012/05/Schermafbeelding-2012-05-05-om-21.35.45.png 524w" sizes="(max-width: 524px) 100vw, 524px" />](http://www.renedohmen.nl/blog/wp-content/uploads/2012/05/Schermafbeelding-2012-05-05-om-21.35.45.png)

Installing packages is easy:

[<img class="alignnone size-full wp-image-576" title="Schermafbeelding 2012-05-05 om 21.24.51" src="http://www.renedohmen.nl/blog/wp-content/uploads/2012/05/Schermafbeelding-2012-05-05-om-21.24.51.png" alt="" width="624" height="445" />](http://www.renedohmen.nl/blog/wp-content/uploads/2012/05/Schermafbeelding-2012-05-05-om-21.24.51.png)

With scripts enabled you can even run custom scripts from the webGUI:

[<img class="alignnone size-full wp-image-575" title="Schermafbeelding 2012-05-05 om 21.20.46" src="http://www.renedohmen.nl/blog/wp-content/uploads/2012/05/Schermafbeelding-2012-05-05-om-21.20.46.png" alt="" width="646" height="630" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2012/05/Schermafbeelding-2012-05-05-om-21.20.46-300x292.png 300w, http://www.renedohmen.nl/blog/wp-content/uploads/2012/05/Schermafbeelding-2012-05-05-om-21.20.46.png 646w" sizes="(max-width: 646px) 100vw, 646px" />](http://www.renedohmen.nl/blog/wp-content/uploads/2012/05/Schermafbeelding-2012-05-05-om-21.20.46.png)

&nbsp;

&nbsp;