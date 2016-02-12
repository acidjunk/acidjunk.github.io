---
id: 490
title: Moving a phpBB to another domain
date: 2012-02-29T21:51:23+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=490
permalink: /2012/02/moving-a-phpbb-to-another-domain/
categories:
  - Computerz
---
This small guide explains the actions and steps to move a phpBB (php based forum software) to another domain with all setting and boards intact.

Most of the steps are described very detailed at <http://www.phpbb.com/kb/article/transferring-your-board-to-a-new-host-or-domain/>

**Step 1**

****Make sure de domain force settings are disabled:
  
Visit your old board’s Administration Control Panel. On the General tab, select the Server settings link on the left-hand side of the page. Ensure Force server URL settings is set to NO.

[<img class="alignnone size-full wp-image-491" title="1" src="http://www.renedohmen.nl/blog/wp-content/uploads/2012/02/1.png" alt="" width="473" height="76" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2012/02/1-300x48.png 300w, http://www.renedohmen.nl/blog/wp-content/uploads/2012/02/1.png 473w" sizes="(max-width: 473px) 100vw, 473px" />](http://www.renedohmen.nl/blog/wp-content/uploads/2012/02/1.png)

Then disable the forum for the moment, to make sure that no new posts etc are done while transferring the stuff to the new domain:
  
Select the Board settings link on the left-hand side of the page. Ensure Disable board is set toYES.

[<img class="alignnone size-full wp-image-492" title="2" src="http://www.renedohmen.nl/blog/wp-content/uploads/2012/02/2.png" alt="" width="494" height="81" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2012/02/2-300x49.png 300w, http://www.renedohmen.nl/blog/wp-content/uploads/2012/02/2.png 494w" sizes="(max-width: 494px) 100vw, 494px" />](http://www.renedohmen.nl/blog/wp-content/uploads/2012/02/2.png)

**Step 2**

Download the complete forum from the old host to a temporary folder. Then  upload the temporary folder to the new location. A couple of folders should have write access: store, files, cache and images/avatars/upload/

**Step 3**

Download the mysql database from the old forum and upload it to the new host.

**Step 4**

Rebuilding the conf file: in this case it&#8217;s simple just use the old config file and change DB settings to the new DB settings provided by your hosting company and upload it to the new host.

**Step 5**

If you are lucky you can now login to the forum on the new host. Try to login as administrator and go to the ACP. If this works, consider yourself lucky  <img src="http://www.renedohmen.nl/blog/wp-includes/images/smilies/simple-smile.png" alt=":-)" class="wp-smiley" style="height: 1em; max-height: 1em;" />After some celebration navigate to Cookie setting in the General tab. Make sure that the Cookie domain is set to your domain. Then everything should work. If you run in to troubles with the cookie method you can find more info here: http://www.phpbb.com/kb/article/fixing-incorrect-cookie-settings/

**Step 6**

enable your forum again

That&#8217;s it; your forum should be up and running on the new location now.