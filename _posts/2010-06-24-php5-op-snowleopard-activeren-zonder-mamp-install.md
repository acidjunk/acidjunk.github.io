---
id: 61
title: PHP5 op snowleopard activeren, zonder MAMP install
date: 2010-06-24T22:00:14+00:00
author: acidjunk
layout: post
guid: http://www.renedohmen.nl/blog/?p=61
permalink: /2010/06/php5-op-snowleopard-activeren-zonder-mamp-install/
categories:
  - Computerz
---
De installatie van een Apache webserver met PHP in OS X is heel gemakkelijk.
  
Standaard staat Apache en PHP al geïnstalleerd op Apple computers. Het enige wat je hoeft te doen is de PHP module activeren en Apache starten. Dit kun je op de volgende manier doen.
  
PHP5 Activeren
  
Open een terminal terminal venster. Het Apache configuratiebestand kan op 2 plekken staan. Probeer de onderstaande regels uit. Een van de 2 commando&#8217;s werkt.

_sudo vim /etc/httpd/httpd.conf
  
_ 
  
of
  
_
  
sudo vim /etc/apache2/httpd.conf_
  
Zoek de volgende regel op

_#LoadModule php5_module libexec/apache2/libphp5.so_
  
Klik op de i op het toetsenbord. Je komt nu in de modus waarin je het bestand kunt bewerken. Haal het hekje voor de regel weg. De regel ziet er dan zo uit.

_LoadModule php5_module libexec/apache2/libphp5.so_
  
Klik op
  
_esc_
  
om uit de schrijfmodus te gaan. Typ
  
_:wq_
  
. Het bestend wordt weggeschreven.

De PHP5 module is nu in apache geactiveerd.

Apache activeren
  
Klik op het appeltje links boven in de hoek. Klik op Systeemvoorkeuren&#8230;, Delen.

Zet vervolgens een vinkje voor Webserver. De Apache webserver wordt nu geactiveerd en kan gelijk gebruikt worden. Aan de rechterkant van het venster zie je een link naar de website. Iedere gebruiker op de computer heeft zijn eigen website te vinden onder [http://localhost/~gebruikersnaam](http://localhost/~gebruikersnaam "http://localhost/~gebruikersnaam"). Er is ook een hoofd pagina [http://localhost/](http://localhost/ "http://localhost/"). Je persoonlijke website verwijst naar Finder, Webpagina&#8217;s. De hoofdpagina verwijst naar /Library/WebServer/Documents/.