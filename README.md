# Contrôle de TP Apprentissage Automatique 1

Ce dépôt contient un notebook Jupyter intitulé **KASMI.ipynb** pour un projet de contrôle de TP en apprentissage automatique, focalisé sur la classification d'échantillons audio à l'aide d'apprentissage profond.

## Objectif

L’objectif de la séance est de classer automatiquement des fichiers audio appartenant à 10 classes différentes à partir d’un corpus fourni, en allant jusqu’à l’extraction de spectrogrammes (représentation temps/fréquence du signal audio) assimilés à des images pour le traitement.

Les classes du corpus sont :
- tronçonneuse (`chainsaw`)
- tic-tac d'une horloge (`clock_tick`)
- craquement de feu (`crackling_fire`)
- pleurs de bébé (`crying_baby`)
- chien (`dog`)
- hélicoptère (`helicopter`)
- pluie (`rain`)
- coq (`rooster`)
- bruit des vagues (`sea_waves`)
- éternuement (`sneezing`)

## Contenu du notebook

### 1. Imports et dépendances
Les bibliothèques suivantes sont utilisées :
- Python standard : `os`, `random`, `zipfile`, `math`
- Visualisation : `matplotlib.pyplot`
- Traitement du signal : `librosa` (installation via `pip` dans le notebook)
- NumPy
- PyTorch (`torch`, `torch.nn`, `torch.optim`, `torch.nn.functional`)

### 2. Chargement et Préparation des Données

- **Téléchargement et extraction du corpus** :  
  Code pour télécharger le corpus à partir d’une URL, le dézipper, et préparer la structure de dossiers.

- **Lecture des fichiers audio et extraction des spectrogrammes** :  
  Une fonction, `load_dataset`, parcourt les fichiers `.wav` de chaque classe, lit les données audio avec `librosa`, extrait les spectrogrammes de type Mel, et les convertit en échelle de dB pour une exploitation ultérieure sous forme d’images.

- **Structure du dossier de données** :  
  Les données sont placées dans le dossier `./data/` avec une arborescence par dossier de classe.

- **Partitionnement apprentissage/test** :  
  Le jeu de données est divisé entre `train` et `test`. Le notebook charge en mémoire séparément les données d’apprentissage et de test.

- **Statistiques de base** :  
  Affichage du nombre d’exemples pour train et test, ainsi que la forme des matrices de données (nombre d’images, taille des images, etc.)

### 3. Visualisation

- **Correspondance label/ID** :  
  Affichage de la liste `idx_to_classes` pour lier les entiers des labels à leur classe réelle.

- **Exemple de spectrogrammes** :  
  Affichage de quelques spectrogrammes exemples en utilisant `matplotlib` et `librosa.display` pour chaque classe.

## Utilisation

Ouvrir `KASMI.ipynb` dans un environnement compatible Jupyter (Colab, JupyterLab…) et exécuter chaque cellule.
- Les dépendances non standard (`librosa`, `torch`) seront installées automatiquement si besoin.
- Le téléchargement du corpus (~123 Mo) requiert une connexion Internet.
- Le chargement initial des données (conversion audio → spectrogrammes) peut prendre quelques minutes.

## Remarque

Ce notebook est focalisé sur la préparation des données pour un projet de classification automatique de sons environnementaux à partir de spectrogrammes.  
L’entraînement complet d’un modèle de deep learning n’est **pas** inclus dans la partie visible du code, mais tout le pré-traitement est prêt pour ce type d’application.

---

*Pour tout détail complémentaire, se référer au code et aux commentaires du notebook [`KASMI.ipynb`](https://github.com/KASMIKAS/Apprentissage-automatique/blob/master/KASMI.ipynb).*
