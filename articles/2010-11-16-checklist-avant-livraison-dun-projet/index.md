---
title: Checklist avant livraison d'un projet
---
Je ne sais pas pour vous mais la livraison d'un projet est souvent sujet à bon nombre d'incertitudes. A-t'on pensé à tout ?
Un bon nombre de clients va chercher à évaluer la réponse apportés à sa demande initiale, ce qui est tout à fait normal.
Il est important d'avoir une checklist qui servira de contrôle qualité avant la livraison d'un site web.
Je précise que ces contraintes sont largement inspirées de celles de l'équipe web "BNP E-business".

<!--more-->

Voici donc une liste (non-exhaustive) des points de contrôle effectués&nbsp;:

## Points de contrôle

### Ergonomie

- Ne pas utiliser de soulignement de texte pour autre chose que des liens.
- La page 404 est indispensable et doit être personnalisée aux couleurs du site. Proposer éventuellement un formulaire de recherche.
- Une feuille de style d’impression doit être prévue.


### Accessibilité

- En cas d’utilisation de plug-ins (vidéo, Flash), prévoir une alternative textuelle pour un utilisateur qui n’aurait pas installé et/ou ne voudrait pas installer le plug-in.
- Tester la page sans images (via l'extension Webdevelopper de Firefox) pour s'assurer que l'ensemble du contenu est lisible sans les images de fond. Exemple&nbsp;: Un texte blanc sur une image def fond peut devenir illisible si aucune couleur de fond n'a été spécifiée dans les propriétés du bloc conteneur.
- Toute image doit avoir un alt, renseigné ou non. Illustration&nbsp;: alt vide, ou image de fond
- Dans le cas où des fichiers sont proposés au téléchargement, deux points sont à respecter&nbsp;: format ouvert, poids du fichier à télécharger doit être indiqué.
- Le javascript doit être non-obstrusif et le site doit être parfaitement utilisable s'il est désactivé par l'utilisateur.

### Intégration HTML / CSS

- Les pages sont valides W3C
- Le balisage est propre&nbsp;: pas de styles ou de scripts dans le code HTML
- Le doctype du document HTML sera du XHTML 1.0 Transitional  dans le cas (limité) d’utilisation d'iframe.
- Le doctype du document HTML sera du XHTML 1.0 Frameset  dans le cas (limité) d’utilisation de frameset.
- **Bannir l'utilisation de tableaux** pour la mise en page, les tableaux ne doivent être utilisée que pour des données tabulaires et non pas pour créer des mises en page.
- S'efforcer de renseigner l'intitulé « title » des liens pour des raisons de référencement et d'accessibilité. Le title du lien doit fournir plus d'informations que l'intitulé du lien lui-même (mais y compris l'intitulé; ex&nbsp;: "Aide (nouvelle fenêtre)")
- La **structuration** de l'**information** doit être **cohérente** par rapport au **contexte général du site** Web (ex&nbsp;: pas de pub au milieu du texte)
- Une page Web doit posséder une structure cohérente (utiliser **h1 (oblig.), h2**, …pour leur fonction 1ère; les blocs d'infos doivent être distincts)
- Pour les tableaux de données, identifier les zones suivante&nbsp;: « thead » (pour l'entête du tableau), « tbody » (pour le corps du tableau) et « tfoot » (pour les données de pied de tableau). On s'efforcera de fournir une description du tableau au sein de la balise « summary »
- Les champs de saisie d'un formulaire doivent être reliés à leurs textes explicatifs respectifs (spécifier **label, id** et **for**)
- Respecter le sens sémantique des balises. Proscrire l'utilisation des balises et attributs dépréciés (ex&nbsp;: b, center, basefont, applet, dir, font, isindex, menu, s, strike, u et align, bgcolor, height…).
- Utiliser la balise ```<abbr>``` et/ou ```<acronym>``` ainsi que son attribut title lorsque cela est possible.
- Dans le cas d’un style spécifique à Internet Explorer, utiliser les commentaires conditionnels. Evitez les hacks du type "_margin" ou encore "*width"
- Pour conserver un maximum de souplesse aux feuilles de style, limiter tant que possible le « poids » des déclarations. Exemple&nbsp;: privilégier « .content » à « body.page #wrapper div.content »
- **Pas de notions topographiques ou colorimétriques dans les noms de classes** ou&nbsp;: noms faisant référence à la structure. Pas de couleur ni gauche/droite. Exemple&nbsp;: ne pas utiliser div.rouge ou div.left. Si on décide un jour de modifier les propriétés de placement ou d'apparence, ces classes n'auront plus de sens.
- Ne pas utiliser de cote, double ou simple, dans les chemins des CSS.
- Les sites, les pages doivent pouvoir être actualisés facilement et avec souplesse. De ce fait, les zones de contenu doivent s’étendre graphiquement en hauteur (pas de hauteur fixe donc pour les blocs)

###  Optimisation du référencement

- Pour des raisons de référencement, limiter au maximum les paramètres et les caractères « exotiques » dans les liens.

- Les balises d’indexation ```<title>```, ```<meta name="description" />``` et ```<meta name="keywords" />``` doivent êtres renseignées même si leur action en terme de référencement peut être discutable. Elles doivent être situées juste sous la balise définissant l’encodage et dans l’ordre suivant&nbsp;: title / description / keywords
- La balise ```<title>``` doit être présente et renseignée sur toutes les pages. Elle doit être en adéquation avec son contenu et donc, dans la plupart des cas, différente d’une page à l’autre.
- La balise ```<meta name="description" />``` doit être présente et renseignée sur toutes les pages. C’est une balise visible par l’internaute. Elle doit être significative de son contenu, des services rendus par la page, des informations livrées.
- La balise ``<meta name="keywords" />`` doit être présente et renseignée sur toutes les pages. Elle doit reprendre les quelques mots-clé de la page. On peut aussi y inclure certains pluriels, synonymes, anglicismes, etc.
- Prévoir un fichier à l’intention des robots d’indexation, à la racine du site. (robots.txt)

###  Compatibilité Navigateurs

- Internet Explorer 6 (N.B.&nbsp;: Pour cette version, il faut que le site soit un minimum exploitable)
- Internet Explorer 7 et +
- Firefox 2 et +
- Safari 2 et + (tolérance)
- Opera 9 et + (tolérance)
- Les pages livrées doivent s’afficher, sans ascenseur horizontal, dans un écran en 1024 x 768

###  Performance

- Le poids maximal d’une page, images incluses, ne doit pas dépasser 150k.
- Seule la page d’accueil fait exception et peut atteindre jusqu’à 250k, images incluses.
- Évitez les appels multiples à des feuilles de style ou à des fichiers javascript. Merger ces appels pour des raisons évidentes de performance
- L’utilisation du format PNG 24 devra être utilisé avec parcimonie pour des raisons de compatibilité navigateur (IE6 ne supporte pas les couches alpha sans l'utilisation de DirectX. Ce dernier pose des soucis de performances, les images filtrées n'étant pas mises en cache).

###  Autre...

- L’encodage privilégié est l’UTF-8, il est indiqué avec la balise meta « content type ».
- Les caractères suivants doivent être encodés sous forme d’entité HTML&nbsp;: ```&amp;```, ```&lt;```, ```&gt;```, ```&euro;```
- Prévoir une icône de favori à la racine du site.
- Les valeurs monétaires, statiques ou dynamiques, doivent suivre le format suivant&nbsp;: un espace insécable comme séparateur de millier une virgule comme séparateur de décimale un espace insécable entre le nombre et son unité
- Utiliser un espace insécable entre une double ponctuation et le mot qui la précède&nbsp;: !, ?,&nbsp;:,;
- Les chemins vers les pages (mais aussi vers les scripts, feuilles de style, images, etc) doivent être en absolu en considérant le répertoire / comme la racine du site.
- Dans le cas d’envoi de paramètre dans l’URL, ne pas oublier d’encoder sous forme d’entité HTML le « &amp; » (&amp;amp;).