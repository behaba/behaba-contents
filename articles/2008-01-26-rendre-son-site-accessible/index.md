---
title: Rendre son site accessible
---
Sur le web, les sites respectant les règles de validités <abbr title="World Wide Web Consortium">W3C</abbr> fleurissent, mais pour ce qui est des sites accessibles, **les progrès sont lents**.

**Que faut-il faire exactement pour rendre son site accessible?**

Nous allons voir brièvement une liste d'éléments à intégrer dans le code XHTML pour permettre à son site de **respecter les contraintes d'accessibilité**.

### Bien organiser son document XHTML

Un document accessible se doit de respecter une certaine logique. **On ne doit surtout pas organiser son contenu en fonction de l'apparence graphique du site**. C'est la méthode qui était utilisée lorsque l'on construisait des structures graphique à l'aide de tableau. Il faut veiller à ce que le document soit lisible sans la présence de feuilles <abbr title="Cascading Style Sheet">CSS</abbr>. On respecte impérativement l'ordre logique des balises (```<h1>```, ```<h2>```, etc...). Le titre du site et de la page consultée doit se trouver en haut du document suivi du menu principal. On passe ensuite au contenu et enfin le pied de page.

### Veiller à ce que le titre de la page change

Cela parait peut être anecdotique mais la balise ```<title>``` est très importante pour les personnes ayant des déficiences visuelles. Cela leur permet de mieux se repérer dans les différentes pages du site internet. Si vous laissez le même titre pour chaque page, il sera complètement perdu. Et puis, prendre la peine de mettre des beaux ```<title>``` en fonction du contenu, ça fait déjà plus sérieux ;)

### Indiquez à l'utilisateur où il se trouve sur la page

Il est important parfois de signaler à l'utilisateur utilisant un lecteur d'écran où il se trouve sur la page en l'indiquant dans un texte masqué par <abbr title="Cascading Style Sheet">CSS</abbr> pour les autres utilisateurs. Pour cela, on signale par exemple à l'internaute qu'il se trouve sur le menu principal par cette phrase : "Vous êtes actuellement sur la navigation principale du site". On cache cette phrase par la propriété CSS > display:none. Attention, n'utilisez pas la propriété ```visibility:hidden``` car la phrase ne sera pas lue par le lecteur d'écran.

### On ne fait pas de la mise en page avec des tableaux

Beaucoup de sites ont encore des structures graphiques à base de tableaux. Sémantiquement, ça ne veut rien dire. Rappelons-le, **les tableaux sont destinés uniquement à la structuration de données**.

### Renseignez correctement vos tableaux

Le tableau est certainement l'élément le plus difficile à rendre accessible. **Les lecteurs d'écran ont beaucoup de mal à lire les données tabulaires non renseignées**. L'attribut "Summary" permet de donner une indication sur les données contenues dans le tableau. "Caption" servira à donner un titre. Il faut également définir les entêtes du tableaux. Les balisages ```<thead>```, ```<tbody>``` et ```<tfoot>``` permettent de rassembler les différentes parties du tableau, ils correspondent respectivement à l'entête, le corps et le pied du tableau. Ensuite, on place des ID à chaque entête et on assigne aux cellules associées cet ID par le biais de l'attribut headers="". Enfin, si vraiment on souhaite être pointilleux, on ajoute aux entêtes l'attribut ```abbr=""``` afin de donner une abréviation du contenu de la cellule.

Voici un tableau non-accessible...


```html
<p class="desc">Evolution du prix des jouets</p>
<table border="1" cellspacing="0" cellpadding="2">
   <tr>
     	<td><b>Jouets</b></td>
     	<td><b>Elmo</b></td>
     	<td><b>Nono le robot</b></td>
     	<td><b>Poupée barbie</b></td>
     	<td><b>Canard vibrant</b></td>
     </tr>
     <tr>
     	<td><b>Prix en 1998</b></td><br />
     	<td>20,3 €</td>
     	<td>35,4 €</td>
     	<td>23,2 €</td>
     	<td>10,5 €</td>
     </tr>
     <tr>
     	<td><b>Prix en 1999</b></td>
     	<td>20,6 €</td>
     	<td>30,4 €</td>
     	<td>25,2 €</td>
     	<td>9,5 €</td>
     </tr><tr>
  </tr>
</table>
```

... et le même tableau respectant les contraintes d'accessibilité :

```html
<table summary="Tableaux de prix des jouets en euros" border="1" cellspacing="0" cellpadding="2">
	<caption>Evolution du prix des jouets</caption>
	<thead>
		<tr>
			<th>Jouets</th>
			<th id="elmo" abbr="elmo">Elmo</th>
			<th id="nono" abbr="nono">Nono le robot</th>
			<th id="barbie" abbr="barbie">Poupée barbie</th>
			<th id="canard" abbr="canard">Canard vibrant</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<th id="1998">Prix en 1998</th>
			<td headers="elmo 1998">20,3 €</td>
			<td headers="nono 1998">35,4 €</td>
			<td headers="barbie 1998">23,2 €</td>
			<td headers="canard 1998">10,5 €</td>
		</tr>
		<tr>
			<th id="1999">Prix en 1999</th>
			<td headers="elmo 1999">20,6 €</td>
			<td headers="nono 1999">30,4 €</td>
			<td headers="barbie 1999">25,2 €</td>
			<td headers="canard 1999">9,5 €</td>
		</tr>
	</tbody>
</table>
```

