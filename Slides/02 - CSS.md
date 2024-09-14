---
marp: true
theme: "themedd"
lang: fr
paginate: true
header: "🌈 CSS, Cascading Stylesheets"
footer: "Gaëtan Ark / EDD 2024-25"
---

<!-- _class: lead-->

# CSS

## Cascading StyleSheets, feuilles de styles en cascade

---

## Rôle de CSS

CSS définit l’apparence des éléments d’un contenu web.

- **Découplage** : HTML gère le contenu, CSS l’apparence ([Participez au CSS Naked Day](https://css-naked-day.github.io/));
- **Maintenabilité** : Une seule page HTML peut avoir des formes visuelles très différentes ([CSS Zen Garden](https://csszengarden.com/tr/fr/218/));
- **Ré-utilisabilité** : un seul document CSS permet de gérer toutes les pages d’un site mais aussi d’autres sites.

CSS est un standard et peu donc être utilisé sur une large palette de _devices_.

---

## Syntaxe

```css
selecteur {
  propriété: valeur
}
```

- **Sélecteur**, les éléments HTML sur lesquels les styles s’appliquent;
- **Propriété**, caractéristique visuelle (la police, la couleur du text, le fond…);
- **Valeur**, la configuration de la propriété, par exemple `serif`, `red`, `#cacaca`;
- La propriété et la valeur sont séparées par un `:`.

---

## Syntaxe, détails

```css
p {
  /* Chaque ligne est séparée par un `;` */
  color: blue;
  font-weight: bold;
}
```

---

## Et comment l’utiliser ?

1. CSS externes dans un fichier lié au document `html`;
2. CSS _inline_;
3. CSS _internes_.

---

## Comme fichier externe

Pratique idéale, permet de bien séparer le contenu et l’aspect visuel et de utiliser un seul document CSS pour plusieurs pages.

```html
<head>
  <link rel="stylesheet" href="monfichier.css">
</head>
<body>
  <p>Test</p>
</body>
```

```css
/* monfichier.css */
p {color: orange}
```

---

## Autres méthodes

Méthodes existantes mais **à éviter autant que possible**.

```html
<!-- Styles inline-->
<p style="color: orange">Exemple de styles inline</p>
```

```html
<!-- Styles internes -->
<p>Exemple de styles internes</p>
<style>
  p {color: orange}
</style>
```

---

## Essayons toutes ces méthodes

Dans un nouveau projet, faites trois pages html et pour chacune essayez d’appliquer des styles avec ces trois méthodes.

---

<!-- _class: invert -->

## La sélection en CSS

---

## Les sélecteurs basiques

- Par nom d’élément (`body,p,h1,h2…,section`);
- Par `class` (`.class`);
- Par `id` (`#id`);

---

## La sélection par nom d’élément

```css
body {
  margin: 0;
  background-color: white;
}
p {
  color: orange
}
```

- Le `body` sera sans marge et son fond sera blanc;
- Tous les `p` seront oranges.

---

## La sélection par `class`

```css
.big {
  font-size: 3rem
}
.small {
  font-size: 1rem
}
```

```html
<p class="big">Ce texte sera grand</p>
<p class="small">Ce texte sera plus petit</p>
<section class="small"><p>Ce texte sera plus petit aussi</p></section>
```

Permet de sélectionner des ensembles d’éléments portant un même attribut `class`.

---

## La sélection par `id`

```css
#header-logo { color: blue }
#footer-logo { color: orange }
```

```html
<!-- L’id est unique : un seul élément avec un même id par page -->
<h2 id="header-logo">Logo entête</h2>
<h2 id="footer-logo">Logo pied de page</h2>
```
---

## À propos de la sélection par `id`

La sélection par `id` est aujourd’hui considérée comme une **mauvaise pratique** mais est parfois utilisée en JavaScript.

---

## Quand utiliser quel sélecteur ?

- **Pas de sélection par `id` en CSS, sauf si vous avez plus de 35 ans**;
- La sélection par `class` sera votre alliée pour la vie;
- La sélection par élément (balise ou _tag_) est utilisée pour _initialiser_ des styles génériques sur des familles d’éléments;

---

## 🤑 Héritage

Principe par lequel des propriétés sont naturellement **_transmises_** d’un élément parent vers un élément enfant.

Des propriétés sont _héritables_, comme la couleur du texte, l’interlignage, l’inter-lettrage et d’autres ne seront jamais héritées (marges, fonds).

---

## Exemple d’héritage

```html
<p>Un simple paragraphe</p>
<section>
  <p>Un autre paragraphe, enfant de l’élément section</p>
</section>
```

```css
section { color: orange }
```

Le second paragraphe aura une couleur orange dont il _hérite_ de son parent l’élément `section`.

---

<!-- _class: alt -->

## 🌊 Cascade, le _C_ de CSS

L’aspect d’un élément est déterminé par plusieurs règles qui le concernent : 

- Spécificité (force) des sélecteurs ou héritages;
- L’ordre d’apparence de ces règles;
- L’importance forcée (`!important`);

---

## Cascadons

Dans l’exemple qui suit, décrivez l’apparence du texte qui dit «Bonjour».

---

```html
<body>
  <section>
    <h2 class="small">Bonjour</h2>
  </section>
</body>
```

```css
body { font-family: Inter, sans-serif }
section { font-family: serif }
h2 { color: blue }
.small { font-size: 1rem }
```

---

## 🎡 Letz goooo

1. Nouveau projet;
2. Une fiche d’identité présentant les informations suivantes : Nom, prénom, photo, rôle, nom de l’entreprise, un lien de contact;

- [La maquette, sur Figma](https://www.figma.com/design/wXZtKEBG4Ka3v6GFI9m7lr/Untitled?node-id=0-1&t=t8E9SKFFiZTPT0K3-1)

---

## Références

- [CSS Diner, un jeu sur la sélection CSS](https://flukeout.github.io/);
- [CSS Battle, si tu aimes jouer](https://cssbattle.dev/) pas le meilleur endroit pour apprendre les bonnes pratiques;
- [Un document complet à propos des sélecteurs CSS (en)](https://selectors.sandroroth.com/);
- [Un speedrun ?](https://css-speedrun.netlify.app/)

---
