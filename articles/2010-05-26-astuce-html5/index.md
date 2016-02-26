---
title: Astuce pour HTML5
---
Comme vous avez surement pu le constater, il est possible en HTML5 d'encadrer des balises de type bloc par une balise de type lien inline de cette manière :

```html
<a href="http://www.smashingmagazine.com">
  <h1>Smashing Magazine</h1>
  <h2>online magazine dedicated to designers and developers.</h2>
</a>
```

Le lien devient ainsi actif sur l'ensemble des balises bloc. Ceci évite d'insérer plusieurs fois le même lien.

Ce balisage marche sur la plupart des navigateurs dont IE6 seulement voilà, sur ce dernier, le curseur n'est pas correct au survol des balises de type bloc. A la place du pointeur, on à le curseur de type de texte.

Voici ce que l'on peut ajouter dans la feuille de style pour corriger celà :

```css
a * { cursor:pointer; }
```

Et miracle, le curseur par défaut des liens fonctionne également sur les balises type bloc.