*   [Pour en savoir plus...](http://openweb.eu.org/articles/tableaux_css/ "Se rendre sur les tableaux accessible d'Openweb") (Tutorial Open Web)

### Bien organiser ses formulaires

Les formulaires bénéficient également de règles d'accessibilité. Lorsque vous créez un ```<label>``` pour une balise ```<input>```, vous devez impérativement définir l'id associé :

```html
<p>
	<label for="ymca">YMCA</label>
	<input name="post_ymca" type="text" id="ymca" />
</p>
```

Ensuite, la balise ```<fieldset>``` permet de regrouper différentes catégories de champs. La balise ```<legend>```, quant à elle, permet de donner un titre aux différents ```<fieldset>``` :

```html
<fieldset>
	<legend>Civilité</legend>
	<p><label>Nom&nbsp;: <input type="text" name="champs_nom "/></label></p>
	<p><label>Prénom&nbsp;: <input type="text" name="champs_prenom " /></label></p>
</fieldset>
<fieldset>
	<legend>Renseignement divers</legend>
	<p><label>Date d'obtention du permis: <input type="text" name="champs_permis" /></label></p>
	<p><label>Loisirs : <input type="text" name="champs_loisirs" /></label></p>
</fieldset>
```

_(Notez que l'on a organisé le formulaire différemment pour les labels. Néanmoins, Internet Explorer comprend mal ce type de balisage.)_

Sur ce même formulaire, on peut ajouter l'attribut ```tabindex=""``` afin de définir l'ordre de tabulation. Cela se révèle très utile :


```html
<fieldset>
	<legend>Civilité</legend><br />  
	<p>
		<label>
			Nom&nbsp;: 
			<input tabindex="1" type="text" name="champs_nom "/>
		</label>
	</p>
	<p>
		<label>
			Prénom&nbsp;: 
			<input tabindex="2" type="text" name="champs_prenom " />
		</label>
	</p>
</fieldset>
<fieldset>
	<legend>Renseignement divers</legend>
	<p>
		<label>
			Date d'obtention du permis:
	 		<input tabindex="3" type="text" name="champs_permis" />
	 	</label>
	 </p>
	 <p>
	 	<label>
	 		Loisirs : 
	 		<input tabindex="4" type="text" name="champs_loisirs" />
	 	</label>
	 </p>
</fieldset>
```

Concernant les listes déroulantes, on fera appel à ```<optgroup>``` afin de créer des catégories lorsque cela est nécessaire :

```html
<select name="constructeur_automobile">
	<optgroup label="Europe">
		<option value="vw" selected="selected">Volkswagen</option>
		<option value="peu">Peugeot</option>
		<option value="ren">Renault</option>
	</optgroup>
	<optgroup label="Asie">
		<option value="hyun">Hyundai</option>
	</optgroup>
</select>
```

*   [Pour en savoir plus...](http://openweb.eu.org/articles/formulaire_accessible/ "Se rendre sur le tuto sur les formulaires accessible d'Openweb") (Tutorial Open Web)

### Ajouter des combinaisons d'accès rapide

Les attributs ```accesskey=""``` permettent de définir des raccourcis-clavier pour accéder directement aux éléments de la page. Cela peut se révéler pratique pour la navigation à l'intérieur de la page mais également dans les longs formulaires. Il ne faut jamais utiliser de lettre pour les raccourcis-clavier

*   [Pour en savoir plus...](http://openweb.eu.org/articles/accesskey_essai_non_transforme/ "Se rendre sur Openweb") (Article Open Web)

### Ajouter des ```title=""``` à chaque lien

Sur chaque lien que vous placerez sur vos pages, il faudra renseigner un title sous cette forme :

```html
<a href="mon lien" title="Se rendre sur la page de mon lien">
  Mon lien
</a>
```

Il est important de placer dans cet attribut title **un vrai texte de description** du lien et non pas une phrase bidon.

### Ne pas oublier les "alt" des images

Quand cela se justifie, il faut impérativement renseigner l'attribut alt correspondant à l'image affichée. Parfois, il n'est pas important de le renseigner si l'image n'est pas importante (notamment pour certaines images d'illustration) pour comprendre le document. Tout est question de jugement.

### Pour aller plus loin

Voici ci-dessous une liste de site qui complètera cet article :

*   [Section Accessibilité d'Open Web](http://openweb.eu.org/accessibilite/ "Se rendre sur la section Accessibilité d'Openweb")
*   [Article d'AlsaCréationS sur les Access Keys](http://css.alsacreations.com/Accessibilite-du-Web/Accesskey-le-grand-echec-de-l-accessibilite-du-Web "Se rendre sur l'article Accesskey le grand échec de l'accessibilité du Web d'Alsacreations")
*   [Le site Access-Keys, une référence en la matière](http://www.access-key.org/ "Se rendre sur le site Access-Keys.org")
*   [Un testeur d'accessibilité](http://www.accessibiliteweb.com/ "Se rendre sur le testeur de site d'Accessibilite Web")