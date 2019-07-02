---
title: Poster avec le CMS Forestry
date: 2019-07-02
tags:
- CMS Forestry

---
Sur la recommandation de [Frank Taillandier](https://frank.taillandier.me "https://frank.taillandier.me"), je poste cet article à partir de l'interface-utilisateur du [CMS Forestry](https://forestry.io "forestry.io").

Importé ce site `Hylia-master` -en suivant les indications après avoir cliqué sur Add site, puis _Others (importeur générique pour tout dépôt Git)_.

[Configuration d'un gabarit](https://forestry.io/docs/settings/front-matter-templates/ "Template Front Matter pour Forestry") créé à partir d'un article existant.

Configuration de la barre latérale pour afficher les différentes sections du site :

* les articles,
* la page d'accueil,
* les données (fichiers JSON),
* le README (affiché en lecture seule).

Interface minimaliste et réactive : l'écran est pensé pour éditer d'un côté le front matter et de l'autre l'édition au format Markdown.

![](/images/forestry-cms.png)

Après une modification d'un simple clic, on peut voir le rendu final sur une URL dédiée. En coulisse, l'image Docker Node qui a fait tourner la commande `eleventy --serve` en arrière plan va déclencher la régénération, l'opération ne prend que quelques secondes.

Forestry se synchronise avec le dépôt Git en arrière-plan. Le déploiement est déclenché automatiquement du côté de chez Netlify.