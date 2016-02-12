---
id: 471
title: Building Fancy DMG Images on Mac OS X
date: 2012-04-01T02:17:34+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=471
permalink: /2012/04/building-fancy-dmg-images-on-mac-os-x/
categories:
  - Computerz
---
**Creating the template <img src="http://www.renedohmen.nl/blog/wp-includes/images/smilies/simple-smile.png" alt=":-)" class="wp-smiley" style="height: 1em; max-height: 1em;" />**
  
First, we&#8217;ll start by specifying how our disk image should look when it is mounted (and opened). If you don&#8217;t need a fancy look, you can skip this section; the Makefile provided at the end of the page will automatically create a default template if you don&#8217;t create one yourself. Of course it&#8217;s weird to want fancy disk images but when used for a while it&#8217;s quite a relief. It&#8217;s just a unix mounted folder.

I could explain how to intstall Mac OSX applications to a first time mac user in 10 seconds: Drag the cool shiny applications icon to the Applications folder with the little arrow in it 0-). That&#8217;s it. If and old version of the application exists you will get a prompt asking if you want to update, use both or cancel the &#8220;app install&#8221;.

**[<img title="Schermafbeelding 2012-04-01 om 04.09.54" src="http://www.renedohmen.nl/blog/wp-content/uploads/2012/04/Schermafbeelding-2012-04-01-om-04.09.54.png" alt="" width="351" height="200" />](http://www.renedohmen.nl/blog/wp-content/uploads/2012/04/Schermafbeelding-2012-04-01-om-04.09.54.png)**

So fancy disk images is a nice thing to do for most of your application users; here we go:

  1. Using Disk Utility (which comes with Mac OS X), create a new disk image, and call it InstallerTemplate.dmg. Select a size which is more than enough to store the contents you plan to put in the final DMG. The Encryption and Format settings (None and r/w respectively) should be left untouched. Then, create your image by clicking Create.
  2. Open the newly created image.
  3. From the View menu of Finder, choose Show, View Options. You can now customize the way your folder will look. Be careful, don&#8217;t forget to select &#8220;this window&#8221; only, such that your changes will only apply to the current folder. Using the View menu, you can change the looks of the window even further. Also note that, if you choose a background picture, the picture file must reside in the image itself. It is common to create a (hidden) directory .background in the root dir of the image, dropping the background picture there, and then selecting it as a background. Use Cmd-Shift-G in combination with the full path (e.g. /Volumes/InstallerTemplate/.background) to open the hidden directory in Finder and copy your picture there (or, alternatively, use Terminal). The select button in the View menu seems to open the .background dir by default if it exists. If not, also use Cmd-Shift-G. This was a cool &#8220;wow, prffp, zop -> I didn&#8217;t know the Cmd-Shift-G keycombo to get to hidden linux folders in MAC OS X the graphical way, which proves to be quite handy when using a mac/linux hybrid :-)&#8221;
  4. Drag all your .app files you want in your image into the volume, and place them exactly where you want to. So in our case we use our .app folder from the build an just copy it into the mounted templateInstaller folder. Assign icons to the files by control- clicking on the icons, and using the Show Info dialog. If your using a .app your icons and you use .plist file with an icon location the icon should already appear by itself.
  5. Customize the icon of the disk image in the same way as the other icons, only this time by control-clicking on the disk image icon on the desktop.
  6. Eject the disk image.

you could want to compress it using bzip2. This is not strictly necessary, but if you created an initial disk size of 256M, using bzip2 you can reduce this to only a couples of Mb&#8217;s
  
If all went well, you should now have a InstallerTemplate.dmg(.bz2) which, when you open it, has a custom icon on the desktop, and looks exactly how you would like the final disk image to be. Now all we need to do is fill it up with the right files.

**Building the final DMG**
  
The easiest way to create a final DMG is by doing it by hand. All you have to do:

  1. Open Disk Utility (in Dutch version of OS  X look for &#8220;Schijfhulpprogramma&#8221;)
  2. Select the image you created in the previous step : InstallerTemplate.dmg
  3. Select Convert&#8230; from the Images menu
  4. Enter the name you want your final image to get
  5. Select Compressed as your Image Format
  6. Click Save

That&#8217;s it, your final DMG should be ready for distribution. Other mac users just have to double click it; and drag the application icon to the other icon.

**
  
**