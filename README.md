# Marketplace : HTML + Tailwind CSS

## Objectif

Créer une page de type “Marketplace” simple, propre et responsive:

- Header avec titre et bouton “Se déconnecter”
- Menu horizontal avec hover
- Grille de cartes produits cliquables (image, titre, description, prix)
- Palette limitée à deux couleurs sur fond clair (beige/blanc cassé)

## Contenu de la page

- Header: titre + avatar rond + bouton de déconnexion
- Menu: éléments horizontaux avec transition de couleur au survol
- Main: section “Galerie d’articles” affichée en grille responsive (1/2/3 colonnes)
- Cartes: image en haut, titre, description courte, prix; carte entière cliquable (href="#")
- Footer: mention simple

## HTML

- Balises sémantiques: header, nav, main, section, footer
- Accessibilité minimale: alt sur toutes les images produits; aria-label possible sur nav

## Tailwind CSS (classes utilisées – base)

- Couleurs/fond: bg-yellow-50, bg-white, text-gray-800/900
- Espacements: px-4, py-4, p-4, gap-6, mb-6
- Layout: flex, items-center, justify-between, grid, grid-cols-1, sm:grid-cols-2, lg:grid-cols-3
- Bordures/arrondis: border, border-gray-200, rounded, rounded-lg, rounded-t-lg
- Ombres/transitions: shadow-sm, hover:shadow-md, transition-colors, transition-shadow
- Typo: text-sm, text-xl, font-semibold, font-bold
- Bouton: bg-indigo-600 hover:bg-indigo-700 text-white rounded

## Arborescence

- index.html
- img/
  - avatar.png
  - laptop.jpg (ou images Unsplash via URLs)

## Bonnes pratiques

- Palette limitée à 2 couleurs principales au maximum pour la cohérence
- Fond clair: beige/blanc cassé (bg-yellow-50)
- Menu: hover visible (couleur + fond léger)
- Cartes: ombre légère + hover:shadow-md, bords arrondis, marges/padding réguliers
- Images: chemins relatifs corrects (./img/…), noms sans espaces/accents
- Responsive: grid 1/2/3 colonnes, tester la fenêtre réduite

## Extraits utiles

Header + bouton

```html
<header class="bg-yellow-200 border-b border-yellow-300">
  <div class="max-w-6xl mx-auto px-4 py-4 flex items-center justify-between">
    <h1 class="text-2xl font-semibold">Marketplace</h1>
    <button
      class="bg-indigo-600 hover:bg-indigo-700 text-white text-sm font-semibold px-4 py-2 rounded transition-colors"
    >
      Se déconnecter
    </button>
  </div>
</header>
```

Menu avec hover

```html
<nav class="bg-white border-b border-gray-200">
  <ul class="max-w-6xl mx-auto px-4 flex flex-wrap">
    <li>
      <a
        href="#"
        class="block px-5 py-3 text-sm text-gray-700 hover:text-indigo-700 hover:bg-indigo-50 transition-colors"
        >Accueil</a
      >
    </li>
    <li>
      <a
        href="#"
        class="block px-5 py-3 text-sm text-gray-700 hover:text-indigo-700 hover:bg-indigo-50 transition-colors"
        >Nouveautés</a
      >
    </li>
    <li>
      <a
        href="#"
        class="block px-5 py-3 text-sm text-gray-700 hover:text-indigo-700 hover:bg-indigo-50 transition-colors"
        >Populaires</a
      >
    </li>
  </ul>
</nav>
```

Carte produit

```html
<a
  href="#"
  class="bg-white border border-gray-200 rounded-lg shadow-sm hover:shadow-md transition-shadow"
>
  <img
    src="./img/laptop.jpg"
    alt="Ordinateur portable"
    class="w-full h-40 object-cover rounded-t-lg"
  />
  <div class="p-4">
    <h3 class="font-semibold text-gray-900">Titre produit</h3>
    <p class="text-sm text-gray-600 mt-2">Brève description.</p>
    <p class="mt-3 font-semibold text-gray-900">199,00 €</p>
  </div>
</a>
```
