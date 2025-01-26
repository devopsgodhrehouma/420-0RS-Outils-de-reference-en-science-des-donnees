### **Examen Git et HTML/CSS : La Page Magique**

---

#### **Objectif :**  
Créer une page web simple et élégante avec HTML/CSS et un peu de JavaScript, tout en apprenant à utiliser Git pour sauvegarder et gérer vos versions. Chaque étape nécessite une sauvegarde via Git. Vous devez également apprendre à corriger des erreurs en revenant à une version précédente du projet.

**Attention :** Vous ne devez **pas recevoir les commandes Git** directement. Vous devrez les deviner et les écrire dans les espaces prévus.

---

### **Étape 1 : Initialisation du Projet**

1. Créez un dossier pour ce projet et placez-y deux fichiers :
   - `index.html` : contient la structure de base d'une page HTML avec un titre et un lien vers une feuille de style.
   - `style.css` : contient un style de base pour la page, avec un texte centré et des couleurs par défaut.  

**Exemple attendu dans `index.html` :**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Page Magique</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Bienvenue sur la Page Magique</h1>
</body>
</html>
```

**Exemple attendu dans `style.css` :**
```css
body {
    font-family: Arial, sans-serif;
    text-align: center;
    background-color: white;
    color: black;
}
```

2. **Initialisez un dépôt Git dans ce dossier.**  
   *Écrivez ici la commande utilisée :*  
   ```
   
   ```

3. **Sauvegardez cette première version dans Git.**  
   *Écrivez ici les commandes utilisées :*  
   ```
   
   ```

---

### **Étape 2 : Ajout d’un Bouton**

1. Ajoutez un bouton en bas du texte dans `index.html`. Exemple :  
   ```html
   <button>Appuyez-moi</button>
   ```

2. Ajoutez du style au bouton dans `style.css` :  
   - Le bouton doit avoir une couleur de fond bleue, un texte blanc, un effet de survol avec une couleur plus foncée, et une bordure arrondie.

3. **Sauvegardez les modifications avec Git.**  
   *Écrivez ici les commandes utilisées :*  
   ```
   
   ```

---

### **Étape 3 : Ajout d’un Message Dynamique**

1. Ajoutez un script JavaScript à `index.html` pour afficher un message lorsque l’utilisateur clique sur le bouton. Exemple :  
   ```html
   <script>
       function showMessage() {
           document.getElementById('message').innerText = "Vous êtes magique ! 🌟";
       }
   </script>
   ```

2. Ajoutez un paragraphe vide pour afficher ce message. Exemple :  
   ```html
   <p id="message"></p>
   ```

3. **Sauvegardez les modifications avec Git.**  
   *Écrivez ici les commandes utilisées :*  
   ```
   
   ```

---

### **Étape 4 : Amélioration Visuelle**

1. Modifiez `style.css` pour ajouter un arrière-plan dégradé à la page. Exemple :  
   ```css
   background: linear-gradient(to bottom, #ff7e5f, #feb47b);
   ```

2. **Sauvegardez les modifications avec Git.**  
   *Écrivez ici les commandes utilisées :*  
   ```
   
   ```

---

### **Étape 5 : Ajout d’un Effet de Transition**

1. Ajoutez un effet de transition fluide au bouton dans `style.css`. Exemple :  
   ```css
   button {
       transition: all 0.3s ease;
   }
   ```

2. **Sauvegardez les modifications avec Git.**  
   *Écrivez ici les commandes utilisées :*  
   ```
   
   ```

---

### **Étape 6 : La Catastrophe**

1. Modifiez `index.html` pour simuler une erreur. Par exemple, remplacez le contenu par :  
   ```html
   <body>
       <h1>ERREUR 404</h1>
       <button onclick="showMessage()">Plus rien ne fonctionne...</button>
       <p id="message">Oups ! Tout est cassé.</p>
   </body>
   ```

2. Modifiez `style.css` pour rendre la page visuellement chaotique :  
   ```css
   body {
       background-color: red;
       color: yellow;
   }
   button {
       animation: clignote 1s infinite;
   }
   @keyframes clignote {
       0% { opacity: 1; }
       50% { opacity: 0; }
       100% { opacity: 1; }
   }
   ```

3. **Sauvegardez les modifications avec Git.**  
   *Écrivez ici les commandes utilisées :*  
   ```
   
   ```

---

### **Étape 7 : Restauration de la Version Précédente**

1. Utilisez Git pour afficher l’historique des commits. Identifiez le commit avant la catastrophe.  
   *Écrivez ici la commande utilisée :*  
   ```
   
   ```

2. Revenez à ce commit stable et restaurez la version correcte de votre projet.  
   *Écrivez ici les commandes utilisées :*  
   ```
   
   ```

---

### **Conclusion :**  
Expliquez comment vous avez utilisé Git pour gérer votre projet, sauvegarder vos étapes et corriger une erreur. 🎓
