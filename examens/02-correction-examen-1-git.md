### **Correction : Exercice Pratique : Découverte de Git avec GitHub**

---

#### **1. Créez un dossier et initialisez un dépôt Git.**
*(Commandes nécessaires pour cette étape)*

```bash
mkdir projet-git
cd projet-git
git init
git status
```

*Explication :*  
- `mkdir projet-git` : Crée un dossier nommé `projet-git`.  
- `cd projet-git` : Entrez dans ce dossier.  
- `git init` : Initialise un dépôt Git dans le dossier courant.  
- `git status` : Vérifie que le dépôt est correctement initialisé (aucun fichier suivi au départ).

---

#### **2. Configurez votre identité locale Git.**
*(Commandes nécessaires pour configurer votre identité locale)*

```bash
git config --global user.name "Votre Nom"
git config --global user.email "votre.email@example.com"
git config --list
```

*Explication :*  
- `git config --global user.name "Votre Nom"` : Définit votre nom pour tous les dépôts locaux.  
- `git config --global user.email "votre.email@example.com"` : Définit votre email pour les commits.  
- `git config --list` : Affiche la configuration Git actuelle, y compris le nom et l’email.

---

#### **3. Créez un fichier nommé `fichier1.txt`, ajoutez du contenu et effectuez un commit.**
*(Commandes nécessaires)*

```bash
echo "Contenu du fichier 1" > fichier1.txt
git status
git add fichier1.txt
git commit -m "Ajout du fichier1.txt avec son contenu initial"
git status
```

*Explication :*  
- `echo "Contenu du fichier 1" > fichier1.txt` : Crée un fichier et y ajoute du contenu.  
- `git add fichier1.txt` : Ajoute le fichier au suivi Git.  
- `git commit -m ...` : Enregistre les modifications avec un message explicatif.

---

#### **4. Créez un fichier nommé `fichier2.txt`, ajoutez du contenu et effectuez un commit.**
*(Commandes nécessaires)*

```bash
echo "Contenu du fichier 2" > fichier2.txt
git status
git add fichier2.txt
git commit -m "Ajout du fichier2.txt avec son contenu initial"
git status
```

---

#### **5. Créez un fichier nommé `fichier3.txt`, ajoutez du contenu et effectuez un commit.**
*(Commandes nécessaires)*

```bash
echo "Contenu du fichier 3" > fichier3.txt
git status
git add fichier3.txt
git commit -m "Ajout du fichier3.txt avec son contenu initial"
git status
```

---

#### **6. Créez un dépôt GitHub et configurez-le comme dépôt distant.**
*(Commandes nécessaires)*

```bash
git remote add origin https://github.com/votre-utilisateur/projet-git.git
git remote -v
git push -u origin main
```

*Explication :*  
- `git remote add origin ...` : Associe le dépôt GitHub en tant que dépôt distant.  
- `git remote -v` : Vérifie que le dépôt distant est correctement configuré.  
- `git push -u origin main` : Pousse les commits locaux vers la branche `main` du dépôt distant.

---

#### **7. Modifiez le fichier `fichier2.txt`, effectuez un commit et poussez les modifications.**
*(Commandes nécessaires)*

```bash
echo "Modification du contenu du fichier 2" >> fichier2.txt
git status
git add fichier2.txt
git commit -m "Modification du fichier2.txt : ajout de contenu"
git push
```

---

#### **8. Changez l’identité Git, modifiez `fichier3.txt`, effectuez un commit et poussez les modifications.**
*(Commandes nécessaires)*

```bash
git config user.name "Nom de votre collègue"
git config user.email "email.collegue@example.com"
echo "Ajout du nom du collègue" >> fichier3.txt
git status
git add fichier3.txt
git commit -m "Ajout du nom du collègue dans fichier3.txt"
git push
```

---

#### **9. Reconfigurez Git avec vos identifiants personnels.**
*(Commandes nécessaires)*

```bash
git config user.name "Votre Nom"
git config user.email "votre.email@example.com"
git config --list
```

---

#### **10. Créez trois fichiers en même temps, effectuez un commit unique et poussez-les.**
*(Commandes nécessaires)*

```bash
echo "Contenu fichier 4" > fichier4.txt
echo "Contenu fichier 5" > fichier5.txt
echo "Contenu fichier 6" > fichier6.txt
git status
git add .
git commit -m "Ajout des fichiers fichier4.txt, fichier5.txt et fichier6.txt"
git push
```

---

#### **11. Affichez l’historique des commits.**
*(Commandes nécessaires)*

```bash
git log --oneline
```

---

#### **12. Vérifiez les informations sur le dépôt distant.**
*(Commandes nécessaires)*

```bash
git remote -v
```

---

### **Résumé des commandes principales utilisées :**

1. Initialisation et configuration :
   - `git init`
   - `git config --global user.name ...`
   - `git config --global user.email ...`

2. Gestion des fichiers :
   - `git add <fichier>`  
   - `git commit -m ...`

3. Dépôt distant :
   - `git remote add origin ...`
   - `git push`

4. Vérifications :
   - `git status`
   - `git log --oneline`
   - `git remote -v`

