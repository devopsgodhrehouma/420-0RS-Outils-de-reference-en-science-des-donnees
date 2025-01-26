### **Projet HTML/CSS pour Maîtriser Git pas à pas : La Page Magique**

**Objectif :** Apprendre à utiliser Git avec un projet simple mais complet. Vous allez créer une page web magique avec HTML/CSS (et un peu de JavaScript). À chaque étape, vous ferez un commit pour garder une trace des modifications. Ensuite, vous apprendrez à réparer une erreur en restaurant une version précédente.

---

### **Étape 1 : Initialisation du Projet**

1. **Créez un dossier pour le projet :**
   ```bash
   mkdir projet-magique
   cd projet-magique
   ```

2. **Initialisez un dépôt Git :**
   ```bash
   git init
   ```

3. **Créez les fichiers nécessaires :**
   - *index.html* :
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
   - *style.css* :
     ```css
     body {
         font-family: Arial, sans-serif;
         text-align: center;
         background-color: white;
         color: black;
     }
     ```

4. **Ajoutez les fichiers au dépôt et faites un commit :**
   ```bash
   git add .
   git commit -m "Initialisation du projet avec une page HTML de base"
   ```

---

### **Étape 2 : Ajout d’un Bouton Magique**

1. **Ajoutez un bouton dans *index.html* :**
   ```html
   <body>
       <h1>Bienvenue sur la Page Magique</h1>
       <button>Appuyez-moi</button>
   </body>
   ```

2. **Ajoutez du style pour le bouton dans *style.css* :**
   ```css
   button {
       background-color: blue;
       color: white;
       padding: 10px 20px;
       border: none;
       border-radius: 5px;
       cursor: pointer;
   }
   button:hover {
       background-color: darkblue;
   }
   ```

3. **Ajoutez et validez les modifications :**
   ```bash
   git add .
   git commit -m "Ajout d'un bouton magique avec des styles"
   ```

---

### **Étape 3 : Ajout d’un Message Dynamique**

1. **Ajoutez un script dans *index.html* :**
   ```html
   <body>
       <h1>Bienvenue sur la Page Magique</h1>
       <button onclick="showMessage()">Appuyez-moi</button>
       <p id="message"></p>
       <script>
           function showMessage() {
               document.getElementById('message').innerText = "Vous êtes magique ! 🌟";
           }
       </script>
   </body>
   ```

2. **Ajoutez et validez les modifications :**
   ```bash
   git add .
   git commit -m "Ajout d'un message dynamique avec JavaScript"
   ```

---

### **Étape 4 : Amélioration Visuelle**

1. **Ajoutez un arrière-plan dégradé dans *style.css* :**
   ```css
   body {
       font-family: Arial, sans-serif;
       text-align: center;
       background: linear-gradient(to bottom, #ff7e5f, #feb47b);
       color: white;
       margin: 0;
       height: 100vh;
       display: flex;
       flex-direction: column;
       justify-content: center;
       align-items: center;
   }
   ```

2. **Ajoutez et validez les modifications :**
   ```bash
   git add .
   git commit -m "Ajout d'un arrière-plan dégradé"
   ```

---

### **Étape 5 : Ajout d’un Effet de Transition**

1. **Ajoutez une transition au bouton dans *style.css* :**
   ```css
   button {
       transition: all 0.3s ease;
   }
   ```

2. **Ajoutez et validez les modifications :**
   ```bash
   git add .
   git commit -m "Ajout d'une transition fluide au bouton"
   ```

---

### **Étape 6 : La Catastrophe !**

1. **Remplacez le contenu de *index.html* par ceci :**
   ```html
   <body>
       <h1>ERREUR 404</h1>
       <button onclick="showMessage()">Plus rien ne fonctionne...</button>
       <p id="message">Oups ! Tout est cassé.</p>
   </body>
   ```

2. **Ajoutez un style chaotique dans *style.css* :**
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

3. **Ajoutez et validez les modifications :**
   ```bash
   git add .
   git commit -m "Ajout d'une version chaotique pour tester Git"
   ```

---

### **Étape 7 : Restauration de la Version Précédente**

1. **Listez les commits pour voir l’historique :**
   ```bash
   git log --oneline
   ```

   Exemple de sortie :
   ```
   a1b2c3d (HEAD -> main) Ajout d'une version chaotique pour tester Git
   4e5f6g7 Ajout d'une transition fluide au bouton
   8h9i0j1 Ajout d'un arrière-plan dégradé
   2k3l4m5 Ajout d'un message dynamique avec JavaScript
   6n7o8p9 Ajout d'un bouton magique avec des styles
   q1r2s3t Initialisation du projet avec une page HTML de base
   ```

2. **Revenez au dernier commit stable (avant la catastrophe) :**
   ```bash
   git checkout 4e5f6g7
   ```

3. **Mettez à jour la branche principale :**
   ```bash
   git branch -f main HEAD
   git switch main
   ```

4. **Vérifiez que tout est restauré correctement.**

---

### **Conclusion**

Vous avez appris à :
- Initialiser un projet avec Git.
- Faire des commits réguliers.
- Suivre les modifications étape par étape.
- Restaurer une version stable après une erreur.

🎉 Félicitations, vous êtes prêt à maîtriser Git pour vos projets futurs !
