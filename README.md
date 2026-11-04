# Carte de la défavorisation, Laurentides

Carte web interactive de l'indice de défavorisation matérielle et sociale
(Pampalon) pour les 89 municipalités et territoires non organisés de la
région des Laurentides. Réalisée dans le cadre de la formation
C.A.R.T.O.S. (QGIS, Leaflet et GitHub Pages).

## Voir les cartes

| Version | Lien | Contenu |
|---|---|---|
| Carte de formation | [carte_defavorisation3.html](https://eranlorob-dotcom.github.io/carte-laurentides2/carte_defavorisation3.html) | Choroplèthe, popups et légende : le résultat du module 3 |
| Carte d'analyse | [carte_defavorisation_plus.html](https://eranlorob-dotcom.github.io/carte-laurentides2/carte_defavorisation_plus.html) | Panneau d'analyse, filtres par MRC, matrice matérielle × sociale, analyse de proximité, exports |

## Contenu du dépôt

| Fichier | Rôle |
|---|---|
| `carte_defavorisation3.html` | Carte de base construite pas à pas au module 3 |
| `carte_defavorisation_plus.html` | Version enrichie qui montre les capacités natives de Leaflet, sans extension |
| `laurentides_defavorisation.js` | Les données : GeoJSON des municipalités précédé de `const donnees =`, partagé par les deux cartes |
| `README.md` | Ce fichier |

## Données

- **Indicateur :** indice de défavorisation matérielle et sociale (Pampalon), données 2016
- **Classes :** quintiles régionaux calculés parmi les 89 municipalités (Q1 = moins défavorisé, Q5 = plus défavorisé)
- **Champs :** `code_mun`, `nom_mun`, `defav_mat_quintile`, `defav_soc_quintile`
- **Préparation :** jointure du tableau des indices aux limites municipales, puis export en GeoJSON (EPSG:4326) dans QGIS
- **Fonds de carte :** gouvernement du Québec (carte de base et orthoimagerie)

## Lecture et limites

- Un quintile est un rang relatif à la région, pas une mesure absolue.
- La valeur municipale masque les écarts entre les secteurs d'une même municipalité.
- Les données proviennent du recensement de 2016.
- Dans la carte d'analyse, les quintiles moyens par MRC sont indicatifs : ils ne sont pas pondérés par la population.

## Mettre à jour les données

1. Exporter le nouveau GeoJSON depuis QGIS (EPSG:4326), avec les mêmes noms de champs.
2. Ajouter `const donnees =` au tout début et `;` à la fin, puis enregistrer sous `laurentides_defavorisation.js`.
3. Sur GitHub : Add file > Upload files, déposer le fichier (il remplace l'ancien), Commit changes.
4. Attendre 1 à 2 minutes : les deux cartes se mettent à jour.

## Outils

QGIS · Leaflet 1.9.4 · GitHub Pages

## Crédits

Santé Québec Laurentides, Direction de santé publique · Formation C.A.R.T.O.S. · Mise à jour : 2026-11-04
