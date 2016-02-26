---
title: Utilisabilité et ergonomie
tags:
  - ux
  - accessibilité
  - css
---
## Introduction

L’utilisabilité ou usabilité est définie par la norme ISO 9241-11 comme « le degré selon lequel un produit peut être utilisé, par des utilisateurs identifiés, pour atteindre des buts définis avec efficacité, efficience et satisfaction, dans un contexte d’utilisation spécifié » (définition Wikipédia).
On nomme ergonomie « l'étude scientifique de la relation entre l'homme et ses moyens, méthodes et milieux de travail » et l'application de ces connaissances à la conception de systèmes « qui puissent être utilisés avec le maximum de confort, de sécurité et d'efficacité par le plus grand nombre. »

<figure class="large">

  ![Ergonomie et Utilisabilité sur le web](http://clearideaz.com/assets/articles/utilisabilite-ergonomie/usability.png)
  <figcaption>Illustration <a href="http://www.shutterstock.com/">Shutterstock</a></figcaption>
  
</figure>
 
Les critères de l’utilisabilité sont :

- l’efficacité : le produit permet à ses utilisateurs d’atteindre le résultat prévu ;
- l’efficience : atteint le résultat avec un effort moindre ou requiert un temps minimal ;
- la satisfaction : confort et évaluation subjective de l’interaction pour l’utilisateur.

Dans cet article, nous allons explorer quelques-une des règles à suivre pour améliorer l’ergonomie d’un site web.

<!--more-->

## Typographie

Sur le web, la manière d’agencer l’information est très différente du format imprimé. Il faut des messages clairs et efficaces. Il est important de captiver rapidement l’oeil de l’utilisateur. C’est à la mise en page que revient la tâche de rendre l’information clairement identifiable mais c’est la typographie qui va rendre l’information lisible. Voici quelques critères qui permettent d’obtenir un bon niveau de lisibilité :

- Largeur de ligne : 150 caractères par ligne est idéal pour une bonne lisibilité.
- Interlignage : utiliser un ratio minimum de 1,3 par rapport à la taille de la police.
- L’espacement entre les caractères : éviter les espacements trop large. En général, garder celui par défaut suffit. Toutefois, pour des titres en taille de police importante, il peut être judicieux de réduire l’espacement.
- Alignement : l'alignement à gauche améliore la lisibilité (éviter la justification qui provoque des effets indésirables).
- Taille de police : un minimum de 12 pixel ou 0.75em est conseillé...
- Type de police : selon des études, il n'y a pas de différence entre les polices de caractère à empattement et celles sans empattement, cependant, certains experts affirment que les polices à empattement sont meilleures pour la lisibilité..
- Famille de police : éviter les polices exotiques difficiles à lire.
 
Pour améliorer la typographie d’un site, il existe de nombreux frameworks CSS. Citons notamment [Blueprint](http://www.blueprintcss.org/), [BaselineCSS](http://baselinecss.com/), [Atatonic](http://atatonic.timbenniks.nl/) et enfin le petit dernier, [Gridless](http://thatcoolguy.github.com/gridless-boilerplate/).

## Couleurs et contraste

Le contraste des couleurs est directement lié à l'esthétique et à la typographie. L'utilisation d'un texte noir sur fond blanc (ou vice-versa) peut rendre le contenu pénible à lire.
Ajouter à cela, la part d’utilisateurs daltoniens (10% des hommes) et vous comprendrez que le choix des couleurs pour un site n’est pas si évident.
Heureusement, Pour tester les contrastes, vous trouverez différents outils pour vous aider à convenir à un large public :

- [Colorscheme designer](http://colorschemedesigner.com/) : cet outil web permet de générer des palettes de couleur avec des contrastes importants. Il permet également de visualiser cette palette en mode daltonien.
- [Contrast A](http://adobe.com/cfusion/marketplace/index.cfm?event=marketplace.offering&offeringid=10763) : il s’agit d’une application Adobe Air permettant de tester le rapport de contraste entre la couleur de texte et la couleur de fond. Il indique également le niveau de conformité (WCAG 2.0 ou WCAG 1.0). Cette application permet également d’avoir un aperçu des couleurs par un daltonien (chose qu’il est également possible faire dans la suite Adobe Creative).
- [Colorblind](http://colorfilter.wickline.org/) : Cet outil web va vous permettre de visionner n’importe quel site web du point de vue d’un daltonien en paramétrant ses différentes variante (Deutéranopie, Protanopie, Tritanopie, etc...). Cet outil ne pourra pas utiliser pour les sites Flash. [ColorOracle](http://colororacle.cartography.ch/) est un logiciel similaire qui vous permettra de tester tout type de sites.
 
Globalement, vous éviterez de choisir des couleurs qui sont similaires en terme de luminosité, comme avoir un gris clair sur fond blanc.
Enfin, bannissez la distinction des boutons d’action au seul paramètre de la couleur.

## Navigation

La navigation est sans doute l'élément le plus important d'un site web. Il indique à l'utilisateur où il est et où aller. Un menu de navigation efficace doit immédiatement indiquer à l'utilisateur comment il doit procéder s'il veut passer à une autre URL.
Voici comment améliorer la convivialité de la navigation :

- Cohérence : la navigation doit apparaître au même endroit sur ​​chaque page.
- Visibilité : la navigation doit être facile à trouver. Il faut rester classique dans le positionnement (en général, en haut à droite ou dans une barre latérale). Le choix de son emplacement est stratégique et doit être directement mis en relation avec le contenu de la page.
- Couleurs : différencier les liens actifs, les liens sélectionnés et les liens survolés est très important.
- Texte : utiliser uniquement des icônes / images pour la navigation demande à l'utilisateur de deviner ce qu'ils signifient. Utiliser plutôt du texte accompagné pourquoi pas d'une icône.
Les liens du contenus jouent également un rôle essentiel dans votre navigation. Créer des relations entre les différents documents quand cela est possible va vous permettre de maximiser les accès à vos contenus.
Faites attention aux termes génériques pour vos liens (“cliquez ici“, “en savoir plus”). Le document lié doit être clairement identifiables.
Si votre site comporte beaucoup de sous-rubriques, il peut être judicieux de fournir un fil d’ariane.
Et pour aider un peu plus l’utilisateur à s’y retrouver sur votre site, pensez à intégrer un moteur de recherche quand le niveau de contenu devient important.
Enfin, n’oubliez pas la page “plan du site” et la fameuse page d’erreur 404.

## Des outils simples et des listes de contrôle

Les tests d'utilisabilité évaluent l'efficacité de l'ergonomie du site web.
Afin d'améliorer son site web, il est essentiel de savoir ce qui peut être amélioré et il faut savoir comment les utilisateurs interagissent avec le site.
Voici une liste d'outils qui peut fournir ces tests d'utilisabilité :

- [Clixpy](http://clixpy.com/) : traque tout ce que font les utilisateurs sur le site : mouvement de la souris, clics, défilement de pages, les entrées de formulaire. Vous aurez la possibilité de regarder et d'examiner des vidéos montrant ces actions.
- [Usabilla](http://usabilla.com/) : offre un moyen simple et rapide pour recueillir des retours visuels sur des pages Web, des maquettes, des croquis, ou d'autres images.
- [Fivesecondtest.com](http://fivesecondtest.com/) : aide à affiner les pages de destination et les call-to-action (élements appellant à une action de l'utilisateur) en analysant les éléments les plus importants du design.
- [Userfly.com](http://userfly.com/) : fournit une liste d'études sur les visiteurs en enregistrant leurs visites et en analysant leurs mouvements de souris et leurs interaction avec les formulaires du site.

## Conclusion

L'Internet évolue très vite, et la tentative de créer des sites web uniques peut vraiment mener la vie dure à l'utilisateur final. La tentation de vouloir réinventer la roue peut rendre chaotique la navigation dans un site. Repousser les limites du webdesign est une chose, créer une interface user-friendly et rapidement compréhensible en est une autre.
Il ne faut pas perdre de vue que l’utilisateur consulte plusieurs dizaines de sites par jour sinon plus... Le temps passé sur chacune des pages de ces sites est très réduit. Bien souvent, il ne lit pas, il survole. S’il ne prends pas le temps de décrypter le contenu d’un site, pensez-vous vraiment qu’il en prendra à étudier votre système de navigation ultra-novateur ?
Attention, il ne s’agit pas ici d’un refus de la modernité ! Bien au contraire ! Allier la modernité des nouvelles technologies à une ergonomie maîtrisée est un défi qui s’offre à vous pour les projets à venir.
Il existe un certain nombre d’ouvrages dédiés à l’ergonomie web et à l’accessibilité et il est parfois difficile de s’y retrouver.
Même si le web évolue à une vitesse impressionnante, les principes d’ergonomie restent sensiblement les mêmes au fil des années. Disposer d’ouvrages de référence pour aborder vos prochains projets vous sera bénéfique. Voici quelques livres qui vont vous aider à progresser sur l’ergonomie et l’accessibilité de vos sites web :

- [Je ne veux pas chercher ! Optimisez la navigation sur vos sites](http://www.amazon.fr/veux-pas-chercher-navigation-internautes/dp/274402189X) par Steve Krug : En plus d’être agréable à lire, cet ouvrage met en relation utilisabilité et design. Avec des exemples concrets, l’auteur expose les failles de certaines navigations ou de mode de fonctionnement. Vous explorerez différents modes de navigation et découvrirez l’importance des tests d’utilisabilité.
- [Ergonomie Web. Pour des sites web efficaces](http://www.amazon.fr/Ergonomie-web-Pour-sites-efficaces/dp/2212132158/) par Amélie Boucher : Ce livre présente les lois théoriques de l’ergonomie et les met en pratique. Comment aborder l’ergonomie sur de nouveaux projets ? Comment améliorer l’ergonomie d’un site existant ? Tout y est expliqué de manière simple et précise.
- [Site Web Priorité à la Simplicité](http://www.amazon.fr/Site-Web-priorit%C3%A9-%C3%A0-simplicit%C3%A9/dp/2744021520) par Jakob Nielsen et Hoa Lauranger : Dans cet ouvrage, Jakob Nielsen, référence dans le monde de l’ergonomie, explique que la simplification du contenu, la simplification des éléments de navigation et l’explication des visées du site sur la page d’accueil sont les éléments-clés d’une bonne ergonomie.

*Cet article a déjà fait l'objet d'une parution sur le [Webdesign Magazine](http://ww3.advancedcreation.fr/webdesignmag/)*