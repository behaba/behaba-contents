---
title: Comment ouvrir les hostilités...
tags:
  - webdesign
  - w3c
  - accessibilité
---
Pour ce premier billet qui inaugure ce carnet Web, j’aimerais exposer **ma conception de la réalisation Web**.

[![Design du blog de Veerle](public_veerleblog1-150x150.jpg "Design du blog de Veerle")](public_veerleblog1.jpg)Aujourd’hui, l’apparence d’un site Web est un élément primordial qui peut fidéliser des visiteurs. Le look peut saisir l’utilisateur soit par la beauté de sa simplicité ([Flickr](http://www.flickr.com/ "Aller sur le site de Flickr") pour ne citer que lui) ou encore par sa finesse et sa recherche du détail ([le blog de Veerle](http://veerle.duoh.com/ "Aller sur le blog de Veerle") en est un excellent exemple).

**La réalisation web est devenu un exercice particulièrement périlleux** au vue de la multiplication des supports de lecture (PDA, Lecteurs d’écran, systèmes d’exploitation) et c’est pourquoi il a fallu définir un certain nombre de conventions en quelque sorte.

On utilise le terme "Accessibilité" à tort et à travers mais de quoi s’agit-il exactement ?

Pour Tim Berners-Lee, directeur du [W3C](http://www.w3.org/ "Aller sur le site officiel du W3C"), l’Accessibilité c’est :

> Mettre le Web et ses services à la disposition de tous les individus, quel que soit leur matériel ou logiciel, leur infrastructure réseau, leur langue maternelle, leur culture, leur localisation géographique, ou leurs aptitudes physiques ou mentales.

Quelle jolie idée ! Sur le papier c’est pas mal mais sur le terrain, c’est une autre histoire. **Le message est parfois mal compris.**

### Le fond et la forme

![W3C](public_w3c.gif "W3C")Le <abbr title="World Wide Web Consortium">W3C</abbr> est un consortium qui veille à ce que les pages web respectent plusieurs règles syntaxiques. Il a mis en place sur son site officiel un validateur de pages qui scrute les différentes pages à la recherche de l’erreur de syntaxe fatale !!! Mais beaucoup considèrent que si le site passe dans le [validateur](http://validator.w3.org/ "Aller à la page de validation des pages du W3C"), c’est qu’il est accessible. **Il n’en est rien**.

Plusieurs balises ou informations importantes pour les lecteurs d’écran peuvent être insérées dans le code afin de le rendre plus accessible. Par exemple pour un tableau, il est recommandé de fournir une balise <caption> afin de lui définir une légende. Mettre des title="" pour les balises de lien est également un reflex à avoir (j’avoue parfois, j’en oublie, suis-je pardonné ?).

**La vraie révolution** ces dernières années a été de passer au <abbr title="eXtensible HyperText Markup Language">XHTML</abbr> ! Enfin, on ne mélangeait plus dans le processus de création la structure et la présentation ! C’est à ce moment qu’on a pu constater la puissance des feuilles <abbr title="Cascading Style Sheets">CSS</abbr>. En reprenant le même squelette HTML, on pouvait modifier l’apparence totale avec deux feuilles de style. Toutefois, même si de plus en plus de concepteurs web tendent à apprendre CSS et XHTML, d’autres se bornent à poursuivre à réaliser des sites avec tableaux. Et **le plus triste dans tout ça, c’est que parfois ces sites sont présentés en exemple**. Sur Webcreme (un site que je fréquente régulièrement), j’ai pu découvrir l’horreur (j’en fais trop ?). Le 23 Novembre, [Webcreme](http://www.webcreme.com/2007/11/four-iv/ "Aller sur la page du site Webcreme concernant FOURIV") publie le site [FOURIV](http://www.fouriv.com/ "Aller sur le site tout en tableaux FOURIV :(") qui est bâti uniquement sur des tableaux… Je me rassure en me disant que [Webcreme](http://www.webcreme.com/ "Aller sur le site de Webcreme") ne s’est jamais défini comme un relais des techniques de créations XHTML/CSS mais plutôt comme une inspiration pour le design de site web.

### Finalement

Faire du design web actuellement, c’est plutôt imaginer comment disposer les différents calques de manière à obtenir la plus jolies mise en page. Il ne s’agit plus de créer sa maquette sur Photoshop et de l’adapter sans réfléchir sur son éditeur html.** Il y a un véritable travail de sémantique**. L’ordre dans lequel seront disposées les différentes balises ne sera pas forcément l’ordre dans lequel les éléments apparaîtront sur la page. Par exemple, il est en général, plus convenable de placer le menu de navigation en haut de la page de code juste en dessous de la balise de titre principale (h1) même si sur la maquette du site web, ce menu apparaît sur le coté gauche, en dessous de la bannière.

Lors de la phase de conception, l’idéal, serait en fait, de bâtir dans un premier temps le code html nu sans feuille de style afin de réaliser **une hiérarchisation du contenu** et surtout **organiser une certaine logique de la sémantique** (oh ça rime !).

En tout état de cause, le design web n’est plus uniquement un souci d’apparence mais aussi une réflexion autour de l’intégration des éléments graphiques dans le code. Cela permet des rapprocher les codeurs et les designeurs et ça, c’est plutot une bonne nouvelle :)
