---
id: 462
title: As a reminder for myself, the command line options of mc2xml
date: 2012-01-28T19:54:48+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=462
permalink: /2012/01/as-a-reminder-for-myself-the-command-line-options-of-mc2xml/
categories:
  - Computerz
---
mc2xml is a small and fast standalone command line program for Windows/Linux/OSX that downloads media center, titantv, or schedules direct tv listings and outputs an XMLTV formatted (xmltv.dtd) .xml file.
  
mc2xml options (case sensitive):
    
-a append &#8221; *&#8221; to new programs
    
-A append &#8221; *&#8221; to live programs
    
-F output channel &#8220;name&#8221; first (rather than &#8220;number name&#8221;)
    
-L include <live /> tag (not part of xmltv.dtd)
    
-u output date/time in UTC (default = localtime)
    
-U output UTF-8 (default = &#8220;ISO-8859-1&#8221;)
    
-f force re-download (use with caution)
    
-d <#> set listings duration (in hours)
    
-s <[+/-]#> set listings relative start position (in hours)
    
-c         set country code<br />
  -g <code>        set postal/zip code<br />
  -w <seconds>     wait for <seconds> and exit<br />
  -t               use titantv service<br />
  -y <id>          set 30 char id for titantv service<br />
  -T <user>:<pass> use schedules direct service<br />
  -i <#>           add <#> to all channel numbers<br />
  -I <xmltv file>  include <xmltv file> in output<br />
  -R <filename>    set ren filename (default = "mc2xml.ren")<br />
  -D <filename>    set dat filename (default = "mc2xml.dat")<br />
  -C <filename>    set channel file (default = "mc2xml.chl")<br />
  -o <filename>    set output file  (default = "xmltv.xml")</p>
<p>mc2xml quickstart: (see also: FAQ: nextpvr, mythtv, mediaportal, ...) </p>
<p>Windows:</p>
<p>Run "mc2xml", it has a simple graphical user interface<br />
Input postal code and country code and press OK<br />
Select lineup number from the returned list and an xmltv.xml file will be produced</p>
<p>Other OSs and command line usage:</p>
<p>Run mc2xml with both the -c and -g parameters to set your location </p>
<p>-t is optional, and only works for US zipcodes<br />
-T is optional, and requires an account user:pass (-c & -g are not needed)<br />
-U is required for languages that contain non ISO-8859-1 characters</p>
<p>Select lineup number from the returned list and an xmltv.xml file will be produced</p>
<p>mc2xml setup examples:</p>
<p>US: mc2xml -c us -g 20006<br />
US: mc2xml -c us -g 20006 -t -y <id><br />
CA: mc2xml -c ca -g M1N2K3 </p>
<p>AT: mc2xml -c at -g 1000<br />
BE: mc2xml -c be -g 1000<br />
BR: mc2xml -c br -g 20010-020<br />
CH: mc2xml -c ch -g 1000<br />
CZ: mc2xml -c cz -g "100 10"<br />
DE: mc2xml -c de -g 10000<br />
DK: mc2xml -c dk -g 1000<br />
ES: mc2xml -c es -g 28000<br />
FI: mc2xml -c fi -g 10000<br />
FR: mc2xml -c fr -g 10000<br />
IE: mc2xml -c ie -g 0<br />
IL: mc2xml -c il -g 10000 -U<br />
IN: mc2xml -c in -g 110000<br />
IT: mc2xml -c it -g 00100<br />
JP: mc2xml -c jp -g 1028000 -U<br />
KR: mc2xml -c kr -g 100 -U<br />
MX: mc2xml -c mx -g 22440<br />
NL: mc2xml -c nl -g 1000<br />
NO: mc2xml -c no -g 1000<br />
PL: mc2xml -c pl -g 11-111<br />
PT: mc2xml -c pt -g 1000<br />
RU: mc2xml -c ru -g 101000 -U<br />
SE: mc2xml -c se -g "100 10"<br />
SK: mc2xml -c sk -g "100 10"<br />
TR: mc2xml -c tr -g 01000 -U<br />
TW: mc2xml -c tw -g 10000 -U<br />
UK: mc2xml -c gb -g "SW1X 7LA"</p>