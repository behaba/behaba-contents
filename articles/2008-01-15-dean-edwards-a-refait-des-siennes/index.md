---
title: Dean Edwards a refait des siennes
---
Actuellement très occupé sur divers projets web, je n'ai pas eu beaucoup de temps à accorder à mon blog. Je voulais juste vous signaler que Dean Edwards venait de publier une nouvelle classe javascript permettant de pallier les faiblesses de IE 6 mais également de IE 7. Elle ne pèse que 38 Ko et n'utilise aucun module complémentaire. En réalité, il a implémenté les nouvelles possibilités que devrait offrir IE 8, le navigateur qui intégrera (théoriquement) CSS 3.

Je précise que cette classe js est en cours développement et qu'elle contient encore quelques bugs. Pour l'avoir déjà utilisé, je peux déjà vous  en citer quelques uns :

*   Difficulté à gérer les classes pouvant posséder plusieurs propriétés (ex : #accueil .conteneur {}, #article .conteneur {})
*   Certaines propriétés telle que la pseudo-classe :first-child ne fonctionnent pas si on utilise une feuille de style externe

La classe est à télécharger sur [la page de Projet Google de Dean Edwards](http://code.google.com/p/ie7-js/ "Se rendre sur la page de projet de Dean Edwards")
