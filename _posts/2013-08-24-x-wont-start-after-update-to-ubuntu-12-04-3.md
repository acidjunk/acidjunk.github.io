---
id: 856
title: 'Fixed: X won&#8217;t start after update to Ubuntu 12.04.3'
date: 2013-08-24T19:07:54+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=856
permalink: /2013/08/x-wont-start-after-update-to-ubuntu-12-04-3/
categories:
  - Computerz
---
I&#8217;m running a dual-screen set-up and need the proprietary drivers because the standard ones won&#8217;t drive the second screen at full resolution.

After updating to 12.0.4.3, xserver/gdm/lightdm won&#8217;t load at all. So only console login is left.

It appears they&#8217;ve messed up your kernel module configuration by installing both an upstream Nvidia driver as well as one from the Ubuntu repositories.

Now the &#8220;userland&#8221; Xorg libraries don&#8217;t match the version of the kernel module and that&#8217;s what you&#8217;re seeing here in the Xorg error logs. I&#8217;ll describe the steps to take in order to get a graphical login again.

  1. Uninstall the manually installed Nvidia driver. Refer to one of the many questions on this, e.g. 
    [How to uninstall manually installed Nvidia drivers?](http://askubuntu.com/q/219942/88802)</li> 
    
      * Uninstall all possible Ubuntu&#8217;s Nvidia packages: 
            sudo apt-get purge 'nvidia-*'
            
    
      * List and remove the Nvidia kernel modules still installed (if any) at this point: 
            dkms status
            dkms remove nvidia -k your-kernel-version-here
            
        
        _Repeat this until you see no Nvidia modules anymore using `dkms status`._</li> 
        
          * Install from the repositories: 
                sudo apt-get install nvidia-current nvidia-settings
                
            
            or if you need newer/recent versions:
            
                sudo apt-get install nvidia-current-updates nvidia-settings-updates
                
        
          * Verify that the Nvidia kernel driver is build for your running kernel: 
                dkms status | grep `uname -r`
                
            
            should produce e.g. `nvidia-304-updates, 304.88, 3.2.0-52-generic-pae, i686: installed`.</li> 
            
              * Reboot.</ol>