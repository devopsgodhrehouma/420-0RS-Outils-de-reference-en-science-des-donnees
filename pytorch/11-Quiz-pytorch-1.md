---
title: "Quiz 1 : PyTorch en Pratique"
description: "Quiz pour tester vos connaissances sur l'implémentation de réseaux de neurones avec PyTorch et la manipulation des données"
tags: ["Deep Learning", "Quiz", "PyTorch"]
slug: "quiz-pytorch-1"
---

# **Quiz 1 : PyTorch en Pratique**

---

:::info 🎯 **Objectif du quiz** : 
Tester vos connaissances sur les concepts fondamentaux des réseaux de neurones. Dans ce quiz, les réponses sont fournies. Les réponses correctes sont marquées d'un `[x]`.
:::



### **Question 1**  
**Quel est l'objectif principal du modèle implémenté dans cet exercice ?**

- [ ] Classifier des images en différentes catégories.  
- [x] Prédire les coûts de production d'un produit en fonction de variables d'entrée.  
- [ ] Identifier des anomalies dans les données de production.  
- [ ] Segmenter les coûts en catégories spécifiques.  

---

### **Question 2**  
**Quelle méthode est utilisée pour structurer et manipuler les ensembles de données ?**

- [ ] pandas DataFrame.  
- [x] PyTorch Dataset et DataLoader.  
- [ ] numpy Array.  
- [ ] Scikit-learn Pipeline.  

---

### **Question 3**  
**Quel est le rôle principal de la classe `ProductionDataset` dans le code ?**

- [ ] Entraîner le modèle avec les données brutes.  
- [x] Structurer les données pour les utiliser dans un DataLoader.  
- [ ] Normaliser les données d'entrée.  
- [ ] Visualiser les performances du modèle.  

---

### **Question 4**  
**Pourquoi ajoute-t-on une dimension aux sorties dans `self.y.unsqueeze(1)` dans le Dataset ?**

- [ ] Pour augmenter le nombre d'échantillons.  
- [ ] Pour normaliser les données de sortie.  
- [ ] Pour rendre les données compatibles avec la fonction de coût.  
- [x] Pour convertir les sorties en format matriciel attendu par le modèle.  

---

### **Question 5**  
**Quelle est la fonction principale de `nn.Sequential` dans la définition du modèle ?**

- [ ] Appliquer automatiquement une fonction de perte.  
- [ ] Empiler des couches linéaires et des fonctions d'activation dans un modèle organisé.  
- [x] Gérer l'optimisation du modèle.  
- [ ] Effectuer des calculs sur les gradients.  

---

### **Question 6**  
**Quelle fonction d'activation est utilisée dans les couches cachées du modèle ?**

- [ ] Sigmoid.  
- [ ] Tanh.  
- [x] ReLU.  
- [ ] Softmax.  

---

### **Question 7**  
**Quel optimiseur est utilisé pour entraîner le modèle ?**

- [ ] SGD (Stochastic Gradient Descent).  
- [ ] RMSprop.  
- [x] Adam.  
- [ ] Adagrad.  

---

### **Question 8**  
**Quelle est la fonction de perte utilisée pour entraîner ce modèle de régression ?**

- [ ] CrossEntropyLoss.  
- [ ] Negative Log-Likelihood Loss.  
- [x] Mean Squared Error (MSE).  
- [ ] Hinge Loss.  

---

### **Question 9**  
**Pourquoi divise-t-on les données en ensembles d'entraînement et de test ?**

- [ ] Pour réduire la taille des données utilisées dans le modèle.  
- [x] Pour évaluer la capacité du modèle à généraliser sur des données non vues.  
- [ ] Pour éviter que les pertes n'explosent pendant l'entraînement.  
- [ ] Pour optimiser les performances du modèle sur l'ensemble d'entraînement.  

---

### **Question 10**  
**Quelle commande permet de mettre à jour les poids du modèle lors de l'entraînement ?**

