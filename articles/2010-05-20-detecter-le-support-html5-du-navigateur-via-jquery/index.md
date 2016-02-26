---
title: Détecter le support HTML5 du navigateur via Jquery
---
Le site <a title="Dive into HTML5 par Mark Pilgrim" href="http://diveintohtml5.org/everything.html" lang="en">Dive into HTML5</a> a publié récemment un article détaillant les différentes méthodes de détection de fonctionnalités HTML5 sur les navigateurs via Javascript.

Utilisateur régulier de <a href="http://jquery.com" title="Site officiel de la librairie Javascript jQuery" lang="en">jQuery</a>, j'ai décidé de porter ces scripts au sein de la fonction <a href="http://api.jquery.com/jQuery.support/" title="Documentation de la fonction support de jQuery" lang="en">```$.support```</a>.

Voici la liste des tests possibles : ```audio```, ```audioMp3```, ```audioVorbis```, ```audioWav```, ```audioAAC```, ```canvas```, ```canvasTxt```, ```command```, ```datalist```, ```details```, ```device```, ```formConstraints```, ```iframeSandbox```, ```iframeSrcDoc```, ```autofocus```, ```placeholder```, ```color```, ```email```, ```number```, ```range```, ```search```, ```tel```, ```url```, ```date```, ```time```, ```datetime```, ```datetime-local```, ```month```, ```week```, ```meter```, ```output```, ```progress```, ```time```, ```video```, ```videoCaptions```, ```videoPoster```, ```videoWebM```, ```videoH264```, ```videoTheora```, ```contentEditable```, ```dragAndDrop```, ```fileAPI```, ```geoLocation```, ```history```, ```localStorage```, ```microdata```, ```applicationCache```, ```eventSource```, ```sessionStorage```, ```svg```, ```svgInHtml```, ```webSimpleDb```, ```webSocket```, ```openDatabase```, ```webWorkers```, ```undo```.

Vous trouverez une démonstration des possibilités offertes par le script sur cette <a href="http://clearideaz.com/assets/demos/jquerySupportHTML5/" title="HTML5 detection with jQuery Support" lang="en">page de test du support HTML5 de votre navigateur</a>.

Si vous souhaitez par exemple tester le support du SVG, insérez la ligne suivante au sein de votre fichier Javascript :

```javascript
$.support.svg // retourne false sur IE et true sur les versions récentes de Firefox
```

Le script est léger : 8ko en version source et 3ko en version minifiée.

Vous pouvez télécharger l'extend jQuery sur <a href="http://github.com/behaba/jquerySupportHTML5" title="Espace Github de Behaba" lang="en">mon espace Github</a> 

N'hésitez pas à me signaler le moindre bug.

Édit : correction d'un lien
