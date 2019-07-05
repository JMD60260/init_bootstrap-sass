# Bootstrap & Sass

Template et architecture permettant de commencer un projet Bootstrap personnalisable via Sass.
_Installation de Sass pré-requise pour utiliser les fonctions de preprocessing._

>Cliquer sur "Use this template" pour disposer du template dans un nouveau repository.

## Contenu
### bootstrap/
* `mixins/`, `mixins/`, `mixins/` et l'ensemble des fichiers `.scss` dont le nom commence par un _underscore_ (ex : `_variables.scss`) : ensemble des propriétés qui composent le framework de Bootstrap.
* `Bootstrap_loader.scss` : fichier de sélection des propriétés Bootstrap à inclure dans le projet.
* `Bootstrap_over.scss` : fichier de réécriture de variables Bootstrap.
* Local_style.scss : fichier servant à l'ajout de nouvelle propriétés de style.
### style/
* `style.css` : feuille de style définitive appelée par la page html, générée par sass en version développement ou production.
* `style.css.map` : permet à Sass de localiser les erreur au sein des différents fichiers au moment du développement.
### index.html
Starting template Bootstrap implémentant la feuille de style générée par Sass, les CDN JavaScript de Bootstrap et les _meta tags_ nécessaires.

## Développement

1. Modifier le fichier `Bootstrap_loader.scss` et retirer la balise commentaire pour les packages Bootstrap utiles au projet. La sélection de ces paquets permettra d'alléger la feuille de style définitive.
2. Modifier le fichier `Bootstrap_over.scss` afin de personnaliser les différentes variables Bootstrap comme, par exemple, celles concernant les couleurs. Retirer la balise commentaire pour les variables à modifier et procéder ensuite au changement de valeur, en laissant donc intacts les fichiers Sass propres à Bootstrap. Permet une meilleure maintenance du code, avec de possibles retours en arrière.
3. Compléter le fichier `Local_style.scss` pour personnaliser certains éléments de la page. Je recommande l'usage de conventions particulières pour nommer les classes et id des différents éléments appelés, afin d'éviter de confondre les propriété ajoutées avec des propriétés Bootstrap.

## Process

Au niveau du répertoire de votre projet :

```$ sass bootstrap/Bootstrap_loader.scss style/style.css --watch```
> Permet de générer dynamiquement la feuille de style définitive, mise à jour automatiquement à chaque sauvegarde de l'un des fichiers Sass. Génère également la map Sass permettant un rapport d'erreur cohérent avec l'architecture du projet.

```$ sass bootstrap/Bootstrap_loader.scss style/style.css --no-source-map --style=compressed```
> Permet de générer une feuille de style minifiée et adaptée à la mise en production du site.
