# Choco Traiteur Paella

Site vitrine statique de **CHOCO TRAITEUR PAELLA**, traiteur pour manifestations (mariages,
baptêmes, anniversaires, associations) : paëlla, couscous, tartiflette, à domicile ou à emporter,
secteur Guérard et Meaux (77).

## Stack

HTML, CSS et JavaScript natifs. Aucune dépendance, aucune étape de build, aucune requête
vers un service externe hormis la carte OpenStreetMap de la section « Zone d'intervention ».

```
index.html                     page unique, sections ancrées, sprite d'icônes inline, JSON-LD LocalBusiness
assets/css/styles.css          variables de thème, layout, mode sombre, responsive (640px / 1024px)
assets/js/main.js              menu mobile, apparition au défilement, année du footer
assets/img/logo.svg            poêle à paëlla + wordmark CHOCO, couleur (fond clair)
assets/img/logo-mono-blanc.svg même logo en blanc (footer sombre)
assets/img/favicon.svg         pastille poêle à paëlla seule, carrée
robots.txt / sitemap.xml       référencement
source-choco-traiteur-paella.jpg photo du camion, source des données, non référencée par le site
```

Le sprite d'icônes est inline dans `index.html` : un `<use href="fichier.svg#id">` externe
n'est pas supporté partout et échoue en `file://`.

## Développement local

```sh
python3 -m http.server 8000
# puis http://localhost:8000
```

## Production

https://choco-traiteur-paella.vercel.app/

## Données utilisées

| Champ | Valeur | Source |
|---|---|---|
| Nom | CHOCO TRAITEUR PAELLA | camion |
| Prestations | Paëlla, couscous, tartiflette, etc. ; domicile ou à emporter ; devis sur demande | camion |
| Événements | Mariage, baptême, anniversaire, associations | camion |
| Téléphone | 07 78 71 31 69 | camion |
| Email | choco.traiteur.paella@gmail.com | camion |
| Commune | Guérard (77580), à proximité de Meaux | annuaire tiers evenementielpourtous.com |
| Centre de la carte | 48.8128, 2.9533 (centre de la commune) | geo.api.gouv.fr |
| SIREN, forme juridique, APE, siège, dirigeant | introuvables | recherche-entreprises.api.gouv.fr, 15/09/2026 |

## TODO restants

Chaque point correspond à un commentaire `TODO` dans `index.html`.

- [ ] **Mentions légales** : dénomination officielle, forme juridique, SIREN, SIRET, APE, siège,
      dirigeant, lien Annuaire des Entreprises, directeur de publication, hébergeur.
- [ ] **JSON-LD** : `identifier`, `foundingDate`, `founder`, `streetAddress`, `geo`.
- [ ] **Chiffres clés** : année de création à remplacer une fois la fiche INSEE connue.
- [ ] **Commune et zone** : Guérard vient d'un annuaire tiers, liste des communes à confirmer.
- [ ] **Carte** : recentrer sur les coordonnées officielles du siège.
- [ ] **Adresse de contact** : adresse du siège.
- [ ] **Modalités** : nombre minimum de parts, matériel, service sur place.
- [ ] **Réassurance** : « fait maison » / « produits frais » seulement si confirmé.
- [ ] **À propos** : prénom du dirigeant, parcours, année de démarrage.
- [ ] **Image Open Graph** : photo de paëlla réalisée en 1200x630.

## Versions

| Version | Date | Direction visuelle |
|---|---|---|
| v1 | 2026-09-15 | Hero sombre en dégradé braise sur deux colonnes, orange et noir du camion, pastille poêle à paëlla, cartes à icônes rondes |
