---
id: 199
title: ImageMagick for batch processing images
date: 2011-06-14T19:53:42+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=199
permalink: /2011/06/imagemagick-for-batch-processing-images/
categories:
  - Computerz
---
Imagemagick is the ideal tool to scale, convert or crop a lot of images. The last version of Imagemagick support construction with * to work with a lot of images. But if your images are scattered over a lot of folders and subfolder you need another construction:

The next command will convert al jpg to new jpg with 75% quality, the maxdepth options specifies how much subfolders it will do:

<pre>find . -maxdepth 1 -name '*.jpg' -print0 | xargs -0 -I {} convert -quality 75 {} \
/tmp/thumbs/{}</pre>

To compress and resize inplace:

NOTE! Mogrify is a dangerous command because it operates on the original files! Test your commands on COPIES of your files.

<pre>find . -maxdepth 1 -name '*.jpg' -print0 | xargs -0 mogrify -resize 800x600 -quality 75</pre>

To change file types:

<pre>find . -maxdepth 1 -name '*.jpg' -print0 | xargs -0 mogrify -format png</pre>

_The above statement will leave the original JPG files alone, and write PNGs beside them._

Same from png -> jpg with scaling 50% applied:

<pre>find . -maxdepth 1 -name '*.png' -print0 | xargs -0 mogrify -quality 80 -scale 50% \
-format jpg</pre>

_The above statement will leave the original PNG files alone, and write JPGs beside them._

<div>
  <em><br /> </em>
</div>