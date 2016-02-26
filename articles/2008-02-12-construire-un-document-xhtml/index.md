---
title: Construire un document XHTML
---
![xhtml, c'est chaud !!!](http://clearideaz.com/assets/articles/construire-un-document-xhtml/xhtml.gif "xhtml, c'est chaud !!!")Le **XHTML** (_eXtended HyperText Markup Language_) est, à l'instar du HTML, un langage de balisage. Sa syntaxe est basée sur la syntaxe du <abbr title="Extensible Markup Language">XML</abbr>.

Il existe différentes versions du <abbr title="eXtended HyperText Markup Language">XHTML</abbr> :

*   **XHTML 1.0 Strict** : Il ne gère que le contenu du document et non l'affichage. C'est le type de document à privilégier.
*   **XHTML 1.0 Transitional** : C'est la passerelle entre le <abbr title="HyperText Markup Language">HTML</abbr> et le XHTML. Il permet l'utilisation de balises liées à l'affichage.
*   **XHTML 1.0 Frameset** : C'est le seul type de document qui autorise les frames. Logiquement, un document accessible ne doit pas inclure d'éléments frame donc à éviter...
*   **XHTML 1.1** : C'est une évolution du XHTML 1.0 Strict avec quelques balises qui ont été implantés ou modifiés.

Lors de la construction d'un document XHTML, il est important d'avoir à l'esprit que ce n'est pas l'apparence du site qui engendre le balisage mais bien le contenu de ce document.

Pour l'élaboration d'un document type, nous prendrons le XHTML Strict 1.0 comme référence. Nous ne gérerons que le contenu. Exit les propriétés d'affichage tels que _bgcolor_, _color_ ou encore _size_. Nous éviterons, de ce fait, de placer l'attribut (tout à fait valide) _style=""_ qui insère dans le document des propriétés <abbr title="Cascading Style Sheet">CSS</abbr>. Cela se fera dans une feuille de style externe. Le XHTML nécessite de se mettre en conformité avec certaines règles :

<!--more-->
*   **Le XHTML impose l'utilisation d'attributs** ```<input type="checkbox" name="option_test" id="option-test" value="" checked="">``` en HTML s'écrit en XHTML : ```<input type="checkbox" name="option_test" id="option-test" value="" checked="checked">```
*   **Toute balise ouverte doit être refermée** Vous pourrez remarquer dans l'exemple ci-dessus le slash à la fin de la balise input.
*   **Les balises doivent être correctement imbriquées** Un ordre hiérarchique des balises est défini. C'est l'ordre logique de lecture du document qui déterminera l'agencement des balises et non l'affichage que le site devra avoir à l'écran.
*   **Toute la syntaxe doit être rédigée en bas de casse** Autrement dit, en minuscule.
*   **Les attributs obligatoires ne doivent pas être omis** On citera notamment _alt_ pour la balise _img_.
*   **Chaque attribut sera encadré de guillemets ** L'utilisation de double-quote est <del>donc de rigueur</del> conseillé pour chaque attribut de balise.

## L'entête du document

L'entête de page permet au navigateur de connaître un certain nombre d'informations avant de charger le corps de page (le contenu). On y trouvera par exemple, le type d'encodage (UTF-8 ou ISO), le titre du document ou l'appel à des fichiers externes (feuilles de style, javascript). L'entête est introduit par la balise ```<head>``` qui est insérée juste après le balise ```<html>```.

La première étape n'est pas indispensable. On indique au navigateur qu'il s'agit d'un document XML tout en renseignant dans l'attribut encoding, l'encodage des caractères (ici ISO) :

```html
<?xml version="1.0" encoding="iso-8859-1"?>
```

Un problème se pose toutefois avec Internet Explorer. En effet, en affichant cette balise avant le doctype, le navigateur passe en quirks mode, c'est-à-dire en mode non-standard.

Le DOCTYPE est la seconde chose à spécifier dans le document XHTML. Il permet au navigateur de savoir à quel type de document il a à faire. Voici les DOCTYPEs XHTML qu'il est possible d'insérer :

### XHTML 1.0 Strict

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" 
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
```

### XHTML 1.0 Transitional

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" 
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
```

### XHTML 1.0 Frameset

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Frameset//EN" 
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-frameset.dtd">
```

### XHTML 1.0 Strict

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.1//EN" 
"http://www.w3.org/TR/xhtml11/DTD/xhtml11.dtd">
```

Ensuite, il faut renseigner la balise ```<html>``` avec un namespace utilisant l'attribut ```xmlns```. On prendra le soin de spécifier la langue du document dans les balises ```xml:lang="la_langue"``` et ```lang="la_langue"```. Cette redondance est requise pour la validité du document et la compatibilité avec les différents navigateurs. Ces deux attributs ont la même fonction mais lang="" permet en réalité d'être compris sur les anciens navigateur.

```html
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="fr" lang="fr"></html>
```

Nous passons ensuite à l'entête du document par le biais de la balise ```<head>```. Cette balise permettra de lier au document une ou plusieurs feuilles de styles, d'insérer des appels à des fichiers javascript. Mais auparavant, il faut définir l'encodage du document à l'aide d'une balise meta :

**Pour de l'UTF-8** (Encodage international) :

```html
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
```

<strong>Pour de l'ISO</strong> (Encodage européen) :

```html
<meta http-equiv="Content-Type" content="text/HTML; charset=iso-8859-1" />
```

Pour plus d'info sur la notion d'encodage, lisez [l'article d'OpenWeb sur les jeux de caractères](http://openweb.eu.org/articles/jeux_caracteres/ "Se rendre sur l'article d'OpenWeb sur les jeux de caractères")

On aura la possibilité d'ajouter différentes balises méta afin de permettre un meilleur référencement du document. En voici un exemple :

```html
<meta name="DC.title" xml:lang="fr" content="Clearideaz.com, XHTML, CSS, Accessibilité, Marketing, Design web" />
<meta name="author" content="Gorzalka, Olivier" />
<meta name="description" content="Carnet web de Olivier Gorzalka" />
```

Comme vous pourrez le constatez, on utilise une balise meta avec dans l'attribut name DC. Il s'agit en fait d'un schéma de métadonnées générique préconisé par le W3C.

Nous pouvons maintenant définir le titre du document avec la balise ```<title>```. Il faut qu'il soit explicite. Évitez de donner le même titre à toutes les pages de votre site. Pensez aux personnes non-voyantes (et pas seulement...) utilisant des lecteurs de d'écran et qui se repèrent grâce aux dénominations des différents articles. Le titre se présentera de la façon suivante :

```html
<title>
     Clearideaz.com, XHTML, CSS, Accessibilité, Marketing, Design web
</title>
```

A la suite de ce ```<title>```, on insère l'appel éventuel à une feuille de style. Il existe deux méthodes sensiblement équivalentes :

### La méthode @import

```html
<!--
     @import url(/themes/clearideaz/style.css);
-->
```

### La méthode link

```html
<link rel="stylesheet" href="themes/clearideaz/style.css" type="text/css" media="screen" />
```

Il n'existe pas, en soit, de grandes différences entre ces deux méthodes. Nous signalerons tout de même que ```@import``` n'est pas reconnue par les navigateurs dinosaures tels que Netscape 4.

## Le corps du document

Nous arrivons au corps du document via la balise ```<body>```. C'est le contenu qui sera visible dans le navigateur internet. On s'efforcera de hiérarchiser au maximum les éléments textuels. Il est important de ne pas penser à l'apparence du site lorsque l'on procède au balisage du document. Il faut respecter l'ordre de lecture du contenu. Nous userons par exemple des différents niveaux de titre ```<h1>```, ```<h2>```, ```<h3>```, ```<h4>```, ```<h5>``` et ```<h6>```

Lorsqu'il s'agira d'une liste d'éléments, on utilisera les listes à puce :

```html
<h1>Sciences de la vie</h1>
Bienvenue sur le site "Sciences de la vie"
<h2>Le monde animal</h2>
Voici différents animaux :
<ul>
     <li>Le chien</li>
     <li>Le singe</li>
     <li>Le tigre</li>
</ul>
```

_Rappel : Chaque balise ouverte doit être obligatoirement refermée. Ainsi un paragraphe de texte commencera par ```<p>``` et se terminera par ```</p>```. Les balises de retour à la ligne ne s'écrivent plus ```<br>``` comme ce fut le cas dans le HTML mais ```<br />```. Idem pour ```<hr>``` qui devient ```<hr />```._

Un document XHTML type n'organisera pas son contenu à l'aide de tableau. Pour une meilleure hiérarchisation, on utilisera les calques qui se traduisent par des balises ```<div>```. Ces balises nous permettrons par la suite de styler le document à l'aide de la feuille CSS. Il est judicieux d'attribuer à chaque balise ```<div>``` un ID explicite qui permettra de les différencier lors de l'élaboration de la feuille de style :

```html
<div id="page">
     <div id="entete">
     </div>
     <div id="conteneur">
     <ul id="menu-principal">
          <li>Rubrique 1</li>
          <li>Rubrique 2</li>
          <li>Rubrique 3</li>
     </ul>
     <div id="contenu">
     </div>
     </div>
     <div id="pied">
          Créé par Moi :)
     </div>
</div>
```

Évitez de multipliez les calques, cela facilitera la compréhension de votre balisage.

Enfin on ferme la balise ```<body>``` et ```<html>``` du document. Voici donc ce que l'on pourrait obtenir :

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="fr" lang="fr">
<head>
     <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
     <meta name="DC.title" xml:lang="fr" content="Weblog.fr, XHTML, CSS, Accessibilité, Marketing, Design web" />
     <meta name="author" content="Gorzalka, Olivier" />
     <meta name="description" content="Carnet web de Olivier Gorzalka" />
     <title>Weblog.fr, XHTML, CSS, Accessibilité, Marketing, Design web</title>
     <style type="text/css" media="screen">
          @import url(/themes/weblogr/style.css);
     </style>
</head>
<body>
     <div id="page">
          <div id="entete">
               <h1>Sciences de la vie</h1>
          </div>
          <div id="conteneur">
               <ul id="menu-principal">
                    <li>Rubrique 1</li>
                    <li>Rubrique 2</li>
                    <li>Rubrique 3</li>
               </ul>
               <div id="contenu">
                    Bienvenue sur le site "Sciences de la vie"
                    ## Le monde animal
                    Voici différents animaux :
                    <ul>
                         <li>Le chien</li>
                         <li>Le singe</li>
                         <li>Le tigre</li>
                    </ul>
               </div>
          </div>
          <div id="pied">
               Créé par Moi :)
          </div>
     </div>
</body>
</html>
```

### La validation W3C

Une fois le document XHTML terminé, il faut passer le fichier HTML au [validateur W3C](http://validator.w3.org/ "Voir le validateur W3C"). Le W3C est un consortium visant à promouvoir la compatibilité des technologies du Web et notamment le XHTML. En vérifiant la validité de la syntaxe de votre site, vous aurez la certitude que les différents documents XHTML respectent les standards du web. Si votre document contient des erreurs, le validateur vous les listera et il faudra bien évidemment les corriger ;)

## Les balises courantes

Il existe un grand nombre de balises XHTML qui permettent de rendre le document plus compréhensible. Je vous invite à visiter [l'espace de Giminik](http://giminik.developpez.com/xhtml/ "Voir l'espace de Giminik") qui recense l'ensemble des balises courantes du XHTML. Il existe deux grandes catégories de balises. Les inline (en-ligne) et les block (bloc). Les balises blocs permettent de structurer le document et peuvent contenir d'autres balises block ou inline. Les inline quant à eux attribue une sémantique spécifique à des mots d'une phrase et ne peut contenir que des éléments inline.

### Les balises de type block

**```<div>```** Elle donne la possibilité de structurer le contenu en différent blocs couramment appelés calques.

**```<h1>```, ```<h2>```, ```<h3>```, ```<h4>```, ```<h5>```, ```<h6>```** Ils définissent différents niveaux de titre _(ex: ```<h2>```Mon titre```</h2>```)._

**```<hr />```** Cette balise insère une ligne horizontale dans le document.

**```<p>```** Cette balise identifie un élément comme paragraphe.

**```<ul>```, ```<ol>```, ```<li>```** Elles intègrent des listes d'éléments au document. La balise ```<ul>``` insère une liste à puces tandis que ```<ol>``` dresse une liste ordonnée. Les différents éléments de la liste sont encadrés par la balise ```<li>```.

## Les balises de type inline

**```<a>```** Elle insère un lien hypertexte sur le texte balisé. Elle peut aussi agir comme point d'ancrage dans le document.

**```<br />```** Elle permet d'insérer un saut de ligne. A utiliser avec parcimonie...

**```<em>```** Le texte est mis en emphase? On l'assimile souvent à tort avec la balise ```<i>```.

**```<strong>```** Elle permet de réalise une mise en emphase forte.

**```<span>```** Elle donne la possibilité de mettre en forme du texte à l'aide de CSS.

**```<img />```** Cette balise insère une image dans le document. Elle doit automatiquement intégrer un attribut <em>alt=""</em>.

**```<cite>```** Elle défini un texte comme citation. L'équivalent en block est <em>blockquote</em>.

**```<abbr>```** Elle donne la signification d'une abréviation. (_ex: <abbr title="Cascading Style Sheet">CSS</abbr>)._

**```<q>```**  
Elle caractérise une courte citation.

### Ce qu'il faut éviter

Voici quelques petites choses à éviter lors de la création de votre document XHTML.

*   Abuser des retours à la ligne (```<br />```). Préférez l'utilisation de paragraphe (```<p>```)
*   Multipliez les balises ```<div>```. D'autres éléments peuvent être stylés à la manière de ces calques.
*   Utiliser ```<img />``` pour des illustrations. Cette balise ne doit être utilisée que si elle apporte un complément d'information au texte de l'article.
*   Insérer du javascript dans le document. Tout le code JS doit être placé dans un fichier externe. C'est ce qu'on appelle le [javascript non-intrusif](http://www.journaldunet.com/developpeur/tutoriel/dht/070119-js-unobstrusive-javascript-non-intrusif.shtml "Voir un exemple sur le JDN").
*   Nommer les ID ou les class des différents éléments en fonction de la couleur qu'ils auront dans le document. Pensez que votre site pourra évoluer et donc que les couleurs pourront changer. Nommer donc vos balises selon leur sens sémantique et non selon leur apparence.
*   Insérer du style CSS dans le document avec <em>style=""</em>. La feuille de style est là pour ça, pourquoi surcharger votre document ?

Comme nous avons pu le constater, la création d'un document XHTML est soumise à un certain nombre de règle. A ces règles s'ajoutent ensuite [les contraintes d'accessibilités](http://www.weblogr.fr/index.php/post/2008/01/26/Rendre-son-site-accessible "Voir l'article qui explique comment rendre son site accessible"). En respectant ces "normes", vous garantissez à votre site d'être lu par différents supports. Être lu par le plus grand nombre, c'est bien ça le principe du web ;)

### Pour aller plus loin

Quelques liens qui apporteront un complément à ce billet :

*   [Documentation du XHTML 1.0 par le W3C](http://www.w3.org/TR/xhtml1/ "Voir la documentation du W3C sur le XHTML") ([traduction française](http://www.la-grange.net/w3c/xhtml1/ "Voir la traduction de la documentation sur le XHTML par le W3C"))
*   [Rubrique XHTML du site OpenWeb](http://openweb.eu.org/xhtml/ "Se rendre sur les articles d'Open Web à propos du XHTML")
