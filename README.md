# Projet 7 OC – Analysez les ventes et le stock de BottleNeck / Analyze BottleNeck's Sales and Stock

[![Jupyter](https://img.shields.io/badge/Jupyter-ffffff?logo=Jupyter)](#)
[![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=fff)](#)
[![Pandas](https://img.shields.io/badge/Pandas-150458?logo=pandas&logoColor=fff)](#)
[![NumPy](https://img.shields.io/badge/NumPy-4DABCF?logo=numpy&logoColor=fff)](#)
[![Matplotlib](https://custom-icon-badges.demolab.com/badge/Matplotlib-71D291?logo=matplotlib&logoColor=fff)](#)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![License: MIT](https://img.shields.io/badge/License-MIT-blue)

---

## 🇫🇷 Version française

Ceci est le dépôt GitHub d’un projet réalisé dans le cadre de ma formation **Développeur IA** avec OpenClassrooms.

L’objectif principal est de réaliser une analyse de données pour **BottleNeck**, un marchand de spiritueux, vins et champagnes. 
Le but est de rapprocher deux bases de données (ERP et Web), d'analyser le chiffre d'affaires et de détecter d'éventuelles anomalies (outliers) dans les prix des produits.

L'analyse a été réalisée via un **Notebook Jupyter**, en mettant l'accent sur la qualité des données et la visualisation interactive.

### Fonctionnalités Clés

- **Nettoyage et préparation des données** : Traitement des valeurs nulles, doublons et erreurs de saisie (fichiers Excel ERP, Web et Liaison).
- **Rapprochement des bases** : Fusion des jeux de données (Jointures) pour créer un "Master Dataset".
- **Analyse du Chiffre d'Affaires** : Calcul du CA total et par produit, identification des "Flops" et "Tops" ventes.
- **Détection des Outliers (Prix)** : Utilisation de méthodes statistiques (Z-Score et Interquartile Range - IQR) pour identifier les produits aux prix atypiques (produits Premium).
- **Visualisation de données** : Graphiques interactifs avec Plotly Express et statistiques descriptives.
- **Export** : Génération d'un fichier final propre pour les équipes métiers.

## Technologies utilisées

| Pile Technique | Outil | Rôle |
|:---|:---|:---|
| Langage | Python | Langage principal pour l'analyse de données |
| Manipulation des données | Pandas / NumPy | Librairies pour le nettoyage, l'agrégation et le calcul scientifique (Z-score) |
| Visualisation | Plotly Express | Création de graphiques interactifs (Scatter plots, Boxplots) |
| Visualisation (Statique) | Matplotlib / Seaborn | Création de graphiques statiques pour l'analyse exploratoire (Heatmap) |
| Environnement | Jupyter Notebook | Interface de développement pour l'exécution du code et la documentation |

## Installation & utilisation

> J'ai utilisé [Poetry](https://python-poetry.org/docs/) pour gérer mes dépendances, il est préférable que vous l'ailliez également sur votre machine pour installer au mieux ce projet.

1. Cloner le dépôt

```bash
git clone https://github.com/ifTrueReturnFalse/retraining-data-analysis-store.git
cd retraining-data-analysis-store
```

2. Installer les dépendances

```bash
poetry install
```

3. Lancer le notebook

```python
jupyter notebook bottleneck_analysis.ipynb
```

## Aperçu de l'analyse

L'analyse complète est détaillée dans le notebook. Voici quelques points pertinents :

<details> <summary><b>Analyse des Outliers (Prix)</b></summary>
  
L'analyse univariée des prix a révélé plusieurs outliers.

- **Méthode Z-Score** : Identification des produits dont le prix s'éloigne de la moyenne de plus de 3 écarts-types.
- **Méthode IQR** : Identification via l'écart interquartile.

*Conclusion* : Ces outliers ne sont pas des erreurs mais correspondent à des vins Ultra Premium (ex: Champagne Egly-Ouriet, Cognac Frapin).

</details>

<details> <summary><b>Corrélations Stock / Ventes</b></summary>

Une Heatmap de corrélation a été générée pour comprendre les liens entre le prix, le stock et les ventes.

- Il n'y a pas de corrélation linéaire forte entre le prix et le stock.
- La relation Prix/Ventes suit une tendance logarithmique (les ventes chutent drastiquement quand le prix augmente, sauf pour les produits d'exception).

</details>
