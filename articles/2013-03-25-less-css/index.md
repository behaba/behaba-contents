---
title: Less pour booster vos CSS
tags:
  - html
  - css
  - pre-processeur
---
## Introduction
Depuis quelques années, de nombreux outils ont fleuri sur le web pour optimiser le temps de création de sites internet et plus particulièrement des feuilles de styles. Des frameworks au pré-processeurs de CSS, les intégrateurs ont désormais de nombreux outils auquel recourir pour minimiser leur temps de développement. Nous allons nous intéresser ici à Less, un pré-processeur qui est de plus en plus utilisé et qui est développé par [Alexis Sellier](http://cloudhead.io/).
 
Parmi ses avantages :

- Il s’inspire fortement de la syntaxe CSS même pour les fonctions les plus avancées. Cette caractéristique en fait un des pré-processeurs les plus simple à apprendre.
- Il peut s’utiliser côté serveur (via NodeJS) ou côté client (via Javascript).  Il donc très simple d’utiliser rapidement LessJS.
 
<!--more-->

## Cas concret d’utilisation
Pour une mise en route rapide avec Less, nous allons, à partir d’une base HTML simple, créer un template pour une liste de tags. Vous pourrez constater ainsi une partie des possibilités offertes par l’outil.
Dans notre exemple, Less sera utilisé côté client, c'est à dire que nous utiliserons Javascript pour interpréter le fichier less. Vous pourrez également réaliser ce tutorial en installant Less coté serveur. Pour cela, reportez vous à la partie sur l'installation de Less coté serveur.

### Le code HTML
Nous allons en premier lieu intégrer le fichier less via une balise script. Récuperez la dernière version de Less sur [le site dédié](http://www.lesscss.org) (v1.3.3 au moment de l'écriture de cet article) puis insérez la dans votre code HTML de la manière suivante :
 
```html
<script src="less.js" type="text/javascript"></script>
```
 
Ensuite, intégrez l'appel à la feuille de style Less. En considérant qu'elle se nomme styles.less, voici ce qu'il vous faudra placer :
 
```html
<link rel="stylesheet/less" type="text/css" href="styles.less">
```
 
Précision importante, chacun des appels à une feuille de style less doit précéder la balise de script less.js auquel cas, la feuille de style ne sera pas interprétée.
 
Le code HTML principal est plutôt basique. Nous dressons ici une simple liste à puce.
 
```html
<ul>
  <li><a href="#">Lessjs</a></li>
  <li><a href="#">HTML</a></li>
  <li><a href="#">CSS3</a></li>
  <li><a href="#">Fun !</a></li>
</ul>
```
 
### Définition des mixins et des variables

Afin de pouvoir réutiliser des parties de style, nous allons utiliser la puissance des mixins. Dans notre exemple, nous allons notamment utiliser la propriété « transform » qui va être déclinée pour les extensions propriétaires des navigateurs. Nous allons plus particulièrement utiliser la fonction SkewX qui permet d’appliquer une modification horizontale des coordonnées d'un objet selon un angle donné. Voici le mixin à insérer dans la feuille de style :
 
```less
.skewX(@deg: 90deg) {
  -moz-transform: skewX(@deg);
  -ms-transform: skewX(@deg);
  -o-transform: skewX(@deg);
  -webkit-transform: skewX(@deg);
  transform: skewX(@deg);
}
```
 
La variable entre parenthèse définit la valeur par défaut si aucun paramètre n'a été renseigné au sein du mixin.
 
Nous allons maintenant définir des variables qui nous permettrons de pouvoir configurer plus facilement notre nuage de tags si nous souhaitons par la suite modifier le style.
 
```less
@gutter: 0.8em; // définit les espacements entre les tags
@background:#C7D23F; // couleur de fond du nuage de tags
@text: #262016; // couleur du texte des tags
```

### Stylisation du conteneur principal
 
Nous allons tout d'abord renseigner les styles principaux de la balise “ul” :
 
```less
ul {
  background-color:@background;
  display:inline-block;
  padding:0 0 0 @gutter;
  overflow:hidden;
  position:relative;
}
```
 
Sur le premier attribut, nous avons affecté la variable @background, elle sera donc remplacée en sortie par la couleur #C7D23F.
Ensuite, nous avons utiliser la variable @gutter sur le padding de gauche. Nous obtiendrons donc en valeur finale : 0 0 0 0.8em.
 
Il est possible de modifier en cours de route la valeur de la variable de la même manière qu'en PHP par exemple.

### Stylisation des puces
 
Au sein du sélecteur ul, nous allons insérer celui qui ciblera la balise &lt;li /&gt;. Cet insertion va nous permettre de définir un sélecteur « ul li ». De cette manière, nous allons fournir les propriétés de style des différentes puces. Voici le code :
 
```less
ul {
  // (...)
  li {
     position: relative;
     display: inline-block;
     margin: 0 @gutter 0 @gutter * -2;
     padding: 0 @gutter * 2;
     line-height: 1em;
  }
}
```
 
Vous remarquerez dans l'exemple les différentes opérations. Nous indiquons sur la marge de gauche qu'il faudra la multiplier par -2. Nous obtenons donc l'opération suivante : 0,8em * - 2 = -1,6em. Pour le padding, même chose : 0,8em * 2 = 1,6em.
 
### Les pseudo-sélecteurs
 
Sur cette partie, nous allons utiliser le sélecteur parent de less définit par le symbole &. Inséré dans une accolade, il récupère directement le sélecteur définit précédemment. Ici nous allons obtenir 3 sélecteurs différents : li:before, li:after, li:last-child. Voici maintenant le code :
 
```less
ul {
  // (...)
  li {
     // (...)
     &:before,
     &:after {
        position: absolute;
        top: 0;
        right: 0;
        display: block;
        content: '';
        height: 50%;
        width:0.5em;
        background-color:#fff;
        .skewX(45deg);
     }
 
     &:after {
        top: auto;
        bottom: 0;
        .skewX(-45deg);
     }
 
     &:last-child {
        position:static;
        &:after, &:before {
           right:-@gutter;
           border-right:@gutter * 2 solid #fff;
        }
     }
  }
}
```
 
Encore une fois, nous avons utilisé des variables et des opérations mais vous noterez également la présence du mixin .skewX() définit plus tôt. Utilisé de cette manière, il insère l'ensemble de la syntaxe indiquée au sein du mixin.
 
### La feuille de style finale
 
Voici donc le code complet de votre feuille de style Less :
 
```less
.skewX(@deg: 90deg) {
  -moz-transform: skewX(@deg);
  -ms-transform: skewX(@deg);
  -o-transform: skewX(@deg);
  -webkit-transform: skewX(@deg);
  transform: skewX(@deg);  
}
 
@gutter: 0.8em;
@background:#C7D23F;
@text: #262016;
 
ul {
  background-color:@background;
  display:inline-block;
  padding:0 0 0 @gutter;
  overflow:hidden;
  position:relative;
 
  li {
     position: relative;
     display: inline-block;
     margin: 0 @gutter 0 -@gutter * 2;
     padding: 0 @gutter * 2;
     line-height: 1em;
 
     &:before,
     &:after {
        position: absolute;
        top: 0;
        right: 0;
        display: block;
        content: '';
        height: 50%;
        width:0.5em;
        background-color:#fff;
        .skewX(45deg);
     }
 
     &:after {
        top: auto;
        bottom: 0;
        .skewX(-45deg);
     }
 
     &:last-child {
        position:static;
        &:after, &:before {
           right:-@gutter;
           border-right:@gutter * 2 solid #fff;
        }
     }
 
     a {
        font: bold 2em sans-serif;
        text-decoration: none;
        color:@text;
     }
  }
}
```
 
Et voici le rendu-final :
 
```css
ul {
  background-color:#c7d23f;
  display:inline-block;
  overflow:hidden;
  padding:0 0 0 .8em;
  position:relative;
}
 
ul li {
  display:inline-block;
  line-height:1em;
  margin:0 .8em 0 -1.6em;
  padding:0 1.6em;
  position:relative;
}
 
ul li:before,ul li:after {
  -moz-transform:skewx(45deg);
  -ms-transform:skewx(45deg);
  -o-transform:skewx(45deg);
  -webkit-transform:skewx(45deg);
  transform:skewx(45deg);
  background-color:#fff;
  content:'';
  display:block;
  height:50%;
  position:absolute;
  right:0;
  top:0;
  width:.5em;
}
 
ul li:after {
  -moz-transform:skewx(-45deg);
  -ms-transform:skewx(-45deg);
  -o-transform:skewx(-45deg);
  -webkit-transform:skewx(-45deg);
  transform:skewx(-45deg);
  bottom:0;
  top:auto;
}
 
ul li:last-child { position:static; }
 
ul li:last-child:after,ul li:last-child:before {
  border-right:1.6em solid #fff;
  right:-.8em;
}
 
ul li a {
  color:#262016;
  font:bold 2em sans-serif;
  text-decoration:none;
}
```

## Installer Less coté serveur
 
Si Less doit être utilisé coté serveur, il faudra installer Node.Js qui est un framework javascript. Vous devrez, pour se faire, disposer au préalable de git, python >= 2.4 et libssl-dev sur votre plate-forme.
 
Dans votre shell (Terminal sous Linux et Mac OSX, Cygwin sous Windows), voici les différentes commandes à utiliser :

```bash
git clone --depth 1 https://github.com/joyent/node.git
cd node
git checkout origin/v0.4 # optional. Note that master is unstable.
export JOBS=2 # optional, sets number of parallel commands.
mkdir ~/local
./configure --prefix=$HOME/local/node
make
make install
echo 'export PATH=$HOME/local/node/bin:$PATH' >> ~/.profile
source ~/.profile
```
 
Il existe également des versions de [Node.Js en paquet pré-compilé](https://github.com/joyent/node/wiki/Installing-Node.js-via-package-manager)
 
Si tout s’est déroulé comme prévu, vous devriez alors avoir accès au binaire Node. Pour s’en assurer, tapez la commande suivante :

```bash
node -v // devrait renvoyer v0.4
```
 
Il faut ensuite installer NPM, le gestionnaire de paquets pour Node.Js. Insérez tout simplement dans votre shell la commande suivante :

```bash
curl http://npmjs.org/install.sh | sh
```
 
Tout est prêt maintenant pour installer lessjs coté serveur. Toujours dans le terminal, tapez ceci :
 
```bash
npm install less
```
 
Pour s’assurer que le binaire est bien installé, tapez la ligne suivante :
 
```bash
lessc -v // devrait renvoyer le numéro de version de less
```
 
Si vous rencontrez des soucis durant l’une des commandes, réessayez en mode administrateur.
 
Une fois que vous aurez créé un document less et que souhaiterez le convertir en css, vous n’aurez qu’à vous placer dans le dossier du document less et à insérer la ligne suivante dans votre shell :

```bash
lessc styles.less > styles.css
```
 
## Less sur différents environnements
 
Vous souhaiter utiliser Less sur d'autres plate-formes ? Aucun problème ! Il est existe différent portages du projet qui peuvent toutefois comporter certaines différences sur la syntaxe.

- [Less](https://github.com/cloudhead/less) : La version originale de Less en Ruby
- [DotLessCss](http://www.dotlesscss.org/) : est une version développé en .NET
- [LessPHP](http://leafo.net/lessphp) : permet d'utiliser Less via PHP
- [Less For Java](http://www.asual.com/lesscss/) : est un outil permettant de faire fonctionner lessjs dans un environnement java.
- [lessc.exe](http://digitalpbk.com/less-css/less-css-compiler-windows-lesscexe) : est un binaire pour Windows
- Une autre version existe également pour windows : [https://github.com/duncansmart/less.js-windows](https://github.com/duncansmart/less.js-windows)

*Cet article a déjà fait l'objet d'une parution sur le [Webdesign Magazine](http://ww3.advancedcreation.fr/webdesignmag/)*