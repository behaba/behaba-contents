---
title: jQuery.eventManager, un plugin de gestion d'évènements
---
La méthode ```$.delegate``` de jQuery fonctionne sur le principe de la délégation d'évènements. La délégation permet notamment de pouvoir ajouter de nouveaux éléments dans le DOM dynamiquement (via Ajax par exemple) sans pour autant leur ré-attacher d'évènements préalablement défini. Elle assure également de meilleures performances.

Sur la plupart des projets, je m'amusais à déléguer des évènements à des objets globaux. C'est ensuite au moment de l'appel à l'évènement que je filtrais le type d'action à effectuer. C'est un exercice plutôt fastidieux...

J'ai donc décidé de créer un plugin jQuery permettant de faciliter la gestion d'évènement via delegate. Il suffit pour cela de créer un objet recensant les objets globaux, les évènements attachés, le filtre, puis l'action a effectuer.

<!--more-->

Voici un exemple d'objet :
```javascript
var eventList = {
 'div' : {
   'mouseover' : {
     '.sidebar' : function (elem) {
       $(elem).addClass('over');
     },
     default : function(elem) {
       $(elem).css('background-color':'red');
     }
   }
   'mouseout' : function() {
      $(elem).css('background-color':'transparent');
   }
 }
}
```

En clair, je délègue des évènements à un ou plusieurs objets de type ```div```. Je lui attribue un évènement de type ```mouseover```. Par défaut, au passage de la souris sur cette ```div```, le fond de cet objet sera rouge. Si la div possède la classe ```.sidebar```, alors je lui ajoute une classe ```.over```. Enfin, lorsque je quitte un objet de type ```div```, je lui affecte un fond transparent.

Une fois cet objet créé, il ne reste plus qu'à l'insérer dans un appel au plugin eventManager :

```javascript
$('#wrapper').eventManager(eventList);
```

Dans cet appel, seules les div placées dans un objet ayant pour ID #wrapper seront affectés par les évènements à déléguer.

Je vous propose d'accéder à la démo pour vous faire une idée des possibilités offertes. Vous pourrez ensuite, si vous le souhaitez, télécharger le plugin sur [mon espace Github](http://github.com/behaba/jQuery.eventManager).

_Édité le 19 juillet : **Nouveauté sur le plugin,** le code a été nettoyé, on peut se passer de 'default' lorsqu'il n'y a pas de sélecteur filtre. Autre nouveauté, on peut désormais utiliser "this" au lieu de "elem" dans les fonctions de l'objet contenant les évènements. Merci beaucoup à [Sunny](http://sunfox.org "Sunfox.org, le site qui te donne des tâches de rousseur") pour son aide !_

*   [Accéder à la démonstration](http://clearideaz.com/assets/demos/jQuery.eventManager/ "Visualiser la démo du plugin jQuery.eventManager")
*   [Télécharger le plugin](http://github.com/clearideaz/jQuery.eventManager/downloads "Télecharger le plugin jQuery.eventManager sur Github")