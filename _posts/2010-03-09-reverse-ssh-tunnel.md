---
id: 40
title: Reverse SSH tunnel
date: 2010-03-09T21:46:58+00:00
author: acidjunk
layout: inner
guid: http://www.renedohmen.nl/blog/?p=40
permalink: /2010/03/reverse-ssh-tunnel/
categories:
  - Computerz
---
Als linux guru wil je graag per SSH van alles doen maar wat nou als de linux computer waar je op wil inloggen zich in een ander netwerk bevind, achter een router/firewall? De oplossing is het gebruik van een reverse SSH tunnel. Je laat de andere computer dan een data connectie opzetten naar een computer op internet vervolgens kun je vanf die computer inloggen via deze dataconnectie (tunnel).

Anyway: mooie theorie, maar ik vergeet natuurlijk steeds het commando, en dat is ook niet raar gezien de syntax; komt ie:

ssh -nNT -R 5000:lokalebak:22 usernaam@internetserver.com

Nu kun je als ingelogd bent op internetserver.com via de SSH tunnel een connectie terug maken met:

ssh -p5000 localhost

Een soort ad hoc VPN dus; dit is een echte lifesaver, want dit scheelt je vaak een reis naar de klant.