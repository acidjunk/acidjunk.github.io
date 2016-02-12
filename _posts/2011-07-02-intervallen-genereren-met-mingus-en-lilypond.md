---
id: 193
title: Intervallen genereren met mingus en lilypond
date: 2011-07-02T16:36:00+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=193
permalink: /2011/07/intervallen-genereren-met-mingus-en-lilypond/
categories:
  - Computerz
  - Muziek
tags:
  - Computer
  - Lilypond
  - Mingus
  - Muziek
  - Python
---
Voor een music elearning project zijn we bezig met een theorie module. Omdat de theorie module veel standaard notenvoorbeelden zal bevatten hebben we eerst een generator geschreven voor toonladders. Dat werkt als volgt; je vult een toonladder in met lilypond notatie -> geeft aan dat ie voor alle toonsoorten gebruikt kan worden en een python script rendert vervolgens de toonladders naar .png bestanden die gebruikt kunnen worden in de theorie module. Tijdens het omzetten naar .ly (lilypond bestanden) wordt er ook een midifile gemaakt die vervolgens door timidity wordt omgezet naar .wav zodat de oefeningen niet alleen qau notenvoorbeeld bekeken kunnen worden maar ook afgespeeld zodat je een idee hebt hoe e.e.a. klinkt.

We hebben ook een aantal python scripts gemaakt die gebruikt kunnen worden om een hele set intervallen te genereren voldoende aan instelbare eisen. Hier is ondertussen ook een akkoord variant van.

De rest van het platform is geheel webbased en kan nu al helemaal gebruikt worden voor het invoeren van algemene muziek theorie vragen en examens. Hieronder een aantal screenshots van hoe het eruit ziet.

[<img class="alignnone size-full wp-image-213" title="Schermafbeelding 2011-07-02 om 18.04.30" src="http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-02-om-18.04.30.png" alt="" width="774" height="353" />](http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-02-om-18.04.30.png)

[<img class="alignnone size-full wp-image-214" title="Schermafbeelding 2011-07-02 om 18.04.48" src="http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-02-om-18.04.48.png" alt="" width="463" height="449" />](http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-02-om-18.04.48.png)

&nbsp;

[<img class="alignnone size-full wp-image-215" title="Schermafbeelding 2011-07-02 om 18.05.21" src="http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-02-om-18.05.21.png" alt="" width="396" height="336" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-02-om-18.05.21-300x254.png 300w, http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-02-om-18.05.21.png 396w" sizes="(max-width: 396px) 100vw, 396px" />](http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-02-om-18.05.21.png)

&nbsp;

[<img class="alignnone size-full wp-image-216" title="Schermafbeelding 2011-07-02 om 18.05.47" src="http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-02-om-18.05.47.png" alt="" width="816" height="491" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-02-om-18.05.47-300x180.png 300w, http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-02-om-18.05.47.png 816w" sizes="(max-width: 816px) 100vw, 816px" />](http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-02-om-18.05.47.png)

&nbsp;

**Note editor
  
** Ook hebben we een noteeditor die, geheel zonder extra plugins in de browser, gebruikt kan worden om notenschrift in te voeren mocht de bibliotheek met standaard materiaal hierin niet voorzien.

[<img class="alignnone size-full wp-image-217" title="Schermafbeelding 2011-07-02 om 18.08.42" src="http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-02-om-18.08.42.png" alt="" width="701" height="463" srcset="http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-02-om-18.08.42-300x198.png 300w, http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-02-om-18.08.42.png 701w" sizes="(max-width: 701px) 100vw, 701px" />](http://www.renedohmen.nl/blog/wp-content/uploads/2011/07/Schermafbeelding-2011-07-02-om-18.08.42.png)