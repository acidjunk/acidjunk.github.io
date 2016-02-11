---
id: 230
title: N7 netwerk tuner bekijken via Boxee
date: 2011-07-07T17:31:38+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=230
permalink: /2011/07/n7-netwerk-tuner-bekijken-via-boxee/
categories:
  - Computerz
---
We zijn bezig aan een app voor het [boxee](http://www.boxee.tv/) platform zodat je ook TV kan kijken via de netwerktuner [N7 van Anysee](http://www.anysee.com/eng/product/anyseeN7TC.php). Standaard ondersteunt Boxee (zover ik kan zien) geen .m3u bestanden. Nadat ik de tuner geconfigureerd had en de playlist had opgeslagen speelde de tuner direct al via bijvobeeld VLC perfect TV af. Kwaliteit is goed te  noemen, maar ik alleen nog met digitenne getest.

Omdat ik nergens in boxee de mogelijkheid zag om zelf een losse stream door te geven ben ik maar eens wat gaan zoeken in Google. Bijna alle apps gebruiken een rss bestand voor het aangeven van medialocaties en metabeschrijvingen hiervan.

Na zelf m.b.v. de Boxee RSS specs een RSS bestand gemaakt te hebben met een paar van de teststreams van de N7 was ik klaar om testen. Ik heb de app My RSS Reader gebruikt om het snel even te testen. Helaas moet je dan wel je RSS bestand op een webserver zetten die via internet te bereiken is. Lokaal wou die het niet laden. Na wat gespit in de logfiles was dit snel duidelijk.

Gebruikte test stream: (werkt alleen als je N7 streamer via 192.168.5.128 te bereiken is.)
  
http://www.formatics.nl/test.rss

[<img class="alignnone size-full wp-image-237" title="Schermafbeelding 2011-07-07 om 18.56.37" src="http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-07-om-18.56.37.png" alt="" width="678" height="380" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-07-om-18.56.37-300x168.png 300w, http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-07-om-18.56.37.png 848w" sizes="(max-width: 678px) 100vw, 678px" />](http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-07-om-18.56.37.png)

[<img class="alignnone size-full wp-image-238" title="Schermafbeelding 2011-07-07 om 18.56.58" src="http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-07-om-18.56.58.png" alt="" width="537" height="115" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-07-om-18.56.58-300x64.png 300w, http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-07-om-18.56.58.png 537w" sizes="(max-width: 537px) 100vw, 537px" />](http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-07-om-18.56.58.png)

[<img class="alignnone size-full wp-image-239" title="Schermafbeelding 2011-07-07 om 18.57.25" src="http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-07-om-18.57.25.png" alt="" width="507" height="169" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-07-om-18.57.25-300x100.png 300w, http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-07-om-18.57.25.png 507w" sizes="(max-width: 507px) 100vw, 507px" />](http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-07-om-18.57.25.png)

[<img class="alignnone size-full wp-image-240" title="Schermafbeelding 2011-07-07 om 19.11.16" src="http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-07-om-19.11.16.png" alt="" width="678" height="378" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-07-om-19.11.16-300x167.png 300w, http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-07-om-19.11.16.png 847w" sizes="(max-width: 678px) 100vw, 678px" />](http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-07-om-19.11.16.png)

Om het geheel wat simpeler op een andere plek te kunnen gebruiken kun je ook dit gebruiken:

<a href="http://tv.formatics.nl/njoy.php?host=192.168.5.128" target="_blank">http://tv.formatics.nl/njoy.php?host=192.168.5.128</a>

<div>
  Bovenstaande link kun je natuurlijk alleen gebruiken als de N7 in je netwerk te vinden is onder 192.168.5.128
</div>

<div>
  (standaard poort: 8080)
</div>

<div>
  Andere poort meegeven kan ook
</div>

<div>
  <div>
    <a href="http://tv.formatics.nl/njoy.php?host=192.168.5.128&port=6000" target="_blank">http://tv.formatics.nl/njoy.php?host=192.168.5.128&port=6000</a>
  </div>
</div>

<div>
  Ik heb de TV stations nu met de hand toegevoegd; weet niet of het nog uitmaakt of je digitenne hebt of iets anders. En nu staat er alleen nog maar NL1-3
</div>

<div>
</div>

<div>
  Mocht iemand deze link gaan gebruiken en uitbreidingen weten; let me know.
</div>