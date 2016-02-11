---
id: 622
title: A quick way to make a USB bootable Ubuntu on OSX.
date: 2012-11-16T18:42:38+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=622
permalink: /2012/11/a-quick-way-to-make-a-usb-bootable-ubuntu-on-osx/
categories:
  - Computerz
---
It&#8217;s quite a long time since my last post. Very busy on new projects as always and getting settled in the new house / office <img src="http://www.renedohmen.nl/blog/wp-includes/images/smilies/simple-smile.png" alt=":)" class="wp-smiley" style="height: 1em; max-height: 1em;" />

The next post is mostly copied from Ubuntu.com. But I see it as a quick reminder for my own Linux boot questions on mac. I keep forgetting the keys and command&#8217;s to work with diskimages. The created stick will be bootable for most comps not only macs!

Note: this procedure requires that you create an .img file from the .iso file you download.

  1. Convert the .iso file to .img using the convert option of hdiutil 
    <pre>hdiutil convert -format UDRW -o ubuntu1210_32.img ubuntu-12.10-desktop-i386.iso</pre>
    
    Note: OS X tends to put the .dmg ending on the output file automatically.</li> 
    
      * Run diskutil list to get the current list of devices.
      * Insert your flash media.
      * Run diskutil list again and determine the device node assigned to your flash media (e.g. /dev/disk2).
      * Unmount the disk so dd can do its work. Run diskutil unmountDisk /dev/diskN (replace N with the disk number from the last command; in the previous example, N would be 2). 
        <pre>diskutil unmountDisk /dev/disk2</pre>
        
        Note for the linux guys among us there is: $ diskutil unmount /dev/disk2s1</li> 
        
          * Overwrite contents of USB stick with the bootable Ubuntu image. Warning stick content will be lost. Execute sudo dd if=/path/to/downloaded.img of=/dev/rdiskN bs=1m 
            <pre>sudo dd if=ubuntu1204_32.img.dmg of=/dev/rdisk2 bs=1m</pre>
            
            Note: Using /dev/rdisk instead of /dev/disk may be faster</li> 
            
              * Run diskutil eject /dev/diskN and remove your flash media when the command completes. 
                <pre>diskutil eject /dev/disk2</pre>
            
              * Restart your Mac and press alt/option key while the Mac is restarting to choose the USB stick.
  
                (windows keyboard, windows key or alt)</ol>