- [ ] `loss_fn.step()`.  
- [ ] `model.update()`.  
- [ ] `dataloader.optimize()`.  
- [x] `optimizer.step()`.  

---

### **Question 11**  
**Pourquoi utilise-t-on `model.eval()` pendant l'évaluation ?**

- [ ] Pour calculer les gradients lors de l'évaluation.  
- [x] Pour désactiver certaines couches comme Dropout.  
- [ ] Pour initialiser les poids du modèle.  
- [ ] Pour accélérer les calculs en désactivant les fonctions d'activation.  

---

### **Question 12**  
**Quel est l'objectif principal de la visualisation des pertes d'entraînement et de test ?**

- [ ] Identifier les erreurs dans les données d'entrée.  
- [ ] Optimiser les hyperparamètres automatiquement.  
- [x] Suivre la convergence du modèle et détecter un éventuel surapprentissage.  
- [ ] Analyser les prédictions sur les données de test.  

---

### **Question 13**  
**Pourquoi est-il important de normaliser les données en entrée ?**

- [ ] Pour augmenter leur taille.  
- [ ] Pour réduire le temps d'entraînement.  
- [x] Pour améliorer la stabilité et la convergence de l'entraînement.  
- [ ] Pour optimiser automatiquement les poids du modèle.  

---

### **Question 14**  
**Combien de couches cachées contient le modèle du premier exemple ?**

- [ ] Une seule couche cachée.  
- [ ] Deux couches cachées.  
- [x] Trois couches cachées.  
- [ ] Cinq couches cachées.  

---

### **Question 15**  
**Que représente le paramètre `batch_size` dans le DataLoader ?**

- [ ] Le nombre total d'échantillons dans le Dataset.  
- [ ] Le nombre d'epochs pour l'entraînement.  
- [x] Le nombre d'échantillons utilisés dans chaque itération d'entraînement.  
- [ ] La fréquence à laquelle le modèle est évalué.  

---

### **Question 16**  
**Comment le modèle prédit les valeurs pour des données de test ?**

- [ ] Il utilise des données étiquetées pour ajuster les prédictions.  
- [ ] Il génère directement des prédictions aléatoires.  
- [x] Il applique les données de test au réseau entraîné.  
- [ ] Il ajuste les poids en fonction des données de test.  

---

### **Question 17**  
**Quel est l’avantage principal d’utiliser `DataLoader` pour manipuler les données ?**

- [ ] Les données sont automatiquement normalisées.  
- [ ] Les échantillons sont augmentés dynamiquement pendant l'entraînement.  
- [x] Les données sont traitées par lots pour optimiser la mémoire et la vitesse.  
- [ ] Les prédictions sont calculées directement dans le DataLoader.  

---

### **Question 18**  
**Quelle est la taille des données en entrée pour chaque échantillon dans ce modèle ?**

- [ ] 1 variable d’entrée.  
- [x] 3 variables d’entrée.  
- [ ] 64 variables d’entrée.  
- [ ] Cela dépend du `batch_size`.  

---

### **Question 19**  
**Comment interpréter une perte élevée sur l’ensemble de test mais faible sur l’ensemble d’entraînement ?**

- [x] Le modèle surapprend (overfitting).  
- [ ] Le modèle sous-apprend (underfitting).  
- [ ] Les données de test sont incorrectes.  
- [ ] Le modèle ne converge pas.  

---

### **Question 20**  
**Quelle est la différence entre les prédictions et les valeurs réelles sur l'ensemble de test appelée ?**

- [ ] Le gradient.  
- [ ] La normalisation.  
- [x] L'erreur ou résidu.  
- [ ] Le taux d'apprentissage.  

<br/>

> **Note** : 
Les réponses correctes sont marquées d'un `[x]`.  
Ce quiz teste à la fois la compréhension des concepts fondamentaux et l'analyse du code implémenté. Vous pouvez personnaliser les questions selon vos besoins. 🎓
