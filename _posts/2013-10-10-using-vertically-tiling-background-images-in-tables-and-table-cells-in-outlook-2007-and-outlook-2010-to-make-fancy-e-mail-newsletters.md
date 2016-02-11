---
id: 892
title: Using vertically tiling background images for tables and tables cells in outlook 2007 and outlook 2010 to make fancy e-mail newsletters
date: 2013-10-10T18:54:35+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=892
permalink: /2013/10/using-vertically-tiling-background-images-in-tables-and-table-cells-in-outlook-2007-and-outlook-2010-to-make-fancy-e-mail-newsletters/
categories:
  - Computerz
---
After a whole day of searching the internet why tiling background won&#8217;t show up in a e-mail template when viewing the mail in Outlook 2007 or Outlook 2010 I finally found the answer on [stackoverflow](http://stackoverflow.com/questions/13335043/repeating-background-image-in-outlook-2007-2010-2013-and-gmail).

The funny thing is that repeating background work in Outlook 2003, Outlook 2000, Gmail and in all the other e-mail clients that we test our mailinglist templates with. Although it seems that background images don&#8217;t work in Lotus Notes; is somebody still using this? 😉

We did test a big scala of approaches; pictures in a div, inline styling, relative placement of transparant overlay, vxml hook with fixed size, size in percentages, etc.

The solution is actually quite easy. In the cell that opens your current background shizzle add:

<pre class="prettyprint">&lt;!--[if gte mso 9]&gt;
&lt;v:rect xmlns:v="urn:schemas-microsoft-com:vml" fill="true" stroke="false" style="width: 200px;"&gt;
&lt;v:fill type="tile" src="http://www.formatics.nl/yourbackground.png" color="#f6f6f6" /&gt;
&lt;v:textbox style="mso-fit-shape-to-text: true;" inset="0,0,0,0"&gt;
&lt;![endif]--&gt;
</pre>

Then at the end of the cell, where you want your background to stop:

<pre class="prettyprint">&lt;!--[if gte mso 9]&gt;
&lt;p style="margin:0;mso-hide:all"&gt;&lt;o:p xmlns:o="urn:schemas-microsoft-com:office:office"&gt;&nbsp;&lt;/o:p&gt;&lt;/p&gt;
   &lt;/v:textbox&gt;
&lt;/v:rect&gt;
&lt;![endif]--&gt;
</pre>

You can find an easy complete example on stack overflow, copy pasteable:

<pre class="prettyprint">&lt;html xmlns:v="urn:schemas-microsoft-com:vml"&gt;
&lt;head&gt;
    &lt;meta http-equiv="Content-Type" content="text/html; charset=utf-8"&gt;
&lt;/head&gt;
&lt;body bgcolor="#FFFFFF"&gt;
&lt;table background="http://i.imgur.com/n8Q6f.png" cellpadding="0" cellspacing="0" width="200"&gt;
    &lt;tr&gt;
        &lt;td&gt;
          &lt;!--[if gte mso 9]&gt;
          &lt;v:rect xmlns:v="urn:schemas-microsoft-com:vml" fill="true" stroke="false" style="width: 200px;"&gt;
            &lt;v:fill type="tile" src="http://i.imgur.com/n8Q6f.png" color="#f6f6f6" /&gt;
            &lt;v:textbox style="mso-fit-shape-to-text: true;" inset="0,0,0,0"&gt;
          &lt;![endif]--&gt;
                &lt;table border="0" cellpadding="0" cellspacing="0"&gt;
                    &lt;tr&gt;
                        &lt;td width="100"&gt;&lt;/td&gt;
                        &lt;td bgcolor="#ffffff" width="100"&gt;
                        The&lt;br/&gt;
                        background&lt;br/&gt;
                        image&lt;br/&gt;
                        on&lt;br/&gt;
                        the&lt;br/&gt;
                        left&lt;br/&gt;
                        will&lt;br/&gt;
                        stretch&lt;br/&gt;
                        to&lt;br/&gt;
                        the&lt;br/&gt;
                        height&lt;br/&gt;
                        of&lt;br/&gt;
                        this&lt;br/&gt;
                        content.
                        &lt;/td&gt;
                    &lt;/tr&gt;
                &lt;/table&gt;
          &lt;!--[if gte mso 9]&gt;
              &lt;p style="margin:0;mso-hide:all"&gt;&lt;o:p xmlns:o="urn:schemas-microsoft-com:office:office"&gt;&nbsp;&lt;/o:p&gt;&lt;/p&gt;
            &lt;/v:textbox&gt;
          &lt;/v:rect&gt;
          &lt;![endif]--&gt;
        &lt;/td&gt;
    &lt;/tr&gt;
&lt;/table&gt;
&lt;/body&gt;
&lt;/html&gt;
</pre>

We found some other weird issues/behaviours while testing our mail in some webclients like Gmail en Hotmail. Webmail clients can have line-height definitions that overrule line-heights! Outlook appears to skip background for table cells completely; so we often use a table cell containing an img element and a background image for the cell. Gmail and other clients will load the background; Outlook 2007 en Outlook 2010 will load the image element. This can get you in problems when content pushes the height of the cell above the image element height. You will get missing gaps in the content.

The problem: The browser already has previous line-height definitions from rendering the Gmail layout; it will/can apply this line-height on your cells. To avoid this we sometimes apply a fixed line-height to &#8220;design cells&#8221;.

An example:

<pre class="prettyprint">&lt;td bgcolor="#2caae1" height="10" width="600" colspan="3" background="http://i.imgur.com/n8Q6f.png" valign="bottom" style="background-image: url(http://i.imgur.com/n8Q6f.png); background-position: top; line-height: 71%;"&gt;
     &lt;img src="http://i.imgur.com/n8Q6f.png" border="0" height="10" width="600"&gt;
&lt;/td&gt;
</pre>

In Hotmail, Outlook.com and Gmail: it would create a table cell with height=18 instead of the wanted and expected 10. The style=&#8221;line-height: 71%;&#8221; will, forcefully correct that. Better suggestions are welcome.