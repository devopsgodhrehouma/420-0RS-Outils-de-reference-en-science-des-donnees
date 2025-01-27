---
title: "Implémentation et Analyse d'un Réseau de Neurones avec PyTorch"
description: "Analyse détaillée d'une implémentation de réseau de neurones avec PyTorch pour la prédiction des coûts de production"
tags: ["Deep Learning", "PyTorch", "Régression", "Analyse de Code"]
slug: /06-Deep-Learning/Chapter6-Practice2-PyTorch/01-Code-Analysis
---

# Exemple pratique 1 : Implémentation et Analyse d'un Réseau de Neurones avec PyTorch

---

## Table des matières

1. [Introduction](#1---introduction)
2. [Contexte du Problème à Résoudre](#2---contexte-du-problème-à-résoudre--prédiction-des-coûts-de-production-dun-produit)
3. [Préparation des Données](#3---préparation-des-données)
4. [Architecture du Modèle](#4---architecture-du-modèle)
5. [Points Clés](#5---points-clés)
6. [Résumé](#6---résumé)
7. [Annexe : Deuxième Exemple de Code](#7---annexe--un-deuxième-exemple-de-code-pour-prédiction-des-coûts-avec-un-modèle-profond-5-couches)
8. [Caractéristiques du Modèle](#8---caractéristiques-du-modèle)
9. [Points Clés](#9---points-clés)
10. [Références](#10---références)


<br/>
---
## Objectifs d'apprentissage
---

- Comprendre l'implémentation d'un réseau de neurones avec PyTorch
- Maîtriser les concepts fondamentaux de l'apprentissage profond
- Développer des compétences pratiques en programmation PyTorch


[⬆️ Retour à la Table des Matières](#table-des-matières)
<br/>
---
## 1 - Introduction
---

Dans ce chapitre, nous allons analyser en détail une implémentation pratique d'un réseau de neurones avec PyTorch. Notre objectif est de créer un modèle capable de prédire les coûts de production d'un produit en fonction de différentes variables d'entrée.

Cette analyse pas à pas nous permettra de :
- Comprendre comment structurer un projet PyTorch complet
- Maîtriser les concepts clés comme les DataLoaders et les Datasets
- Apprendre à implémenter et entraîner un modèle de régression
- Visualiser et interpréter les résultats

Le code que nous allons étudier utilise des données simulées pour se concentrer sur les aspects techniques plutôt que sur la qualité des données. Cette approche nous permet de nous familiariser avec PyTorch dans un environnement contrôlé avant de passer à des données réelles plus complexes.


:::info
👋 **Note aux étudiants**

Dans cette section, nous n'allons pas exécuter le code directement. L'objectif est plutôt de comprendre en profondeur chaque composant du code et son rôle dans la création d'un réseau de neurones avec PyTorch. Nous allons analyser :

- Comment les données sont préparées et structurées
- La logique derrière chaque classe et fonction
- Le rôle des différents composants (DataLoader, Dataset, modèle, etc.)
- Le processus d'entraînement et d'évaluation
- Les techniques de visualisation des résultats

Cette approche analytique vous permettra de mieux maîtriser les concepts fondamentaux et de pouvoir adapter ce code à vos propres projets futurs.
:::



[⬆️ Retour à la Table des Matières](#table-des-matières)
<br/>

---
## 2 - Contexte du Problème à Résoudre : Prédiction des Coûts de Production d'un Produit
---

Vous êtes chargé de développer un modèle de réseau de neurones capable de prédire les coûts de production d'un produit en fonction de plusieurs variables. Les données incluent :
- La quantité de matière première utilisée (en kg),
- Le temps de production (en heures),
- Le coût de la main-d'œuvre (en $).

L'objectif est de former un modèle qui minimise l'erreur entre les coûts réels et prédits. 

Nous demandons à vous de :
1. Comprendre la structure d'un réseau de neurones en PyTorch.
2. Travailler avec des DataLoaders pour manipuler des ensembles de données.
3. Implémenter les fonctions d'entraînement et d'évaluation.
4. Visualiser les performances du modèle.


[⬆️ Retour à la Table des Matières](#table-des-matières)
<br/>

---
## 3 - Étapes du Code
---

- Étape 1 : Importation des Bibliothèques
- Étape 2 : Génération de données simulées
- Étape 3 : Séparation des données
- Étape 4 : Création des datasets
- Étape 5 : Définition du modèle
- Étape 6 : Configuration de l'optimiseur et de la fonction de coût
- Étape 7 : Fonction d'entraînement
- Étape 8 : Fonction d'évaluation
- Étape 9 : Entraînement du modèle
- Étape 10 : Visualisation des performances
- Étape 11 : Évaluation finale



[⬆️ Retour à la Table des Matières](#table-des-matières)
<br/>

---
## 4 - Code Complet
---

```python
import torch
from torch import nn, optim, utils, autograd
import numpy as np
import matplotlib.pyplot as plt

# Génération de données simulées
np.random.seed(42)
torch.manual_seed(42)

# Variables : quantité, temps, coût main d'œuvre
X_data = np.random.rand(1000, 3) * 10  # 1000 échantillons avec 3 variables
y_data = 3 * X_data[:, 0] + 2 * X_data[:, 1] + 4 * X_data[:, 2] + np.random.randn(1000) * 2

# Séparation des données
train_size = int(0.8 * len(X_data))
X_train, X_test = X_data[:train_size], X_data[train_size:]
y_train, y_test = y_data[:train_size], y_data[train_size:]

# Création des datasets
class ProductionDataset(utils.data.Dataset):
    def __init__(self, X, y):
        self.X = torch.tensor(X, dtype=torch.float32)
        self.y = torch.tensor(y, dtype=torch.float32).unsqueeze(1)  # Ajouter une dimension

    def __len__(self):
        return len(self.X)

    def __getitem__(self, idx):
        return self.X[idx], self.y[idx]

train_dataset = ProductionDataset(X_train, y_train)
test_dataset = ProductionDataset(X_test, y_test)

train_loader = utils.data.DataLoader(train_dataset, batch_size=32, shuffle=True)
test_loader = utils.data.DataLoader(test_dataset, batch_size=32)

# Définition du modèle
class NeuralNetwork(nn.Module):
    def __init__(self):
        super(NeuralNetwork, self).__init__()
        self.model = nn.Sequential(
            nn.Linear(3, 64),
            nn.ReLU(),
            nn.Linear(64, 32),
            nn.ReLU(),
            nn.Linear(32, 1)
        )

    def forward(self, x):
        return self.model(x)

model = NeuralNetwork()

# Configuration de l'optimiseur et de la fonction de coût
optimizer = optim.Adam(model.parameters(), lr=0.01)
loss_fn = nn.MSELoss()

# Fonction d'entraînement
def train_model(dataloader, model, loss_fn, optimizer):
    model.train()
    total_loss = 0
    for X_batch, y_batch in dataloader:
        optimizer.zero_grad()
        predictions = model(X_batch)
        loss = loss_fn(predictions, y_batch)
        loss.backward()
        optimizer.step()
        total_loss += loss.item()
    return total_loss / len(dataloader)

# Fonction d'évaluation
def evaluate_model(dataloader, model, loss_fn):
    model.eval()
    total_loss = 0
    with torch.no_grad():
        for X_batch, y_batch in dataloader:
            predictions = model(X_batch)
            loss = loss_fn(predictions, y_batch)
            total_loss += loss.item()
    return total_loss / len(dataloader)

# Entraînement du modèle
num_epochs = 50
train_losses = []
test_losses = []

for epoch in range(num_epochs):
    train_loss = train_model(train_loader, model, loss_fn, optimizer)
    test_loss = evaluate_model(test_loader, model, loss_fn)
    train_losses.append(train_loss)
    test_losses.append(test_loss)
    print(f"Epoch {epoch + 1}/{num_epochs} - Train Loss: {train_loss:.4f}, Test Loss: {test_loss:.4f}")

# Visualisation des pertes
plt.figure(figsize=(10, 5))
plt.plot(range(num_epochs), train_losses, label="Train Loss")
plt.plot(range(num_epochs), test_losses, label="Test Loss")
plt.xlabel("Epochs")
plt.ylabel("Loss")
plt.title("Loss during Training and Testing")
plt.legend()
plt.show()

# Évaluation finale
model.eval()
X_sample = torch.tensor(X_test[:5], dtype=torch.float32)
y_sample = y_test[:5]

predictions = model(X_sample).detach().numpy()
for i, (real, pred) in enumerate(zip(y_sample, predictions)):
    print(f"Sample {i + 1}: Real Value = {real:.2f}, Predicted Value = {pred[0]:.2f}")
```


[⬆️ Retour à la Table des Matières](#table-des-matières)
<br/>

---
## 5 - Points Clés
---

1. **Manipulation des Datasets et DataLoaders** : Charger, normaliser et préparer des données pour l'entraînement.
2. **Définition d'un Modèle** : Créer un modèle avec `nn.Sequential`, ajouter des activations non linéaires.
3. **Fonction de Coût et Optimiseur** : Utiliser des fonctions comme `MSELoss` et optimiser avec `Adam`.
4. **Entraînement et Évaluation** : Implémenter des fonctions d'entraînement et d'évaluation robustes.
5. **Visualisation des Performances** : Utiliser des graphiques pour analyser les pertes et performances du modèle.

Ce code couvre tous les aspects nécessaires pour apprendre la modélisation avec PyTorch tout en résolvant un problème pratique.

[⬆️ Retour à la Table des Matières](#table-des-matières)
<br/>

---
## 6 - Résumé 
---

Dans ce chapitre, nous avons exploré en détail l'implémentation d'un réseau de neurones avec PyTorch pour prédire les coûts de production. Les points essentiels abordés sont :

1. **Préparation des Données**
   - Génération de données simulées pour l'entraînement
   - Séparation en ensembles d'entraînement et de test
   - Utilisation des DataLoaders pour une gestion efficace des lots

2. **Architecture du Modèle**
   - Création d'un réseau de neurones multicouches
   - Configuration des couches et des fonctions d'activation
   - Choix des hyperparamètres appropriés

3. **Processus d'Entraînement**
   - Implémentation des fonctions d'entraînement et d'évaluation
   - Utilisation de l'optimiseur Adam et de la fonction de perte MSE
   - Suivi de la progression avec les métriques de perte

4. **Évaluation et Visualisation**
   - Analyse des courbes d'apprentissage
   - Comparaison des performances sur les ensembles d'entraînement et de test
   - Validation des prédictions sur des échantillons spécifiques

Cette approche pratique permet de comprendre les concepts fondamentaux de PyTorch tout en résolvant un problème concret de régression.


[⬆️ Retour à la Table des Matières](#table-des-matières)
<br/>

---
## 7 - Annexe : un deuxième exemple de code pour prédiction des Coûts avec un Modèle Profond (5 Couches)
---

Le modèle sera configuré avec :
- **5 couches** entièrement connectées (Dense).
- Nombre de neurones par couche : [3 (entrée), 128, 64, 32, 16, 1 (sortie)].
- Fonction d'activation : `ReLU` pour les couches cachées.



#### Code Complet

```python
import torch
from torch import nn, optim, utils
import numpy as np
import matplotlib.pyplot as plt

# ---------------------------------------------------
# Génération de données simulées
# ---------------------------------------------------
np.random.seed(42)
torch.manual_seed(42)

# Données : quantité, temps, coût main d'œuvre
X_data = np.random.rand(5000, 3) * 10  # 5000 échantillons avec 3 variables
y_data = 3 * X_data[:, 0] + 2 * X_data[:, 1] + 4 * X_data[:, 2] + np.random.randn(5000) * 2

# Séparation des données (80% train, 20% test)
train_size = int(0.8 * len(X_data))
X_train, X_test = X_data[:train_size], X_data[train_size:]
y_train, y_test = y_data[:train_size], y_data[train_size:]

# ---------------------------------------------------
# Création du Dataset et DataLoader
# ---------------------------------------------------
class ProductionDataset(utils.data.Dataset):
    def __init__(self, X, y):
        self.X = torch.tensor(X, dtype=torch.float32)
        self.y = torch.tensor(y, dtype=torch.float32).unsqueeze(1)  # Ajouter une dimension pour la sortie

    def __len__(self):
        return len(self.X)

    def __getitem__(self, idx):
        return self.X[idx], self.y[idx]

train_dataset = ProductionDataset(X_train, y_train)
test_dataset = ProductionDataset(X_test, y_test)

train_loader = utils.data.DataLoader(train_dataset, batch_size=64, shuffle=True)
test_loader = utils.data.DataLoader(test_dataset, batch_size=64)

# ---------------------------------------------------
# Définition du modèle (5 couches)
# ---------------------------------------------------
class DeepNeuralNetwork(nn.Module):
    def __init__(self):
        super(DeepNeuralNetwork, self).__init__()
        self.model = nn.Sequential(
            nn.Linear(3, 128),   # Entrée : 3 -> 128 neurones
            nn.ReLU(),
            nn.Linear(128, 64),  # Couche 2 : 128 -> 64 neurones
            nn.ReLU(),
            nn.Linear(64, 32),   # Couche 3 : 64 -> 32 neurones
            nn.ReLU(),
            nn.Linear(32, 16),   # Couche 4 : 32 -> 16 neurones
            nn.ReLU(),
            nn.Linear(16, 1)     # Couche de sortie : 16 -> 1 neurone
        )

    def forward(self, x):
        return self.model(x)

model = DeepNeuralNetwork()

# ---------------------------------------------------
# Configuration de l'optimiseur et de la fonction de coût
# ---------------------------------------------------
optimizer = optim.Adam(model.parameters(), lr=0.001)
loss_fn = nn.MSELoss()

# ---------------------------------------------------
# Fonctions d'entraînement et d'évaluation
# ---------------------------------------------------
def train_model(dataloader, model, loss_fn, optimizer):
    model.train()
    total_loss = 0
    for X_batch, y_batch in dataloader:
        optimizer.zero_grad()
        predictions = model(X_batch)
        loss = loss_fn(predictions, y_batch)
        loss.backward()
        optimizer.step()
        total_loss += loss.item()
    return total_loss / len(dataloader)

def evaluate_model(dataloader, model, loss_fn):
    model.eval()
    total_loss = 0
    with torch.no_grad():
        for X_batch, y_batch in dataloader:
            predictions = model(X_batch)
            loss = loss_fn(predictions, y_batch)
            total_loss += loss.item()
    return total_loss / len(dataloader)

# ---------------------------------------------------
# Entraînement du modèle
# ---------------------------------------------------
num_epochs = 100
train_losses = []
test_losses = []

for epoch in range(num_epochs):
    train_loss = train_model(train_loader, model, loss_fn, optimizer)
    test_loss = evaluate_model(test_loader, model, loss_fn)
    train_losses.append(train_loss)
    test_losses.append(test_loss)
    print(f"Epoch {epoch + 1}/{num_epochs} - Train Loss: {train_loss:.4f}, Test Loss: {test_loss:.4f}")

# ---------------------------------------------------
# Visualisation des performances
# ---------------------------------------------------
plt.figure(figsize=(10, 5))
plt.plot(range(num_epochs), train_losses, label="Train Loss")
plt.plot(range(num_epochs), test_losses, label="Test Loss")
plt.xlabel("Epochs")
plt.ylabel("Loss")
plt.title("Loss during Training and Testing")
plt.legend()
plt.show()

# ---------------------------------------------------
# Évaluation finale avec des échantillons
# ---------------------------------------------------
model.eval()
X_sample = torch.tensor(X_test[:10], dtype=torch.float32)
y_sample = y_test[:10]

predictions = model(X_sample).detach().numpy()
print("\nComparaison entre les valeurs réelles et les prédictions :")
print("Valeur réelle\tPrédiction\tErreur")
print("------------------------------------")
for i, (real, pred) in enumerate(zip(y_sample, predictions)):
    print(f"{real:.2f}\t\t{pred[0]:.2f}\t\t{abs(real - pred[0]):.2f}")
```



[⬆️ Retour à la Table des Matières](#table-des-matières)
<br/>

---
## 8 - Caractéristiques du Modèle
---

1. **Architecture Profonde (5 Couches)** : Les 5 couches permettent au modèle de capturer des relations complexes dans les données.
   - **Entrée** : 3 caractéristiques (quantité, temps, coût).
   - **Couche cachée 1** : 128 neurones.
   - **Couche cachée 2** : 64 neurones.
   - **Couche cachée 3** : 32 neurones.
   - **Couche cachée 4** : 16 neurones.
   - **Sortie** : 1 neurone (valeur de coût prédite).

2. **Optimiseur** : `Adam` est utilisé pour une convergence rapide et efficace.
3. **Fonction de coût** : `MSELoss` (erreur quadratique moyenne) pour minimiser la différence entre les valeurs réelles et prédites.


[⬆️ Retour à la Table des Matières](#table-des-matières)
<br/>

---
## 9 - Points Clés
---

1. Comprendre comment augmenter la complexité d'un réseau de neurones avec plusieurs couches.
2. Apprendre à équilibrer le nombre de neurones par couche pour éviter le surajustement.
3. Visualiser les performances en traçant les pertes pour l'ensemble d'entraînement et de test.
4. Comparer les prédictions du modèle avec les valeurs réelles pour évaluer la précision.


[⬆️ Retour à la Table des Matières](#table-des-matières)
<br/>

---
## 10 - Références
---

- [Getting Started](https://www.kaggle.com/discussions/getting-started/114357)
- [Pipeline for every PyTorch image classification problem](https://medium.com/@siromermer/pipeline-for-every-pytorch-image-classification-problem-creating-dataset-f0f57d6ae225)
- [PyTorch tutorial beginner to advance](https://www.kaggle.com/code/aravindanr22052001/pytorch-tutorial-beginner-to-advance)
- [CIFAR10 tutorial](https://pytorch.org/tutorials/beginner/blitz/cifar10_tutorial.html)

<br/>
[⬆️ Retour à la Table des Matières](#table-des-matières)
