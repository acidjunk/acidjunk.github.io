---
title: Clean up bootpartition on Ubuntu 
subtitle: Howto to clean up a boot partition on Ubuntu 14.04
date: 2016-04-18
author: acidjunk
layout: post
permalink: /2016/02/clean-up-full-bootpartition-on-ubuntu1404
categories:
  - Computerz
header-img: "img/post-bg-02.jpg"
comments: true
---
# The symptom
If apt-get isn't functioning because your /boot is at 100%, you'll need to clean out /boot first. This likely has caught a kernel upgrade in a partial install which means apt has pretty much froze up entirely and will keep telling you to run apt-get -f install even though that command keeps failing.

# The cause
With a small boot partition and UnAttended upgardes on; a


# The solution
Warning: only use this way of cleaning the boot partition when you tried to solve it first with apt-get itself: e.g. `sudo dpkg --list 'linux-image*'` and then delete unneeded kernels with: `sudo apt-get remove linux-image-VERSION` replacing VERSION with the linux kernel versions you want to remove.
If that yields an error like: 
`dpkg: dependency problems prevent removal of linux-image-3.13.0-79-generic: linux-image-extra-3.13.0-79-generic depends on linux-image-3.13.0-79-generic. dpkg: error processing package linux-image-3.13.0-79-generic (--purge): dependency problems - not removing Errors were encountered while processing: linux-image-3.13.0-79-generic`
This solution is for you:

## List kernels that you can remove
Get the list of kernel images and determine what you can do without. The next command will list all installed kernels . 
```
sudo dpkg --list 'linux-image*'|awk '{ if ($1=="ii") print $2}'|grep -v `uname -r`
```

## Remove unneeded/unwanted kernels
Craft a command to delete all files in /boot for kernels that don't matter to you using brace expansion to keep you sane. Remember to exclude the current and two newest kernel images. Example: 
`sudo rm -rf /boot/*-3.13.0-{68,70,71,72,73}-*.`

## Fix apt
sudo apt-get -f install to clean up what's making apt grumpy about a partial install.

If you run into an error that includes a line like "Internal Error: Could not find image (/boot/vmlinuz-3.13.0-68-generic)", then run the command sudo apt-get purge linux-image-3.13.0-68-generic (with your appropriate version).

Finally, sudo apt-get autoremove to clear out the old kernel image packages that have been orphaned by the manual boot clean.

## Install updates/upgrades
Optionally: run `sudo apt-get update` and `sudo apt-get upgrade` to take care of any upgrades that may have backed up while waiting for you to discover the full /boot partition.

# Eliminating the root cause
You can uncomment an option in `/etc/apt/apt.conf.d/50unattended-upgrades`:
Look for this line:

```
// Do automatic removal of new unused dependencies after the upgrade
// (equivalent to apt-get autoremove)
Unattended-Upgrade::Remove-Unused-Dependencies "true";
```

Then apt-get autoremove is executed after each unattended upgrade.

# The alternative
Someone
https://github.com/EvanK/ubuntu-purge-kernels
