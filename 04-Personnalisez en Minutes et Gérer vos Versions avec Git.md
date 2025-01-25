### 04 - Section 4 : Personnalisez en Minutes et Gérer vos Versions avec Git

---

## Partie 1 : Concevoir un Bon Prompt

Pour maximiser l'efficacité des prompts, voici un guide étape par étape :

### **1.1 Préciser la Page à Modifier**  
Indiquez clairement la page ou la section à modifier.  
**Exemple** : La page principale à `http://localhost:3000/`.

### **1.2 Rappeler le Contexte**  
Décrivez brièvement le projet et son objectif.  
**Exemple** : "Ce projet utilise Docusaurus pour fournir une documentation interactive."

### **1.3 Définir les Détails du Style**  
Ajoutez des précisions pour orienter le design :  
- Style moderne avec animations fluides.  
- Palette de couleurs harmonieuse et typographie lisible.  
- Navigation intuitive avec micro-interactions engageantes.

### **1.4 Booster le Prompt**  
Ajoutez un rôle spécifique pour l'IA.  
**Exemple** : "Agis comme un designer professionnel spécialisé en UI/UX avec 30 ans d'expérience."

### **1.5 Exemples de Plans de Formation (Utiliser des Cercles)**  

#### **Plan 1 : Formation Python**  
1. Introduction à Python  
2. Bases du Langage Python  
3. Fonctions et Modules  
4. Gestion des Fichiers  
5. Programmation Orientée Objet (POO)  
6. Projet Final  

#### **Plan 2 : Prompt Engineering et IA Générative**  
1. Introduction à l'IA générative  
2. Optimisation des Prompts  
3. Automatisation avancée avec Make (Integromat)  
4. Création d’un Funnel de Vente  

---

## Partie 2 : Écriture des Prompts et Validation avec Git

### Prompt 1 : Modifier la Page d'Accueil
**Objectif** : Ajouter un titre attractif et un sous-titre.  
**Prompt** :  
```markdown
- Page principale à modifier : `http://localhost:3000/`.  
- Titre : "Formation Complète Docusaurus & IA".  
- Sous-titre : "Apprenez à exploiter l'IA générative pour optimiser vos projets."  
```

**Commandes Git** :
```bash
git status
git add src/pages/index.js
git commit -m "Prompt 1 - Modification du titre de la page d'accueil"
```

---

### Prompt 2 : Ajouter des Liens Cliquables vers des Catégories
**Objectif** : Intégrer des cercles interactifs redirigeant vers les catégories.  
**Prompt** :  
```markdown
- Lien : Chaque cercle redirige vers `/docs/{nom-categorie}`.  
- Style : Animation au survol et transition fluide.  
```

**Commandes Git** :
```bash
git status
git add src/pages/index.js
git commit -m "Prompt 2 - Ajout de liens cliquables vers les catégories"
```

---

### Prompt 3 : Créer une Animation pour les Titres
**Objectif** : Ajouter une animation pour une meilleure expérience utilisateur.  
**Prompt** :  
```markdown
- Animation : Le titre principal glisse de la gauche vers la droite au chargement de la page.  
```

**Commandes Git** :
```bash
git status
git add src/pages/index.js
git commit -m "Prompt 3 - Animation pour les titres"
```

---

### Prompt 4 : Ajouter des Catégories
**Objectif** : Automatiser l’ajout des catégories dans `/docs/`.  
**Prompt** :  
```markdown
- Catégories à ajouter :  
  1. Bases du Langage Python → `/docs/bases-langage-python`.  
  2. Programmation Orientée Objet → `/docs/poo`.  
```

**Commandes Git** :
```bash
git status
git add docs/
git commit -m "Prompt 4 - Ajout de catégories"
```

---

### Prompt 5 : Tout Casser pour Tester Git
**Objectif** : Créer volontairement une version chaotique pour tester Git.  
**Prompt** :  
```markdown
- Modifications :  
  - Supprimer tous les styles CSS.  
  - Remplacer tous les titres par "ERREUR 404".  
  - Ajouter des animations clignotantes et des couleurs rouges.  
```

**Commandes Git** :
```bash
git status
git add src/css/custom.css src/pages/index.js
git commit -m "Prompt 5 - Version chaotique pour tester Git"
```

---

## Partie 3 : Restaurer une Version Précédente avec Git

1. **Lister les Commits** :  
   ```bash
   git log
   ```
2. **Restaurer une Version Stable** :  
   ```bash
   git checkout <commit_id>
   ```
3. **Relancez le Site** :  
   ```bash
   npm start
   ```

---

## Partie 4 : Workflow Git Recommandé

1. **Initialisation** :  
   ```bash
   git init
   git config --global user.name "Votre Nom"
   git config --global user.email "votre.email@example.com"
   ```
2. **Enregistrement des Modifications** :  
   ```bash
   git add .
   git commit -m "Votre message"
   ```
3. **Pousser vers GitHub** :  
   ```bash
   git push origin main
   ```

---

### Bonnes Pratiques

- **Stabilité** : Gardez une branche `main` stable.  
- **Branches Fonctionnelles** : Créez une branche par fonctionnalité ou modification risquée.  
- **Restauration** : Utilisez `git checkout` pour tester des versions antérieures.  

Ce guide vous assure une gestion efficace des prompts et des versions avec Git.
