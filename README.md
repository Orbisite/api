# Orbisite API (contenu client)

Ce dépôt contient les données **éditables par le client** pour le site Orbisite. Le code et la structure des pages (blocs, ordre) sont dans le dépôt `orbisite.github.io`.

## Fichiers

| Fichier | Rôle |
|--------|------|
| `content.json` | Textes, titres, liens, images par section |
| `theme.json` | Couleurs primary / secondary / neutral + images par défaut |
| `site.json` | Titre, description, meta Open Graph / Twitter, favicon |
| `img/` | Fichiers images (référencés par nom dans les JSON) |

## Images

Dans `content.json` et `theme.json`, les champs peuvent mentionner soit une **URL absolue** (`https://...`), soit un **nom de fichier** présent dans `img/`.

## Domaine (CNAME)

Le domaine personnalisé est configuré par Orbisite dans le dépôt du site (`public/CNAME`), pas ici.

## Mise à jour

Après chaque push sur `main`, GitHub Raw sert les fichiers à jour. Le site les charge au chargement de la page (pas besoin de rebuild côté client).
