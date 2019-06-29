---
title: Un article avec des échantillons de code
date: 2019-06-25T22:00:00Z
tags:
- contenu-demo
- code
- blog

---
La meilleure façon de produire une démo d'un article de code, c'est afficher un article dans la vraie vie, aussi regardez celui provenant d'[andy-bell.design](https://andy-bell.design/wrote/creating-a-full-bleed-css-utility/) concernant un utilitaire de CSS full-bleed.

- - -

Il peut vous arriver de vouloir sortir vos composants des contraintes dans lesquels ils se trouvent embarqués. Une situation commune où cela arrive : quand vous n'avez pas beaucoup de contrôle du conteneur dans lequel il existe, par exemple l’aire du contenu principal d'un CMS.

C'est même encore plus le cas avec des outils d'édition comme l'[éditeur Gutenberg de WordPress](https://wordpress.org/gutenberg/), où en théorie, vous pourriez extraire un composant d'un système de design et l'utiliser dans le contenu principal de votre page web. Dans de telles situations, il peut être très utile d’avoir un petit utilitaire qui fera que l'élément prend 100% de la largeur de la fenêtre de visualisation _et_ conserve son flow dans son conteneur parent.

C'est à ce moment-là que je sors de mon chapeau la classe utilitaire `.full-bleed`.

## L'utilitaire `.full-bleed`

Il est petit, mais vraiment puissant : 

```css
.full-bleed {
  width: 100vw;
  margin-left: 50%;
  transform: translateX(-50%);
}
```

Ici, il se trouve dans un contexte où il crée un `<aside>` fantaisiste et un élément `<figure>` vidés de leur conteneur parent.

<iframe height="300" style="width: 100%;" scrolling="no" title="Piccalilli CSS Utility — Issue  #2 — Full bleed utility" src="//codepen.io/andybelldesign/embed/Nmxrwv/?height=300&theme-id=dark&default-tab=css,result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  Voir le Pen <a href='https://codepen.io/andybelldesign/pen/Nmxrwv/'>Piccalilli CSS Utility — Issue  #2 — Full bleed utility</a> d'Andy Bell
  (<a href='https://codepen.io/andybelldesign'>@andybelldesign</a>) sur <a href='https://codepen.io'>CodePen</a>.
</iframe>

L'utilitaire `.full-bleed` donne une proéminence à ces éléments et point important, il conserve leur place sémantique dans la page. Tout comme j'aime.

- - -

🔥 **Pro truc** : Au moment de travailler avec un utilitaire comme `.full-bleed`, c'est une bonne idée d'ajouter un conteneur interne qui ait un `max-width` et une marge horizontale auto comme suit : 

```css
.wrapper {
  max-width: 50rem;
  margin-left: auto;
  margin-right: auto;
}
```

Disposer d'un container comme `.wrapper` aide à créer un contenu cohérent et centré.

- - -

### Comment fonctionne l'utilitaire `.full-bleed`

Nous réglons le contenu pour qu'il soit à `width: 100vw`, ce qui équivaut à la totalité de la largeur du viewport. Nous ne pourrions pas le régler à `width: 100%` car cela ne remplirait que l'espace de son élément parent. La largeur des éléments parents est néanmoins utile, parce qu'en réglant `margin-left: 50%`, nous disons au composant d'aligner son **côté gauche** au centre son élément parent, parce `50%` c'est la moitié de **largeur de l'élément du parent**.

Pour finir, nous utilisons le transformateur CSS   `translateX(-50%)`. Parce que le transform fonctionne en dehors des dimensions de l'élément et pas aux dimenstions du parent, il renverra l'élément à `50vw`, parce qu'il fait `100vw` de large, faisant par conséquent qu'il s'aligne parfaitement avec les bords de la fenêtre viewport

## Emballé

Espérons que cette astuce courte et douce vous aidera dans vos projets. Si c'est le cas, envoyez-moi un [tweet](https://twitter.com/andybelldesign), car j'aimerais beaucoup le voir !

The best way to demo a code post is to display a real life post, so check out this one from [andy-bell.design](https://andy-bell.design/wrote/creating-a-full-bleed-css-utility/) about a full bleed CSS utility.

- - -

Sometimes you want to break your components out of the constraints that they find themselves in. A common situation where this occurs is when you don’t have much control of the container that it exists in, such as a CMS main content area.

This is even more the case with editing tools such as the [WordPress Gutenberg editor](https://wordpress.org/gutenberg/), where in theory, you could pull in a component from a design system and utilise it in the main content of your web page. In these situations, it can be pretty darn handy to have a little utility that makes the element 100% of the viewport’s width _and_ still maintain its flow within its parent container.

This is when I normally pull the `.full-bleed` utility class out of my back pocket.

## The `.full-bleed` utility

It’s small, but hella mighty:

```css
.full-bleed {
  width: 100vw;
  margin-left: 50%;
  transform: translateX(-50%);
}
```

Here it is in a context where it makes a fancy `<aside>` and a `<figure>` element bleed out of their parent container.

<iframe height="300" style="width: 100%;" scrolling="no" title="Piccalilli CSS Utility — Issue  #2 — Full bleed utility" src="//codepen.io/andybelldesign/embed/Nmxrwv/?height=300&theme-id=dark&default-tab=css,result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/andybelldesign/pen/Nmxrwv/'>Piccalilli CSS Utility — Issue  #2 — Full bleed utility</a> by Andy Bell
  (<a href='https://codepen.io/andybelldesign'>@andybelldesign</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

The `.full-bleed` utility gives those elements prominence and _importantly_ keeps their semantic place in the page. Just how I like it.

- - -

🔥 **Pro tip**: When working with a utility like `.full-bleed`, it’s a good idea to add an inner container that has a max-width and auto horizontal margin. For this, I normal create a shared `.wrapper` component like this:

```css
.wrapper {
  max-width: 50rem;
  margin-left: auto;
  margin-right: auto;
}
```

Having a container like `.wrapper` helps to create consistent, centred content.  

- - -

### How the `.full-bleed` utility works

We set the container to be `width: 100vw`, which equates to the full viewport width. We couldn’t set it to `width: 100%` because it would only fill the space of its parent element. The parent element’s width _is_ useful though, because by setting `margin-left: 50%`, we are telling the component to align its **left edge** to the center of its parent element, because `50%` is half of the **parent element’s** width.

Finally, we use CSS transforms to `translateX(-50%)`. Because the transform works off the element’s dimensions and not the parent’s dimensions, it’ll pull the element back `50vw`, because it’s `100vw` wide, thus making it sit perfectly flush with the viewport’s edges.

## Wrapping up

Hopefully this short and sweet trick will help you out on your projects. If it does, [drop me a tweet](https://twitter.com/andybelldesign), because I’d love to see it!