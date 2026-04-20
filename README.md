# Projet de Deep Learning : Prédiction de Séries Temporelles (RNN)

## Description du Projet
Ce projet a été réalisé dans le cadre du cours de Machine Learning. L'objectif est de concevoir, entraîner et évaluer des modèles de Deep Learning en utilisant **TensorFlow** et **Keras**. 

Le travail met l'accent sur l'expérimentation rigoureuse : chaque choix d'architecture ou d'hyperparamètre est documenté selon une démarche scientifique (Hypothèse, Méthodologie, Observations, Conclusions).

###  Sujet et Objectifs
* **Catégorie :** 3 - Prédiction de Séries Temporelles avec RNNs
* **Dataset :** *Household Energy Consumption* (Subset - Consommation Énergétique)
* **Objectif :** Prédire la puissance active globale (`Global_active_power`) pour l'intervalle de temps suivant en se basant sur les minutes précédentes.
* **Métriques d'évaluation :** MSE (Mean Squared Error), MAE (Mean Absolute Error) et RMSE (Root Mean Squared Error).

---

## Membres du Groupe
* **Étudiant 1 :** Justin Fransolet
* **Étudiant 2 :** Thibault Theunissen
* **Étudiant 3 :** [Prénom Nom]

---

## Structure du Projet
Le projet est structuré comme suit pour garantir la reproductibilité :

* `notebook.ipynb` : L'unique fichier source contenant l'exploration des données (visualisation des tendances/saisonnalités), le prétraitement (fenêtrage), l'entraînement des modèles et l'analyse comparative.
* `requirements.txt` : Liste des dépendances Python nécessaires.
* `README.md` : Ce fichier d'instructions.

---

## Installation et Configuration

### 1. Prérequis
Assurez-vous d'avoir Python installé (recommandé : 3.9.13). Le projet utilise principalement :
* TensorFlow / Keras
* Pandas
* Matplotlib / Seaborn

### 2. Installation des dépendances
Utilisez la commande suivante pour installer toutes les bibliothèques requises:
```bash
pip install -r requirements.txt
```

### 3. Datasets
Disponible sur le dépôt **UCI ML** sous le nom `Individual household electric power consumption Data Set`. [Lien](https://archive.ics.uci.edu/dataset/235/individual+household+electric+power+consumption)

**Attention** : Dataset très volumineux.

Nécessite de ne sélectionner qu'une **période limitée** et de gérer les **valeurs manquantes** pour rester dans les contraintes du projet.

---