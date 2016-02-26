---
title: Les standards selon la firme de Redmond
---
![Un IE sous acide :)](acidie.gif "Un IE sous acide :)")En lisant [un article très intéressant de Marc Hertzog](http://marcarea.com/weblog/?post/2008/01/27/IE-8-ne-souhaite-pas-casser-le-web "Se rendre sur le blog de Marc Hertzog") sur le futur navigateur de Microsoft, je me suis aperçu que Microsoft n'était décidément pas prêt de changer. Même si, dans l'article précédent, j'ai (quelque peu) défendu le fait qu'il faille continuer à développer pour <abbr title="Internet Explorer">IE</abbr>, je m'aperçois qu'encore une fois, **le futur <abbr title="Internet Explorer">IE</abbr> va semer le trouble dans la conception web**. Bien qu'il soit déjà reconnu pour être le premier navigateur Microsoft à respecter strictement les standards du web, cela ne se fera pas à n'importe quel prix. Il faudra, en effet, spécifier au navigateur qu'il devra basculer en mode standards à l'aide de cette balise méta :

```html
<meta http-equiv="X-UA-Compatible" content="IE=8" />
```

Microsoft a voulu, une fois de plus, de se démarquer des autres navigateurs en imposant sa syntaxe. Pourquoi devoir signaler au navigateur qu'il s'agit d'une page respectant les standards? De plus, je trouve particulièrement indécent de renseigner dans l'attribut "content" les initiales du futur Internet Explorer. **Microsoft serait donc le pionnier en matière de standards du web ?** On m'aurait menti ?