# Atelier de graphiques statistiques — version GitHub Pages (PWA)

## Publier
1. Copier **tout le contenu de ce dossier** à la racine d'un dépôt GitHub (ou dans un sous-dossier, ex. `docs/`).
2. Settings → Pages → Source : la branche et le dossier choisis.
3. L'applet est alors accessible à `https://<compte>.github.io/<depot>/`. Après une première visite, elle fonctionne **hors ligne** et peut être installée sur tablette ou smartphone (« Ajouter à l'écran d'accueil »).

Fichiers : `index.html` (application), `vendor/plotly-cartesian.min.js` (moteur de graphiques, hébergé localement : aucun service tiers), `sw.js` + `manifest.webmanifest` + icônes (mode hors ligne / installation), `.nojekyll`.

Pour publier une mise à jour, remplacer les fichiers : le cache se renouvelle automatiquement (le nom du cache change avec le contenu de `index.html`).

## Intégrer dans Moodle
Utiliser le fichier **autonome** `atelier-graphiques_moodle.html` (un seul fichier, aucun accès réseau) :
- Ressource « Fichier » (affichage « Intégrer » ou « Dans une fenêtre »), ou
- Ressource « URL » pointant vers la version GitHub Pages, affichée dans une page.
À tester dans votre Moodle : la mémorisation des réglages d'affichage (localStorage) peut être bloquée selon la configuration ; l'applet prévient alors l'utilisateur et fonctionne normalement.

## Limites de l'outil
CSV uniquement (UTF-8 ou Windows-1252 ; séparateur tabulation, point-virgule ou virgule détecté automatiquement). 10 Mo, 200 000 lignes, 2 000 colonnes et 5 millions de cellules au maximum. Ces constantes sont dans `LIMITS` (src/data.js).

## Reconstruire
`node build.mjs` à partir des sources (dossier `src/`, polices dans `fonts/`, Plotly dans `vendor/`).
Polices : Atkinson Hyperlegible et OpenDyslexic (licence SIL OFL 1.1, textes dans `fonts/`). Moteur de graphiques : plotly.js 4.2.0 (MIT).
