---
title: Les hacks c'est pas bien !
---
La tentation de recourir à des hacks est grande lorsque l'on commence à se lancer dans l'intégration d'un site web. Lorsque l’on s'aperçoit que la page développée s'affiche différemment d'un navigateur à l'autre, on se dit très souvent que c'est le navigateur (Internet Explorer pour ne pas le citer) qui interprète le code ou la feuille de style n'importe comment.

Cette réaction est plus ou moins justifiée. Nous sommes tous conscients des lacunes du navigateur Microsoft et plus particulièrement des versions antérieures à la 7. Toutefois, ce n'est pas une raison pour charger sa feuille de style de propriétés invalides en prenant comme bouc émissaire le navigateur de Monsieur Redmond. 

Une feuille de style doit, au même titre que le document <abbr title="eXtensible HyperText Markup Language">XHTML</abbr>, passer l'épreuve du validateur <abbr title="World Wide Web Consortium">W3C</abbr>. Ce n'est pas en insérant des "_width:" ou encore de "%margin:" dans votre <abbr title="Cascading Style Sheet">CSS</abbr> que vous pourrez vous vantez de faire un site au codage propre. J'irais même jusqu'à dire que <strong>les hacks sont bons pour les fainéants la plupart du temps</strong>.

Dernièrement, j'avais fais remarquer à un intégrateur remonté contre <abbr title="Internet Explorer">IE</abbr> que notre boulot perdrait de l'intérêt sans ces soucis de compatibilité. Même si j'affirmais cela ironiquement, je trouve passionnant de découvrir pourquoi telle propriété ne fonctionne pas de la même manière d'un navigateur à l'autre et surtout, comment y remédier.

<!--more-->

## Les hacks que l'on pourrait éviter

### Les images PNG

Prenons l'exemple du <abbr title="Portable Network Graphics">PNG</abbr>. Beaucoup de webmasters s'extasient devant les possibilités de ce format d'image. L'utilisation des <a href="http://blog.lablonde.fr/billets/25-la-couche-alpha-des-png-sous-internet-explorer.html" title="Voir un article traitant des possibilités et des caractéristiques du format PNG">différentes couches alpha de transparence</a> offre effectivement de nombreuses possibilités. Seulement voilà, ce format n'est pas pris en charge par les anciennes versions d’IE. Le hacker en herbe viendra me faire remarquer que l'on peut remédier à ce problème en utilisant la propriété CSS DX.Transform dans la feuille CSS ou dans un <a href="http://www.zeguigui.com/weblog/archives/2005/01/les_behaviors_m.php" title="Les behaviors, mais qu'est-ce donc ?">fichier .htc</a>. Cette utilisation pose plusieurs soucis :

- La feuille de style n'est pas valide W3C.
- La feuille CSS n'est pas censée intégrer ce genre de propriétés ou faire appel à des fichiers chargeant du JavaScript.
- Ce hack fait appel au moteur <a href="http://fr.wikipedia.org/wiki/DirectX" title="Voir l'article dédié à Direct X sur Wikipédia">Direct X</a> et selon la version, une simple image peut faire bugger le système d'exploitation, ce qui est, vous en conviendrez, un peu gênant...

Si vous souhaitez vraiment utilisez le PNG sur Internet Explorer, appelez plutôt un fichier JavaScript pur pour arriver à vos fins.

Parfois, un simple découpage de l'illustration au format <abbr title="Graphics Interchange Format">GIF</abbr> ou même une image JPEG placée intelligemment peut offrir au visiteur le même effet. <strong>Le PNG n'est pas une fin en soit</strong>.

### Les pseudo-classes

Concernant les pseudo-classes, évitez également de passer par un fichier .htc dans votre feuille de style pour intégrer le :hover sur une balise div ou un :target sur une tout autre balise. Encore une fois, si cette utilisation est requise, passez par de pures fonctions JavaScripts.

### Un problème de taille !

Arrêtons de nous prendre le chou avec les débats philosophiques sur le <a href="http://www.tatane.info/index.php/le-hack-model-box-css" title="Un exemple d'article décrivant un hack de model box">model box</a> ou autre double-margin. Ces problèmes peuvent être aisément contournés. De plus, vous le verrez par vous même, quand on commence avec des hacks de placement ou d'ajustement de dimension, on en finit plus. <strong>Les hacks attirent les hacks</strong> :)

Comme vous pourrez le constater sur l'<a href="http://clearideaz.com/assets/demos/23042008/test.html" title="Voir la démonstration sur la gestion des positionnements, padding et margin en CSS">exemple suivant</a>, les soucis de padding ou de margin peuvent parfois être causés par une simple propriété qui n’a pas lieu d'être. Pour être certain de contrôler pleinement votre mise en page, efforcez-vous de tester plusieurs méthodes de positionnement sans passer par les hacks et testez le résultat sur différents navigateurs. Il y aura toujours une méthode qui fasse plaisir à tout le monde :)

## Pour résumer

Avant de se décider à utiliser un hack, il faut d'abord se questionner sur les autres alternatives valables. <strong>Dénigrer IE sans chercher plus loin n'amènera rien de bon</strong>. N'intégrez pas de fonctions JavaScripts dans votre feuille de style par le biais de fichiers .htc mais préférez un fichier JavaScript pur. N'abusez pas du format PNG et ne l'utilisez qu'en dernier recours. Privilégiez l'utilisation de "!important" aux notations bidons telles que "_width:" ou encore "%padding:". Les hacks CSS c'est taboo, on en viendra tous à bout.

## Quelques précisions s'imposent

Au regard de cet article, on peut se demander ce qui est à ranger dans la catégorie des hacks ou non. Si je voulais résumer, j'engloberais les éléments qui ne valident pas la feuille CSS mais voici une petite liste détaillées :

- Dans un premier temps, j'inclus l'ensemble des propriétés mal orthographiées : "_width:", "%padding:" par exemple.
- Les inclusions de fichiers .htc pour faire appel à du javascript par exemple.
- Les propriétés CSS non reconnues par le W3C tel que "opacity".
- Les propriétés en double pour une même classe ou ID (deux propriétés de taille pour un même bloc).
- Les appels à Direct X dans la feuille de style.

Et voici ce que je ne considère pas comme des hacks :

- Les sélecteurs non reconnus par tous les navigateurs mais valides W3C tel que "div &gt; p" (logique non?).
- Les propriétés non reconnues par tous les navigateurs mais valides W3C. "min-height" en est un exemple.
- Les feuilles de style appelées par des <a href="http://forum.alsacreations.com/faq/faq-53-Qu039est-ce-que-les-commentaires-conditionnels-.html" title="Qu'est-ce que les commentaires conditionnels?">commentaires conditionnels</a> (même si on s'en passerait bien...)
