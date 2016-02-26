---
title: Internet Explorer 9 sur la bonne voie
---
## Des débuts (très) difficiles

Internet Explorer a (très) souvent été la cible de critiques passionnées. En cause, son moteur de rendu (Trident) non conforme aux standards du web définis par le W3C et ses nombreux bugs.
La version 6 s'imposait de nombreuses années au sein du système Windows XP.

![Internet Explorer 9, the fucking browser](ie.png)Microsoft décide de publier la version 7 de son navigateur qui sera en série sur le tout nouveau système, Windows Vista. Les améliorations sont nombreuses mais la firme Redmond persiste dans sa volonté d'imposer ses "standards". Il intègre toutefois de nouveaux pseudo-sélecteurs CSS (IE6 ne supportant que les pseudo-sélecteurs affectés aux liens) et supporte enfin le format PNG alpha.  
Problème, la plupart des utilisateurs de Windows XP ne migrent pas vers Vista, le système ayant une mauvaise réputation en terme de stabilité et d'ergonomie. Le passage vers IE7 prendra beaucoup de temps et encore aujourd'hui, IE6 dispose d'une part importante dans le pourcentage des navigateurs utilisés. Cette lente migration s'explique également par le fait qu'Internet Explorer 6 ne dispose d'aucun système de mise à jour automatique (à contrario de Firefox par exemple).

<!--more-->

## Un semblant de renouveau

IE8 succède à la version 7. Les effets d'annonce de cette version n'attenueront pas les critiques de la communauté web. Microsoft fait encore une fois cavalier seul. Son navigateur, en dépit de quelques améliorations ergonomiques, ne parvient pas à séduire le public de connaisseurs.  
Ce navigateur met en place un nouveau principe : la définition du mode de rendu. [Il est possible en effet de choisir entre le mode de rendu IE7 et celui d'IE8 via une balise meta](http://behaba.com/articles/les-standards-selon-la-firme-redmond "Les standards selon la firme Redmond"). Ce principe va à l'encontre du concept d'amélioration progressive. On ne devrait pas choisir de développer pour un ancien navigateur.  
Autre problème, le support du PNG pourtant bien géré sur IE7 est défaillant sur cette version.

## Une lueur d'espoir

Intervient le projet IE9 mené par une équipe renouvelée et des consultants plus jeunes ! À l'heure où je publie cet article, cette version est encore à l'état de développement.
Première nouveauté : Microsoft communique largement sur le projet et encourage fortement la communauté à effectuer des retours.  
Seconde nouveauté : IE9 se veut respectueux des standards du web. [Microsoft se retrouve désormais contributeur actif du W3C](http://www.w3.org/QA/2010/03/interview_paul_cotton_on_micro.html "Interview: Paul Cotton on Microsoft Participation in the W3C HTML Working Group"). Ils insistent sur l'obligation de rendu unique sur l'ensemble des navigateurs.  
Troisième et dernière nouveauté : L'équipe d'IE9 a fait beaucoup d'efforts pour améliorer les performances de son navigateur. Il dispose aujourd'hui d'un des plus puissants moteur Javascript (en comparaison avec les moteurs en version définitive et publiés avec des navigateurs stable, hein !).

Mais ce qui est surtout le plus excitant, c'est le support de nouvelles technologies web. La liste est longue : support de CSS3 (on peut enfin utiliser border-radius, ouais !), moteur de rendu capable d'interpréter HTML5 ainsi que son API (balise video, audio, geolocalisation, webworkers...), implémentation de font-face, mise en conformité de l'interpréteur javascript avec les standards, support de SVG...  
Et dernièrement, [le blog du navigateur Microsoft a annoncé le support de canvas](http://blogs.msdn.com/b/ie/archive/2010/06/23/html5-native-third-ie9-platform-preview-available-for-developers.aspx "HTML5, Native: Third IE9 Platform Preview Available for Developers") ainsi que la prise en charge du format libre WOFF, on y croyait vraiment plus !

Chose étonnante, le futur navigateur suscite l'enthousiasme des professionnels ([Andy Clarke](http://www.stuffandnonsense.co.uk/blog/about/internet_explorer_9_in_on_the_boil/ "Internet Explorer 9 is on the boil"), [Zeldman](http://www.zeldman.com/2010/03/16/ie9-preview/ "IE9 preview") ou encore [Jason Cube](http://sixrevisions.com/web-development/five-things-ie9-is-actually-doing-right/ "Five Things IE9 is (Actually) Doing Right") de Six Revision).

## Et finalement...

C'est donc une grande avancée et on s'imagine déjà développer des sites internet sans avoir à le tester sur 36 navigateurs ! Mais malgré tout, ne fantasmons pas trop vite, le chemin sera encore long et il faudra je pense attendre encore 10 ans avant de pouvoir utiliser pleinement les nouvelles possibilités offertes par HTML5 et CSS3.

<em>Edité le 25 juin 2010 à 9 h 33 min : Ajout d'une petite phrase au sujet de l'intérêt suscité par le navigateur auprès de professionnels</em>