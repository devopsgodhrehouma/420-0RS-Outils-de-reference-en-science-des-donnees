---
title: "Construction d'un Réseau de Neurones - Les Bases"  
description: "Apprenez à construire un réseau de neurones pas à pas"  
tags: ["Deep Learning", "Réseaux de Neurones", "Architecture", "Artificial Intelligence"]  
slug: "neural-network-construction"  
---

# Construction d'un Réseau de Neurones - Les Bases

---

## Table des matières

1. [Architecture d'un réseau de neurones](#architecture)
2. [Les différentes couches](#couches)
3. [La propagation avant](#propagation)
4. [L'apprentissage](#apprentissage)
5. [Les hyperparamètres](#hyperparametres)
6. [Implémentation pratique : Construisons ensemble un réseau de neurones](#implementation)
7. [L'apprentissage](#apprentissage)


---

<a id="architecture"></a>  
<br/>

## 1. Architecture d'un réseau de neurones  
---
### 1.1. Vue d'ensemble  

Un réseau de neurones est une **collection organisée de neurones artificiels** qui travaillent ensemble pour résoudre un problème spécifique.  
- **Chaque neurone** traite une partie des données.  
- **Chaque couche** joue un rôle dans l'extraction ou la transformation de l'information.  
- **Le réseau dans son ensemble** apprend à partir des données pour produire une sortie fiable.  

### 1.2. Les principes fondamentaux  

- **Organisation en couches** : Entrée → Cachées → Sortie.  
- **Connexions entre neurones** : Pondérées pour moduler l’importance des signaux.  
- **Flux d’information unidirectionnel** : Dans un réseau classique, l’information circule de l’entrée à la sortie sans retour immédiat.

:::info  
**Métaphore** : Imaginez une chaîne de production.  
1. Les matières premières (couche d’entrée) sont transformées par chaque équipe (couches cachées).  
2. À la fin, le produit fini est prêt (couche de sortie).  
:::  

[⬆️ Retour à la table des matières](#table-des-matières)  

<a id="couches"></a>  
<br/>

---


## 2. Les différentes couches  
---

### 2.1. Couche d’entrée  

- **Rôle principal** :  
  - Accepter les données brutes (ex. pixels, texte, données numériques).  
  - Les normaliser pour éviter des écarts excessifs.  
  - Distribuer ces données aux couches suivantes.  

### 2.2. Couches cachées  

- **Processus clé** :  
  - Détecter des motifs dans les données.  
  - Apprendre des représentations abstraites à différents niveaux.  

:::info  
Prenons l'exemple d'une reconnaissance faciale :  
- **Couche d’entrée** : Pixels de l’image.  
- **Première couche cachée** : Détection des contours.  
- **Couches suivantes** : Identification des formes (nez, yeux, etc.).  
- **Dernière couche cachée** : Assemblage pour former un visage complet.  
:::  

### 2.3. Couche de sortie  

- Fournit la **prédiction finale**.  
- La sortie peut être :  
  - Une classification (probabilités).  
  - Une valeur continue (régression).  
  - Des catégories (texte, labels).  


[⬆️ Retour à la table des matières](#table-des-matières)  

<a id="propagation"></a>  
<br/>

---


## 3. La propagation avant  
---

### 3.1. Le flux d’information  

1. **Entrée des données**  
   - Les données sont transformées en un format numérique exploitable.  
   - Elles sont normalisées pour une meilleure stabilité.  

2. **Propagation à travers les couches**  
   - Chaque neurone effectue un calcul simple :
     - Il multiplie chaque entrée par son poids
     - Il additionne tous ces résultats
     - Il ajoute un biais
   
   Par exemple, avec 2 entrées :
   - Entrée 1 × Poids 1 = Résultat 1
   - Entrée 2 × Poids 2 = Résultat 2  
   - Total = Résultat 1 + Résultat 2 + Biais

<br/>
    # ➗ Équation mathématique :
    $$z = w_1x_1 + w_2x_2 + b$$

   - Application d’une fonction d’activation pour produire une sortie.  

3. **Génération de la sortie**  
   - Les couches finales produisent la sortie dans un format adapté au problème.  

:::info  
**Métaphore** : C'est comme une rivière qui coule d’amont en aval :  
- Les données (eau) passent par des filtres successifs (couches).  
- À la fin, vous obtenez une eau pure (prédiction).  
:::  


[⬆️ Retour à la table des matières](#table-des-matières)  

<a id="apprentissage"></a> 
<br/>

---

## 4. L'apprentissage
---

### 4.1. Principe général

L'apprentissage est un processus itératif qui ajuste les **poids** et **biais** du réseau pour minimiser une erreur mesurée par une fonction de perte. C'est le cœur de l'intelligence artificielle.

### 4.2. Les trois phases clés

1. **Propagation avant (Forward Pass)**
   - Transmission des données d'entrée à travers le réseau
   - Calcul des prédictions couche par couche
   - Obtention d'une sortie finale à comparer avec la cible

2. **Calcul de l'erreur (Loss Computation)**
   - Évaluation précise de l'écart entre prédiction et réalité
   - Utilisation de fonctions de perte adaptées au problème :
     - MSE pour la régression
     - Cross-entropy pour la classification
     - Autres fonctions spécialisées selon les besoins

3. **Optimisation (Backward Pass)**
   - Calcul des gradients par rétropropagation
   - Mise à jour intelligente des paramètres via l'optimiseur
   - Algorithmes courants : SGD, Adam, RMSprop

### 4.3. Analogies et visualisation

:::info
🎯 **Métaphore du tir à l'arc** :
- La propagation avant = décocher la flèche
- L'erreur = distance à la cible 
- L'optimisation = ajustement de la posture et de la visée

🚲 **Métaphore du vélo** :
- Chaque tentative = une propagation avant
- Les chutes = les erreurs
- L'apprentissage de l'équilibre = l'optimisation des paramètres
:::

### 4.4. Bonnes pratiques

- **Initialisation** : Démarrer avec des poids appropriés
- **Batch size** : Équilibrer vitesse et stabilité
- **Learning rate** : Ajuster selon la convergence
- **Monitoring** : Suivre l'évolution de la perte


:::info
**Analogies concrètes pour les hyperparamètres** :

🎪 **Batch size (taille des lots)** :
- Imaginez une file d'attente de 1000 personnes pour un manège
- Vous pouvez faire entrer :
  - 20 personnes → 50 tours nécessaires (plus stable mais plus long)
  - 100 personnes → 10 tours nécessaires (plus rapide mais plus chaotique)
  - 1000 personnes → 1 seul tour (rapide mais très instable)

⚡ **Learning rate (taux d'apprentissage)** :
- C'est comme apprendre à faire du vélo :
  - Trop prudent (0.0001) → progression très lente
  - Trop téméraire (0.1) → chutes fréquentes
  - Bien dosé (0.01) → apprentissage optimal

🎯 **Nombre d'epochs (cycles d'entraînement)** :
- Comme apprendre une chorégraphie :
  - Trop peu → mouvements imprécis
  - Trop → risque de sur-apprentissage
  - Juste assez → maîtrise parfaite

🧮 **Taille du réseau** :
- Comme une équipe de travail :
  - Trop petite → ne peut pas gérer la complexité
  - Trop grande → gaspillage de ressources
  - Bien dimensionnée → efficacité maximale
:::



:::info  
**Métaphore** : Apprendre à lancer une fléchette.  
- Vous lancez (propagation avant).  
- Vous ratez la cible (erreur).  
- Vous ajustez votre position (rétropropagation).  
- Vous essayez à nouveau (nouvelle mise à jour).  
:::  

[⬆️ Retour à la table des matières](#table-des-matières)  
<a id="hyperparametres"></a> 

<br/>

---

 
## 5. Les hyperparamètres  
---

### 5.1. Paramètres clés  

1. **Nombre de couches**  
   - Plus de couches = capacité à apprendre des motifs complexes.  

2. **Nombre de neurones par couche**  
   - Influence la largeur du réseau et sa capacité à modéliser les données.  

3. **Taux d’apprentissage**  
   - Contrôle la vitesse d’apprentissage :  
     - Trop grand : le modèle peut diverger.  
     - Trop petit : l’apprentissage sera lent.  

:::info
**Les hyperparamètres : des choix AVANT l'action !**

Imaginez la préparation d'un gâteau :
- AVANT de commencer, vous devez choisir :
  - La taille du moule (architecture du réseau)
  - La température du four (taux d'apprentissage)
  - Le temps de cuisson (nombre d'epochs)

Une fois la cuisson lancée, impossible de changer ces paramètres !

C'est la même chose pour un réseau de neurones :
- **Le taux d'apprentissage** doit être fixé avant :
  - Trop élevé → apprentissage chaotique
  - Bien dosé → apprentissage harmonieux

- **L'architecture** est décidée en amont :
  - Trop de neurones → ressources gaspillées
  - Trop peu → capacité insuffisante

❗ **Important** : Comme pour une recette, ces choix sont cruciaux et ne peuvent pas être modifiés pendant l'exécution. Il faut tout recommencer si les paramètres ne conviennent pas !
:::

[⬆️ Retour à la table des matières](#table-des-matières)  

<a id="implementation"></a>  
<br/>

---


## 6. Implémentation pratique : Construisons ensemble un réseau de neurones  
--- 

### 6.1. Pourquoi observer l'architecture ?

Dans ce paragraphe, nous allons examiner attentivement l'architecture d'un réseau de neurones simple. Je vous invite particulièrement à observer :

- Le **nombre de neurones** dans chaque couche
- L'**organisation des couches** (entrée, cachée, sortie)

Ne vous inquiétez pas si tous les concepts ne sont pas clairs immédiatement. L'important est d'abord de bien visualiser comment les neurones sont organisés et connectés entre eux.

:::tip Rassurez-vous !
Ne vous inquiétez pas des fonctions complexes que vous verrez dans le code - elles sont déjà construites par d'autres développeurs. Concentrons-nous plutôt sur le concept essentiel :

Imaginez un entonnoir intelligent qui :
1. Reçoit beaucoup d'informations en entrée
2. Les filtre et les simplifie couche après couche
3. Arrive à une décision finale simple

Par exemple :
- Entrée : 1000 pixels d'une image
- Première couche cachée : 100 neurones qui détectent des formes basiques
- Deuxième couche : 10 neurones qui combinent ces formes
- Sortie : 1 neurone qui dit "chat" ou "pas chat"

C'est la magie des réseaux de neurones : transformer la complexité en simplicité, étape par étape !
:::



### 6.2. Exemple de code : Une seule couche cachée  

Commençons avec le réseau le plus simple possible, une **seule couche cachée**, pour que vous puissiez vous concentrer sur les bases.

```python
import torch
import torch.nn as nn

# Étape 1 : Définir un réseau avec une seule couche cachée
class SimpleNN(nn.Module):
    def __init__(self):
        super(SimpleNN, self).__init__()
        self.hidden = nn.Linear(3, 5)  # 3 entrées, 5 neurones dans la couche cachée
        self.output = nn.Linear(5, 2) # 5 neurones cachés, 2 sorties

    def forward(self, x):
        x = torch.relu(self.hidden(x))  # Fonction d'activation ReLU
        return self.output(x)

# Étape 2 : Initialiser le réseau et les données
model = SimpleNN()
inputs = torch.tensor([[1.0, 2.0, 3.0]])  # Exemple de 3 entrées (ex : poids, taille, âge)
outputs = model(inputs)  # Calcul de la sortie

print(f"Sortie du réseau : {outputs}")
```

#### Ce que vous venez de faire :
1. Vous avez **défini un réseau** avec 3 entrées, une couche cachée de 5 neurones, et une sortie de 2 neurones.
2. Vous avez passé des données d’entrée et observé une **sortie non entraînée**. C’est normal, nous n’avons pas encore entraîné le modèle !



### 6.3. Schématisation du réseau

Visualisez le réseau comme une chaîne :

```
[Entrée] (3 neurones) --> [Couche Cachée] (5 neurones, ReLU) --> [Sortie] (2 neurones)
```
```
[Entrée]           [Couche Cachée]         [Sortie]
   x₁ ----→         o                        y₁
   x₂ ----→        ooo        ReLU  ----→   y₂
   x₃ ----→         o                             
```

- **Entrée (x₁, x₂, x₃)** : Représente les données que vous voulez analyser.  
- **Couche Cachée (5 neurones)** : Apprend des motifs complexes grâce à ses connexions pondérées.  
- **Sortie (y₁, y₂)** : Fournit les résultats (ex. classification ou prédiction).



### 6.4. Ajout d’une fonction de perte et optimisation  

Pour que notre réseau apprenne, nous devons :
1. **Calculer une erreur** (ou perte) entre la sortie du réseau et les valeurs attendues.  
2. **Ajuster les poids** du réseau pour réduire cette erreur.  

```python
import torch.optim as optim

# Étape 1 : Définir la fonction de perte et l’optimiseur
criterion = nn.MSELoss()  # Erreur quadratique moyenne (pour des sorties continues)
optimizer = optim.SGD(model.parameters(), lr=0.01)  # Descente de gradient avec un faible taux d'apprentissage

# Étape 2 : Définir les cibles
targets = torch.tensor([[0.0, 1.0]])  # Exemple de cibles (valeurs attendues)

# Étape 3 : Propagation avant, calcul de la perte et rétropropagation
outputs = model(inputs)               # Calcul des sorties
loss = criterion(outputs, targets)   # Calcul de la perte
loss.backward()                       # Calcul des gradients
optimizer.step()                      # Mise à jour des poids

print(f"Perte après une étape d'apprentissage : {loss.item():.4f}")
```



### 6.5. Ajout d’une deuxième couche cachée  

Une fois que vous êtes à l’aise avec une seule couche, passons à **deux couches cachées**. 

#### Pourquoi ajouter une deuxième couche cachée ?
- Cela permet au réseau d’apprendre des **relations plus complexes** dans vos données.
- Chaque couche cachée extrait des **motifs de plus haut niveau**.

```python
class AdvancedNN(nn.Module):
    def __init__(self):
        super(AdvancedNN, self).__init__()
        self.hidden1 = nn.Linear(3, 5)  # Première couche cachée (5 neurones)
        self.hidden2 = nn.Linear(5, 4)  # Deuxième couche cachée (4 neurones)
        self.output = nn.Linear(4, 2)   # Couche de sortie (2 neurones)

    def forward(self, x):
        x = torch.relu(self.hidden1(x)) # Activation après la première couche
        x = torch.relu(self.hidden2(x)) # Activation après la deuxième couche
        return self.output(x)

# Initialisation
model = AdvancedNN()
criterion = nn.MSELoss()
optimizer = optim.Adam(model.parameters(), lr=0.01)
```



### 6.6. Exercice : Une troisième couche cachée  

#### Pourquoi une troisième couche ?
- Une troisième couche cachée permet de **modéliser des interactions encore plus complexes**.
- Par exemple, si vos données représentent des images, cette couche pourrait apprendre des formes comme des yeux ou des motifs géométriques.

#### Spécifications :
- Couche cachée 1 : 6 neurones.  
- Couche cachée 2 : 4 neurones.  
- Couche cachée 3 : 3 neurones.  
- Couche de sortie : 2 neurones.

```python
class ThreeLayerNN(nn.Module):
    def __init__(self):
        super(ThreeLayerNN, self).__init__()
        self.hidden1 = nn.Linear(3, 6)  # Première couche cachée (6 neurones)
        self.hidden2 = nn.Linear(6, 4)  # Deuxième couche cachée (4 neurones)
        self.hidden3 = nn.Linear(4, 3)  # Troisième couche cachée (3 neurones)
        self.output = nn.Linear(3, 2)   # Couche de sortie (2 neurones)

    def forward(self, x):
        x = torch.relu(self.hidden1(x))
        x = torch.relu(self.hidden2(x))
        x = torch.relu(self.hidden3(x))
        return self.output(x)

# Initialisation
model = ThreeLayerNN()
criterion = nn.CrossEntropyLoss()  # Pour des problèmes de classification
optimizer = optim.Adam(model.parameters(), lr=0.005)
```



### 6.7. Résumé 

- **Une seule couche cachée** : Comprendre la structure de base d’un réseau.  
- **Deux couches cachées** : Ajouter de la complexité et capturer des motifs plus subtils.  
- **Trois couches cachées ou plus** : Modéliser des relations complexes et préparer des architectures profondes.  


[⬆️ Retour à la table des matières](#table-des-matières)

<br/>



