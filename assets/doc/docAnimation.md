# Présentation du Projet Vue.js - Collection d'Images

## Description du Projet

Ce projet Vue.js a été créé pour présenter une collection d'images de la série Desert Series. Il est composé de deux pages : une page d'accueil affichant trois images de la collection et une autre page permettant de visualiser l'ensemble des images.

## Objectif du Projet

L'objectif principal de ce projet est de s'initier et de pratiquer les animations CSS. À travers cette application, je cherche à comprendre et à maîtriser différentes techniques d'animations pour améliorer l'expérience utilisateur.

## Utilisation des Animations CSS

Ce projet explore diverses animations CSS pour améliorer l'aspect visuel et l'interaction utilisateur. Voici quelques-unes des animations implémentées :

### Animation Globale

Le fichier `ProjetCollection.vue` comprend une animation globale `slidein2` appliquée à l'ensemble de la structure de l'application. Cette animation est déclenchée lors du chargement de la page.

### Animation de la Page d'Accueil (`Home.vue`)

La page d'accueil utilise l'animation `slidein3` pour l'apparition fluide des éléments au chargement de la page. Cette animation est appliquée aux images et aux boutons pour améliorer l'effet visuel.

### Animation de la Page de Collection (`Collection.vue`)

La page Collection intègre l'animation `slidein` pour animer la transition lors de l'affichage des différentes images de la collection. Cette animation ajoute une dynamique fluide au défilement des images.

## Exemples d'Animations CSS Utilisées

### Animation Globale (`ProjetCollection.vue`)

```css
@keyframes slidein2 {
  from {
    opacity: 0;
    transform: translateY(-200%);
  }
  to {
    opacity: 1;
    transform: translateY(0%);
  }
}
```

### Animation de la Page d'Accueil (`Home.vue`)

```css
@keyframes slidein3 {
  from {
    opacity: 0;
    transform: translateY(200%);
  }
  to {
    opacity: 1;
    transform: translateY(0%);
  }
}
```

### Animation de la Page de Collection (`Collection.vue`)

```css
@keyframes slidein {
  from {
    opacity: 0;
    transform: translateY(200%);
  }
  to {
    opacity: 1;
    transform: translateY(0%);
  }
}
```

## Installation et Utilisation

1. Cloner le dépôt Git.
2. Installer les dépendances avec `npm install`.
3. Lancer l'application avec `npm run serve`.

## Conclusion

Ce projet est une expérience d'apprentissage pour explorer les animations CSS dans le contexte de développement Vue.js. Il vise à améliorer mes compétences en animations et à appliquer ces connaissances dans des projets futurs.

## Auteur

Ce projet a été réalisé par [Hugo Rytlewski](https://www.linkedin.com/in/hugo-rytlewski-b06841281/).
