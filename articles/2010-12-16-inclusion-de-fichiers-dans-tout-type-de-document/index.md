---
title: Inclusion de fichiers dans tout type de document
---
Une des règles première en terme de performance est de minimiser au maximum les requêtes HTTP. Voici une méthode qui peut avoir son utilité lorsque vous utilisez une dizaine de plugins jQuery ou si vous êtes attaché à séparer vos styles dans diverses feuilles CSS !

<figure class="large">
  <img class="large" src="htaccess.png" alt="htaccess ain't cool but still useful">
  <figcaption>Illustration <a href="http://www.shutterstock.com/">Shutterstock</a></figcaption>
</figure>
Il est possible de réaliser des inclusions de fichiers coté serveur. Pour cela, il vous faudra d'abord rendre opérationnelle l'extension mod_include sur Apache.
Rien de plus simple ! En supposant que votre serveur apache est localisé chemin "/etc/apache2/", exécutez la commande suivante :

<pre class="language-bash">
<code>$ sudo ln -s /etc/apache2/mods-available/include.load /etc/apache2/mods-enabled</code>
</pre>

Cette commande va créer un lien symbolique du module "include" dans le dossier des modules activés de Apache.

N'oubliez pas de redémarrer Apache :

```bash
$ apache2 -k restart
```

Une fois cette opération effectuée, vous avez fait le plus gros du boulot. Nous allons maintenant utiliser ce module pour activer les inclusions au sein des fichiers javascript ayant pour extension ".includer.js"

Dans votre dossier contenant les scripts ou même à la racine de votre projet, créez un fichier .htaccess. Dans ce fichier .htaccess, nous allons d'abord définir un filtre de type de fichier :

```apacheconf
<FilesMatch "\.includer\.js$"></FilesMatch>
```

Ensuite, il faut activer le module include de Apache :

```apacheconf
Options +Includes
```

Enfin, nous lançons le filtre qui va examiner les fichiers filtrés précédemment et gérer l'inclusion :

```apacheconf
SetOutputFilter INCLUDES
```

Voici ce que vous obtenez au final dans votre fichier .htaccess :

```apacheconf
<FilesMatch "\.includer\.js$">
  Options +Includes
  SetOutputFilter INCLUDES
</FilesMatch>
```

Créez maintenant dans votre dossier de script un fichier nommé global.includer.js puis créez votre première inclusion.
Exemple en ayant pris le soin de mettre à disposition jquery dans le même dossier que le fichier gérant l'inclusion:

```javascript
<!--#include file="jquery-1.4.4.js">
$('document').ready(function() {
    alert("L'inclusion fonctionne à merveille");
});
```

Avec cet exemple, jquery va être automatiquement inséré avant le script créant l'alerte javascript.

L'inclusion coté serveur peut être très utile aussi dans des fichiers css ou même html !