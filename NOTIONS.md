# 📚 Les notions du portfolio

Chaque notion utilisée sur le site, expliquée simplement, avec l'endroit où la voir.

## HTML

### La structure d'une page
`<head>` contient ce qui ne s'affiche pas (titre de l'onglet, description pour
Google, polices, feuille de style) ; `<body>` contient la page visible.
→ [index.html](index.html)

### Les balises « qui ont un sens » (sémantiques)
`<header>`, `<main>`, `<section>`, `<article>`, `<nav>`, `<footer>` : elles disent
**ce qu'est** un bloc, pas seulement à quoi il ressemble. Ça aide les lecteurs
d'écran et Google. Chaque projet est un `<article class="card">`.
→ [index.html](index.html), section `#projects`

### La balise `viewport`
`<meta name="viewport" content="width=device-width, …">` : sans elle, un
téléphone affiche la page comme sur un ordinateur, en tout petit.

### Les ancres (`href="#projects"`)
Un lien vers `#projects` fait défiler jusqu'à l'élément qui a `id="projects"`.
→ le bouton « Voir mes projets »

### Images et vidéos accessibles
- `alt` décrit une image à qui ne la voit pas ; `aria-label` fait pareil pour une vidéo.
- `<figure>` + `<figcaption>` : une image et sa légende, liées ensemble.
- `loading="lazy"` : l'image n'est téléchargée que quand on s'en approche.
→ les captures de Manga Tracker et Biboubook

### Une vidéo qui se lance toute seule
`autoplay muted loop playsinline` : les navigateurs n'acceptent la lecture
automatique que si la vidéo est **muette** ; `playsinline` évite que l'iPhone
l'ouvre en plein écran. `poster` = l'image affichée avant le chargement.

## CSS

### Les variables (`--fond`, `--moutarde`…)
Définies une fois dans `:root`, utilisées partout avec `var(--fond)`. Changer
une couleur du site = changer une seule ligne.
→ [style.css](style.css), tout en haut

### `box-sizing: border-box`
La largeur d'un bloc inclut ses marges intérieures et sa bordure : les tailles
deviennent prévisibles.

### Centrer le contenu : `.container`
`max-width` + `margin: 0 auto` : le texte ne s'étale pas sur tout un grand écran.

### La grille des projets (CSS Grid)
`repeat(auto-fit, minmax(300px, 1fr))` : autant de colonnes qu'il en tient, chacune
d'au moins 300 px. Une seule sur téléphone, plusieurs sur ordinateur, sans `@media`.
→ `.projects-grid`

### Flexbox
Aligner des éléments en ligne ou en colonne. Dans une carte, `flex: 1` et
`margin-top: auto` poussent la petite note grise tout en bas.
→ `.card`, `.card-body`, `.private-note`

### La rangée de captures qui défile
`overflow-x: auto` permet de faire défiler horizontalement ; `scroll-snap` arrête
le défilement pile sur une capture.
→ `.screens`

### Le format d'un écran de téléphone
`aspect-ratio: 9 / 19.5` garde la forme d'un écran ; `object-fit: cover` remplit
le cadre sans déformer l'image.

### S'adapter aux petits écrans (`@media`)
`@media (max-width: 600px) { … }` : des règles qui ne s'appliquent que sur un
écran étroit.

### Les polices Google Fonts
`preconnect` ouvre la connexion au serveur des polices en avance, pour qu'elles
arrivent plus vite. Fraunces pour les titres, Inter pour le texte.

## Publication

### GitHub Pages
Un dépôt nommé `<pseudo>.github.io` est publié automatiquement à cette adresse.
**Chaque push sur `main` met le site en ligne** : on travaille donc sur une
branche, on vérifie en local, puis on fusionne.

### Voir le site en local
`python3 -m http.server` dans le dossier, puis ouvrir http://localhost:8000.
Ouvrir directement `index.html` marche aussi, mais un vrai petit serveur se
comporte comme le site en ligne.

---

*Dernière mise à jour : 17 novembre 2026 (ajout de TwoBook).*
