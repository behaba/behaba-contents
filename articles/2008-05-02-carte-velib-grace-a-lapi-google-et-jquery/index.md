---
title: Une carte Vélib grâce à l'API Google
---
Si vous habitez Paris ou si vous ne faites qu'y travailler (comme moi), vous avez surement déjà eu l'occasion d'utiliser le service Vélib. Le [site officiel](http://www.velib.paris.fr/ "Se rendre sur le site officiel du service Vélib") ou d'autres sites indépendants comme [Roulib.fr](http://www.roulib.fr "Visiter le site Roulib.fr") proposent des cartes permettant d'afficher le nombre de vélos disponibles ou encore le nombre d'emplacements restants. Je vous propose de faire la même chose grâce à l'[API de Google Map](http://code.google.com/apis/maps/documentation/ "Voir la page de documentation concernant l'API de Google Maps").

![](map.jpg "css3highlight") 

Le principe est simple. On génère en local un fichier XML à partir du fichier distant présent sur le site officiel Vélib via <abbr title="Hypertext Preprocessor">PHP</abbr>. Une fois cette étape effectuée, on a plus qu'à charger le fichier xml à l'aide de [Javascript.](http://fr.wikipedia.org/wiki/JavaScript "Se rendre sur la page Wikipédia concernant la définition du Javascript")

[La page de démonstration du script](http://clearideaz.com/assets/demos/04062008/ "Se rendre sur la page de démo du script de la carte Vélib") utilise le framework [jQuery](http://www.jquery.com "Se rendre sur le site officiel de jQuery") mais vous pourrez trouver dans l'[archive](http://clearideaz.com/assets/demos/04062008/gmap-velib.zip "télécharger directement l'archive depuis cette page") une version en javascript pur et une autre version associée à l'autre framework [Prototype](http://www.prototypejs.org/ "Visiter le site officiel du framework Prototype") (Merci d'ailleurs à [Sunny](http://www.sunfox.org/ "Voir le fabuleux blog de mon escroc de collègue Sunny") pour son aide ;) )

Vous trouverez toutes les informations nécessaires dans les commentaires des différents fichiers javascript. N'oubliez pas d'aller [générer une clé API Google Map](http://code.google.com/apis/maps/signup.html "Se rendre sur le site Google Map pour obtenir une clé API") sur le site dédié.

Pour pouvoir accéder à la carte et télécharger le script associé, rendez-vous sur [la page de démo du script de carte Vélib](http://clearideaz.com/assets/demos/04062008/ "Se rendre sur la page de démo du script de la carte Vélib"). L'archive contient le script php pour générer les fichiers xml de la carte Vélib et des informations associées à chaque borne, les fichiers Javascript correspondants, la feuille de style <abbr title="Cascading Style Sheet">CSS</abbr> et les images requises.