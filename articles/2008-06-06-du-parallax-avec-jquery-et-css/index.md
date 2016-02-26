---
title: Du Parallax avec jQuery et CSS
---

Le [scrolling parallax](http://fr.wikipedia.org/wiki/D%C3%A9filement "Voir la définition de Scrolling Parallax sur Wikipédia") est une technique qui consiste a créer un pseudo-effet de 3D sur un environnement en 2D. Si vous avez déjà pu jouer aux premières versions de Sonic The Hedgehog, vous comprendrez de quoi je parle. Je me suis amusé, encore une fois avec JQuery, a créer un effet parallax sur une page d’accueil d’un site existant.

J’ai repris la page d’accueil de [SilverBackApp.com](http://www.silverbackapp.com "Se rendre sur le site SilverBack.com") qui utilise déjà un effet Parallax au redimensionnement du navigateur. La technique très subtile consiste a placer les différentes couches de fonds avec des background-position en pourcentage. En jouant justement sur ces valeurs relatives, on peut de ce fait créer un effet intéressant lorsque l’utilisateur redimensionne sa fenêtre.

En partant de cette base, j’ai décidé de rajouter une couche Javascript. Le but est de changer la position du fond en fonction de la position de l’image. Pour cela, on va juste récupérer les positions du pointeur et utiliser ces valeurs pour déterminer le positionnement (en pixel cette fois) des différentes images.

<!--more-->

On obtiendra avec jQuery ce type de code pour la div #frontvines

```javascript
$("body").mousemove(function(event){
   $("#frontvines").css({ 
      backgroundPosition: (event.clientX * 1.1) + 'px 0px'
   });
});
```

Sur la première ligne, on cherche l’évènement qui indique que l’utilisateur bouge sa souris sur la page. Dans la partie fonction, on place en paramètre la position du curseur pour la réutiliser ensuite pour modifier les propriétés de styles associées à la balise comportant l'id #frontvines. Pour observer le résultat, rendez-vous sur la page dédié à cette démonstration [disponible ici](http://clearideaz.com/assets/demos/05062008/ "Accéder à la première démonstration").

Pour aller plus loin, je me suis amusé, dans une [seconde démonstration](http://clearideaz.com/assets/demos/06062008/ "Accéder à la seconde démonstration"), à réutiliser une photo de paysage pour y introduire du parallax. Le principe reste le même, je vous laisse le soin de télécharger le script sur [la page de la seconde démonstration](http://clearideaz.com/assets/demos/06062008/ "Accéder à la seconde démonstration"), vous y trouverez la manière de procéder dans les commentaires du fichier Javascript.

## Quelques liens en rapport avec Parallax :

### Effet parallax à l’aide de CSS ou de Javascript

*   [Le futur site de service Dumago.net (CSS)](http://dumago.net/ "Se rendre sur le site Dumago.net")
*   [Effet parallax aux mouvements de la souris sur Umaghetzeggen.nl (Javascript)](http://www.umaghetzeggen.nl/ "Visiter le site Umaghetzeggen.nl")
*   [Le site des tests de performances Javascript Dromaeo (CSS)](http://dromaeo.com/ "Accéder au site Dromaeo.com")
*   [Démo expérimentale de footer avec effet de vagues (CSS)](http://www.dvessel.com/ "Voir la demo sur le site Dvessel.com")

### Utilisation de parallax sous Flash

*   [Une démo assez bluffante en Flash](http://www.ff0000.com/ "Se rendre sur le site ff0000.com")
*   [Effet de rotation rendu grâce à parallax](http://www.effectscode.com/ImageEffects/DepthField/XML/ "Se rendre sur le site EffectsCod.com")
*   [Un header construit en parallax](http://a.viary.com/ "Aller sur le site de Aviary")
*   [Le site Freedent White](http://www.freedentwhite.com/index.php/page/fr "Visiter le site Freedent White")

### Tutorial

*   [Un tutos sur Sitepoint.com sur les effet parallax en CSS](http://www.sitepoint.com/blogs/2008/01/18/in-the-lab-doing-strange-things-to-css-backgrounds/ "Voir le tutos à propos de parallax via CSS ")
