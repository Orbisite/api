# Orbisite API (contenu client)

Ce dépôt contient les données **éditables par le client** pour le site Orbisite. Le code et la structure des pages (blocs, ordre) sont dans le dépôt `orbisite.github.io`.

## Fichiers

| Fichier | Rôle |
|--------|------|
| `content.json` | Textes, titres, liens, images par section |
| `theme.json` | Couleurs primary / secondary / neutral |
| `site.json` | Titre, description, meta Open Graph / Twitter, favicon |
| `img/` | Fichiers images (référencés par nom dans les JSON) |

## Images

Dans `content.json` et `site.json`, les références d’images peuvent être une **URL absolue** (`https://...`) ou un **nom de fichier** présent dans `img/`.

## Mise en page des grilles (optionnel)

Sur certains blocs, vous pouvez définir **`columnSpan`** sur un élément (plan tarifaire, carte fonctionnalité, tuile showcase, témoignage) :

| Valeur | Effet (grille 3 colonnes en `lg`) |
|--------|-----------------------------------|
| omis ou `1` | une colonne |
| `2` | deux colonnes |
| `full` ou `3` | toute la largeur du rang |

Exemple : offre « Base » en pleine largeur au-dessus, autres offres en dessous (`"columnSpan": "full"` sur le premier plan).

## Domaine (CNAME)

Le domaine personnalisé est configuré par Orbisite dans le dépôt du site (`public/CNAME`), pas ici.

## Mise à jour

Après chaque push sur `main`, GitHub Raw sert les fichiers à jour. Le site les charge au chargement de la page (pas besoin de rebuild côté client).
