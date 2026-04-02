# Orbisite API (contenu client)

Ce dépôt contient les données **éditables par le client** pour le site Orbisite. Le code et la structure des pages (blocs, ordre) sont dans le dépôt `orbisite.github.io`.

## Fichiers

| Fichier | Rôle |
|--------|------|
| `content.json` | Textes, titres, liens, images par section (dont pied de page : `linkHrefs`, `socials`) |
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

## Liens CTA (navbar, hero, tarifs)

| Clé | Emplacement | Rôle |
|-----|-------------|------|
| **`navbar.ctaHref`** | `navbar` | URL du bouton principal de la barre (ex. `#contact`, `mailto:…`) |
| **`hero.ctaHref`** | `hero` | URL du bouton sous le titre du hero (ex. `#pricing`) |
| **`pricing.planCtaHref`** | `pricing` | URL par défaut des boutons de **tous** les plans tarifaires |
| **`ctaHref` sur un plan** | `pricing.plans[]` | Optionnel : remplace `planCtaHref` pour ce plan uniquement |

Les ancres du menu (`navbar.links[].href`), les cartes bento (`bento.items[].href`) et le pied de page (`linkHrefs`, `socials`) sont déjà entièrement dans le JSON.

## Pied de page (`footer`)

- **`privacy`**, **`terms`**, **`contact`** : libellés bilingues des trois liens.
- **`linkHrefs`** (optionnel) : URLs pour ces trois liens — clés `privacy`, `terms`, `contact` (chaînes, ex. `"#"` ou `"/mentions"`).
- **`socials`** (optionnel) : tableau `{ "label": { "fr": "…", "en": "…" }, "href": "https://…" }`. Si absent, le site utilise des réseaux par défaut (placeholders).
- **`links`** (optionnel) : remplace entièrement les trois liens par une liste `{ "label": { "fr", "en" }, "href" }[]` si vous voulez un autre nombre ou ordre de liens.

## Tarifs : plan mis en avant

Dans `pricing`, le champ **`highlightedPlan`** (nombre entier, **à partir de 0**) indique quel plan a le style « recommandé » (bordure / bouton plein). Ex. `0` = premier plan (souvent « Base »), `1` = deuxième, etc.

## Domaine (CNAME)

Le domaine personnalisé est configuré par Orbisite dans le dépôt du site (`public/CNAME`), pas ici.

## Mise à jour

Après chaque push sur `main`, GitHub Raw sert les fichiers à jour. Le site les charge au chargement de la page (pas besoin de rebuild côté client).
