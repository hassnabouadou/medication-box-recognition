# Medication Box Recognition API

Université Mohammed V — Master IT 2025-2026

## Description
Reconnaissance de médicaments par photo : YOLOv8 (détection) + EasyOCR AR/FR/EN
(lecture du texte) + Fuzzy Matching + FastAPI.

## Résultats
- 1548 images testées
- 1411/1548 médicaments identifiés
- 7909 médicaments en base
- 2.78s de latence moyenne

## Lancer le projet
1. Ouvrir `notebook.ipynb` dans Google Colab
2. Activer le GPU T4
3. Adapter les chemins Drive dans la Cellule 1
4. Exécuter toutes les cellules

## API
| Endpoint | Description |
|---|---|
| GET / | Health check |
| POST /recognize | Reconnaître un médicament |
| GET /medicaments | Liste des médicaments |
| GET /stats | Statistiques |

## Méthodologie des données

### Images de test
Les 1548 images de test ont été prises par téléphone, dans des conditions
réelles d'usage : différents angles de prise de vue, distances variables,
éclairage non contrôlé, parfois flou ou bruit. Cela permet d'évaluer le
système dans des conditions proches de l'usage réel plutôt que sur des
photos de studio idéalisées.

### Base de référence (reference.csv)
La base de médicaments combine plusieurs sources pour maximiser la couverture :
- CNOPS (Caisse Nationale des Organismes de Prévoyance Sociale, Maroc) —
  base de référence des médicaments remboursables au Maroc
- Bases de données pharmaceutiques françaises — pour les médicaments
  commercialisés également en France
- Bases de données pharmaceutiques saoudiennes — pour les médicaments
  du marché du Golfe

Ces sources ont été fusionnées et enrichies manuellement avec les noms
arabes (colonne nom_ar) au fil de l'évaluation, pour améliorer le matching
sur les boîtes où seul le texte arabe est lisible.

## Dataset complet et évaluation

GitHub limite la taille des fichiers à 100 MB et déconseille les dépôts
au-delà de 1 GB. Le dataset (1548 photos réelles, environ 4.6 GB) et le
modèle entraîné dépassent cette limite — ils sont hébergés sur Google Drive.

| Ressource | Lien |
|---|---|
| images.zip (dataset brut) | [Télécharger](https://drive.google.com/file/d/1IsofIi3SQOzFgCmCZQLKoqIg-poJN2w5/view?usp=drive_link) |
| Projet complet (modèle, évaluation, graphiques) | [Ouvrir](https://drive.google.com/drive/folders/1sTFDxa_cIG4amYHhW8B4El-Fi-f0j2IN?usp=drive_link) |

## Technologies
YOLOv8, EasyOCR, FastAPI, OpenCV, thefuzz, scikit-learn

## Auteur
Hassna Bouadou
