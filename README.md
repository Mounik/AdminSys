# Un kit de démarrage simple pour Eleventy

Hylia est un kit de démarrage léger [Eleventy](https://11ty.io) avec [Netlify CMS](https://www.netlifycms.org/) pre-configuré, afin que vous puissiez installer en un clic un blog évolutif et une [app web progressive](https://frank.taillandier.me/2016/06/28/que-sont-les-progressive-web-apps/) en quelques minutes. Ce kit vous donne un point de démarrage bien organisé pour évoluer.
Démarrez maintenant en **[déployant Hylia vers Netlify.][deploy-to-netlify]**

[![Déployer vers Netlify](https://www.netlify.com/img/deploy/button.svg)][deploy-to-netlify]

<img src="https://hankchizljaw.imgix.net/hylia-github.jpg?auto=format&q=60" width="550" />

[![Statut Netlify](https://api.netlify.com/api/v1/badges/efd9e384-1d0b-4c13-8dcf-14472859be46/deploy-status)](https://app.netlify.com/sites/hylia-master/deploys)

## Fonctionnalités 

Les fonctionnalités d'Hylia version 0.3.1 :

✍️ Un [CMS Netlify](https://www.netlifycms.org/) pré-configuré  
🎨 des design tokens personnalisables et que vous pouvez créer vous-mêmes 
🌍 Données globales et navigation personnalisable  
📂 Tags et archives de mots-clés
✅ Web app progressive, sémantique et accessible 
🎈 Front-en _super_ léger
🚰 Système CSS motorisé par Sass avec un utilitaire générateur de classe
⚙️  Service worker qui met en cache les pages afin que les personnes puissent lire vos articles hors-ligne 
🚀 Un flux RSS feed pour vos articles 

## Plan de route 

💬 Commentaires motorisés par des [Formulaires Netlify](https://www.netlify.com/docs/form-handling/) 
💡 Bascule mode Nuit/Jour
🗣 Webmentions  
📖 Pagination  
🐦 intégration API de partage Web  
🗒 Mode hors-ligne avec des liens vers les pages mises en cache
📄 Site de documentation 
💅 Documentation propre à Sass 
✍️ Documentation propre au CMS 
🖼 Une facilité afin que vous puissiez ajouter votre logo / marque 

***

## Démarrage 

### Méthode un : Déploiement en Un-Clic vers Netlify

Vous pouvez [déployer Hylia vers Netlify en un clic][deploy-to-netlify] et votre site sera live en quelques minutes ! 

[![Déployer vers Netlify](https://www.netlify.com/img/deploy/button.svg)][deploy-to-netlify]

Andy Bell a enregistré une rapide vidéo de son déploiement d'Hylia ver Netlify pour paramétrer le Gestionnaire de Contenu. [Regardez-la ici](https://youtu.be/0hM_0BH-Y_A).


### Méthode deux : Cloner / Forker

1. Clonez ou forkez ce repo : `git clone https://github.com/christopheducamp/hylia-master`
2. `cd` à l'intérieur du répertoire du projet et lancez `npm install`
3. Une fois toutes les dépendances installées, lancez `npm start`
4. Ouvrez votre navigateur sur `http://localhost:8080` et partez naviguer !

## Commandes de Terminal

### Servir le site localement

```bash
npm start
```

### Construire une version de production du site

```bash
npm run production
```

### Compiler Sass

```bash
npm run sass:process
```

### Re-générer les design tokens pour Sass

```bash
npm run sass:tokens
```

## Démarrer avec le CMS

Avant de pouvoir utiliser le CMS, vous devrez faire un peu de config dans Netlify. Heureusement, ils fournissent un [guide très pratique pour démarrer](https://www.netlify.com/docs/identity/).

En résumé,

- Une fois que vous avez installé le site sur Netlify, allez sur “Settings” > “Identity” et activez Identity
- Descendez vers l'aire “Git Gateway”, cliquez sur “Enable Git Gateway” et suivez les étapes
- Cliquez sur l'onglet “Identity” tout en haut
- Une fois que vous avez activé  Identity, cliquez sur “Invite Users”
- Regardez le lien invite dans votre boîte de réception et cliquez le lien dans l'e-mail qui vous a été envoyé
- Réglez un mot de passe dans la boîte popup
- Allez sur `/admin` de votre site et connectez-vous
- Vous êtes prêt pour éditer votre contenu !

## Tokens de Design et Guide de Style

### Tokens de Design 

Bien qu'Hylia ait un joli design vraiment simple, vous pouvez configurer les tokens de design du noyau afin de contrôler les couleurs, le ratio de taille et les fontes.

***

**Note**: *Le crédit doit être donné au dur travail de [Jina Anne](https://twitter.com/jina) pour avoir fait même exister le concept des tokens de design. Vous devriez regarder [cette  vidéo](https://www.youtube.com/watch?v=wDBEc3dJJV8), puis  [lisez cet article](https://the-pastry-box-project.net/jina-bolton/2015-march-28) et puis enregistrez-vous sur [ce cours](https://aycl.uie.com/virtual_seminars/design_tokens_scaling_design_with_a_single_source_of_truth) afin d'améliorer votre connaissance..*

***

Pour modifier les tokens de design dans le CMS, trouvez le “Globals” dans la barre latérale puis dans les options présentées, sélectionnez “Theme Settings”.

Pour modifier directement les tokens de design, éditez [_src/data/tokens.json](https://github.com/christopheducamp/hylia-master/blob/master/src/_data/tokens.json).

Les tokens sont convertis en cartes que le Sass utilise pour compiler le front-end CSS, aussi assurez vous de maintenir la structure correcte du fichier `tokens.json`. 

### Guide de Style 

Votre version d’Hylia est livrée avec un guide de style par défaut. Vous pouvez regarder une démo du Styleguide sur  <https://hylia.website/styleguide/>.

Vous pouvez éditer le Styleguide en ouvrant [src/styleguide.njk](https://github.com/christopheducamp/hylia-master/blob/master/src/styleguide.njk). Si vous ne voulez pas du  Styleguide, effacez ce fichier et la page disparaîtra.

## Sass

Hylia est basé sur la version [WIP v2 de Stalfos](https://github.com/andybelldesign/stalfos/tree/feature/v2), qui n'a pas de documentation à cette heure (je sais, c'est mal). Voici une documentation très basique pour les éléments du nouveau framework que vous rencontrerez sur ce projet.

### Configuration

Le système global Sass est motorisé par le fichier de configuration centrale, déposé ici : [_src/scss/_config.scss](https://github.com/ChristopheDucamp/hylia-master/blob/master/src/scss/_config.scss).

Avant que Sass ne soit compilé, un fichier `_tokens.scss` est généré à partir de la [config des tokens de design](https://github.com/ChristopheDucamp/hylia-master/blob/master/src/_data/tokens.json) qui est requise.

Éléments-clés 

- `$stalfos-size-scale` : Un jeton pour piloter l'échelle de taille qui, par défaut, est une échelle “Major Third”
- `$stalfos-colors` : Un jeton pour piloter une carte de couleurs
- `$stalfos-util-prefix` : Tous préconstruits, les utilitaires de framework auront ce préfixe. Exemple : l'utilitaire wrapper est '.sf-wrapper' parce que le préfixe par défaut est 'sf-'
- `$metrics` : Différentes métriques à utiliser sur l'ensemble du site
- `$stalfos-config` : Ceci motorise tout, de la génération d'utilitaire de classe jusqu'aux breakpoints pour activer/désactiver les composants/utilitaires pré-construits.

### How to create a new utility class with the generator

Le générateur de classes d’utilitaires vous permet de générer ce que vous voulez, sans donner d'avis sur le nom ou les propriétés de la classe.

Pour ajouter une nouvelle classe, ajoutez un autre élément à la carte existante `$ stalfos-config`. Cet exemple ajoute un utilitaire pour les éléments flottants.

```scss
'float': (
  'items': (
    'left': 'left',
    'right': 'right'
  ),
  'output': 'responsive',
  'property': 'float'
)
```

L'`output` est défini sur `responsive`, ce qui signifie que chaque point d'arrêt générera une classe préfixée pour elle-même. Si vous voulez seulement que les éléments flottent à gauche dans le point d'arrêt `md`, vous devriez maintenant ajouter une classe de `md: float-left` à vos éléments HTML.

Si vous souhaitez uniquement générer des classes d'utilitaires standard, réglez `output` sur `standard`.

### Fonctions

#### `get-color($key)`

Function tries to match the passed `$key` with the `$stalfos-colors` map. Returns null if it can’t find a match.

#### `get-config-value($key, $group)`

Returns back a 1 dimensional (key value pair) config value if available.

#### `get-size($ratio-key)`

Function tries to match the passed `$ratio-key` with the `$stalfos-size-scale`. Returns null if it can’t find a match.

### Mixins

#### `apply-utility($key, $value-key)`

Grabs the property and value of one of the `$stalfos-config utilities` that the generator will generate a class for.

#### `media-query($key)`

Pass in the key of one of your breakpoints set in `$stalfos-config['breakpoints']` and this mixin will generate the `@media` query with your configured value.

## CMS

Hylia dispose du [CMS Netlify](https://www.netlifycms.org/) pre-configuré en standard. Vous pouvez le personnaliser en modifiant [`src/admin/config.yml`](https://github.com/christopheducamp/hylia-master/blob/master/src/admin/config.yml).

### Contenu que vous pouvez modifier

Le réglage basique du CMS vous permet de modifier ce qui suit :

- **Page d'Accueil** : Éditez le contenu de votre page d'accueil
- **Posts** : Créez et éditez les posts de blog
- **Pages Génériques** : Créez des pages génériques qui utilisent un layout similaire aux posts
- **Global site data** : Différents fragments de données globables du site telles que votre url, le titre, le nombre de posts par page et les détails de l'auteur.
- **Navigation**: Editez vos éléments primaires de navigation
- **Theme**: Modifiez les tokens de design qui motorisent le thème du site

## Venez m'aider 

Ce projet est _super_ neuf et votre feedback sera le bienvenu. Afin que les choses puissent tourner en douceur, regardez SVP le [guide de contribution et le code de conduite](https://github.com/christopheducamp/hylia-master/blob/master/contributing.md).

Les trucs où j'attends de l'aide sont : 

- Documentation en français 
- [Webmentions](https://www.w3.org/TR/webmention/)
- Performance
- Micropub

[deploy-to-netlify]: https://app.netlify.com/start/deploy?repository=https://github.com/christopheducamp/hylia-master&stack=cms


