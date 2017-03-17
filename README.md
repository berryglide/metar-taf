# metar-taf
Travaux sur récupération des METAR et TAF pour le briefing AC Issoudun (LFEK)


Objectif :
--------
Développer la partie METAR, TAF et conversion FL-altitude QNH pour un briefing vélivole, en Javascript et donc en utilisant des sources de données qui permettent les requêtes Ajax cross-domain.


Base de travail :
---------------
Travail se basant sur ce qu'on peut trouver sur http://www.volavoile.net/index.php?showtopic=12194 et adapté pour Issoudun LFEK.


Source des données METAR et TAF :
-------------------------------
API https://avwx.rest/documentation, dont on peut trouver les sources pas loin d'ici : https://github.com/flyinactor91/AVWX-Engine
D'après les sources, les données sont issues de https://aviationweather.gov/adds/dataserver_current.
je ne suis pas sûr que les paramètres de recherche sur aviationweather.gov soient optimaux : "hoursBeforeNow=2" fait qu'on peut ne pas retrouver de message et la requête sur l'API avwx échoue et retourne une erreur 500. Cela oblige à gérer ces cas.

Pour palier ce problème, il serait possible par exemple d'utiliser le paramètre "mostRecentForEachStation=constraint" et agrandir le délai de recherche "hoursBeforeNow=2".


Reste à faire :
-------------
- Coder la récupération du SunSet, probablement en incorporant un JS utilisé ici : https://www.esrl.noaa.gov/gmd/grad/solcalc/index.html

- ...
