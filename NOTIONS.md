# Notions du portfolio

Les notions utilisées dans ce site, expliquées simplement, avec l'endroit où les voir.

## HTML

- **Structure d'une page** : `<head>` contient les informations pour le navigateur
  (titre de l'onglet, description pour Google, polices) et `<body>` ce qui s'affiche.
  → [index.html](index.html)
- **Balises qui ont du sens** : `<header>`, `<main>`, `<section>`, `<article>`,
  `<footer>`. Elles décrivent le rôle de chaque partie, ce qui aide les lecteurs
  d'écran et Google. Chaque projet est un `<article class="card">`.
  → [index.html](index.html)
- **`<meta name="description">`** : la phrase que Google affiche sous le titre du site.
  → [index.html](index.html)
- **Ancres** : `href="#projects"` fait défiler la page jusqu'à l'élément qui a
  `id="projects"`. → le bouton « Voir mes projets »
- **Images et vidéos** : `alt` (pour une image) et `aria-label` (pour une vidéo) décrivent
  ce qu'on voit, pour les personnes qui ne le voient pas. `loading="lazy"` ne charge une
  image que quand on s'en approche. Une vidéo avec `autoplay muted loop playsinline` se lit
  toute seule, sans son, en boucle, et sans passer en plein écran sur iPhone. `poster` est
  l'image affichée avant qu'elle démarre.
  → les cartes Manga Tracker et Biboubook
- **`<figure>` et `<figcaption>`** : une image avec sa légende. → `.screens`

## CSS

- **Variables** (`--fond`, `--moutarde`…) : les couleurs sont écrites une seule fois
  dans `:root`, puis réutilisées avec `var(--moutarde)`. Changer une couleur partout =
  changer une ligne. → [style.css](style.css)
- **Flexbox** (`display: flex`) : aligne des éléments sur une ligne, comme les boutons
  ou les étiquettes. `flex-wrap: wrap` les fait passer à la ligne s'il manque de place.
  → `.hero-links`, `.tags`
- **Grid** (`display: grid`) : la grille des cartes. `repeat(auto-fit, minmax(300px, 1fr))`
  met autant de colonnes que possible, de 300 px minimum : deux sur ordinateur,
  une sur téléphone, sans rien écrire de plus. → `.projects-grid`
- **`margin-top: auto`** dans une carte en flex colonne : pousse l'élément tout en bas,
  pour que les boutons des cartes soient alignés. → `.card-links`, `.private-note`
- **Media query** (`@media (max-width: 600px)`) : des règles qui ne s'appliquent que
  sur les petits écrans. → fin de [style.css](style.css)
- **Défilement horizontal aimanté** : `overflow-x: auto` + `scroll-snap-type` font
  défiler les captures du doigt, en s'arrêtant pile sur chacune. → `.screens`
- **Pseudo-élément `::after`** : ajoute une décoration sans toucher au HTML, ici le petit
  trait jaune sous les titres. → `section h2::after`
- **Badge arrondi** : `display: inline-block` + `border-radius: 999px` donnent une
  « pilule » juste à la taille du texte. → `.dispo` (alternance), `.tags li`

## Hébergement

- **GitHub Pages** : GitHub publie gratuitement le contenu d'un dépôt nommé
  `<pseudo>.github.io` à l'adresse https://zbiboo.github.io. Chaque `git push` sur `main`
  met le site à jour en une minute environ.
- **Google Fonts** : les polices Fraunces (titres) et Inter (texte) sont chargées depuis
  Google. `preconnect` prépare la connexion plus tôt pour gagner du temps.
  → `<head>` de [index.html](index.html)

## Pièges rencontrés

- **Rester cohérent avec le CV** : le portfolio disait « je suis en formation » alors que
  la formation commence en janvier 2027, avec l'alternance. Un recruteur lit souvent les
  deux : il vaut mieux les relire ensemble à chaque mise à jour.
- **Projets privés** : pas de lien vers le code de Biboubook ni de TwoBook (dépôts privés).
  À la place, une note en bas de carte (`.private-note`) et, si possible, des captures.
