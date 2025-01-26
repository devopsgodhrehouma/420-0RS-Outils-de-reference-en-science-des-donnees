# QUIZ

### 1. **Quelle commande utiliseriez-vous pour basculer vers une autre branche ?**
   - A. `git switch [nom-de-branche]`
   - B. `git branch [nom-de-branche]`
   - C. `git checkout [nom-de-branche]`
   - D. `git jump [nom-de-branche]`

### 2. **Quelle commande Git est utilisée pour appliquer les derniers changements sauvegardés dans le stash sans les supprimer de la liste de stash ?**
   - A. `git stash pop`
   - B. `git stash apply`
   - C. `git stash clear`
   - D. `git stash save`

### 3. **Vous souhaitez sauvegarder temporairement vos modifications locales sans les committer afin de pouvoir changer de branche. Quelle commande utilisez-vous ?**
   - A. `git stash save`
   - B. `git commit -m "temp"`
   - C. `git pull`
   - D. `git checkout -b`

### 4. **Comment récupérez-vous les dernières modifications d'un dépôt distant et réappliquez-vous vos commits locaux sur la base de code mise à jour ?**
   - A. `git merge`
   - B. `git rebase`
   - C. `git pull --rebase`
   - D. `git fetch && git reapply`

### 5. **Quelle commande utiliseriez-vous pour résoudre manuellement un conflit de fusion ?**
   - A. `git resolve`
   - B. `git merge --manual`
   - C. `git add [fichier]` suivi de `git merge --continue`
   - D. `git pull`

### 6. **Comment rebaser la branche actuelle sur la branche master ?**
   - A. `git rebase master`
   - B. `git rebase --onto master`
   - C. `git reapply master`
   - D. `git pull --rebase master`

### 7. **Si vous souhaitez fusionner une branche de fonctionnalité dans la branche master, quelle commande utilisez-vous ?**
   - A. `git merge feature`
   - B. `git pull feature`
   - C. `git rebase feature`
   - D. `git commit --merge feature`

### 8. **Quelle commande Git utiliseriez-vous pour lister toutes les branches, locales et distantes ?**
   - A. `git branch`
   - B. `git branch --all`
   - C. `git branch --remote`
   - D. `git list branches`

### 9. **Comment supprimer une branche locale dans Git ?**
   - A. `git branch --delete [nom-de-branche]`
   - B. `git remove [nom-de-branche]`
   - C. `git delete [nom-de-branche]`
   - D. `git branch -d [nom-de-branche]`

### 10. **Vous êtes au milieu d'un rebase et réalisez que vous voulez l'arrêter et tout réinitialiser. Quelle commande devriez-vous utiliser ?**
   - A. `git rebase --abort`
   - B. `git reset --hard`
   - C. `git rebase --stop`
   - D. `git rebase --cancel`

### 11. **Comment récupérez-vous toutes les branches d'un dépôt distant sans fusionner les modifications ?**
   - A. `git pull`
   - B. `git fetch`
   - C. `git sync`
   - D. `git clone`

### 12. **Quelle commande permet de "squasher" plusieurs commits en un seul avant de pousser vers un dépôt distant ?**
   - A. `git squash`
   - B. `git rebase -i HEAD~[nombre]`
   - C. `git commit --squash`
   - D. `git reapply HEAD`

### 13. **Vous travaillez sur une branche de fonctionnalité et vous souhaitez fusionner les changements de `main` dans votre branche pour rester à jour. Quelle commande devriez-vous utiliser ?**
   - A. `git pull main`
   - B. `git merge main`
   - C. `git rebase main`
   - D. `git sync main`

### 14. **Quelle commande Git est utilisée pour indexer toutes les modifications, y compris les suppressions, dans votre répertoire de travail ?**
   - A. `git add .`
   - B. `git add -A`
   - C. `git commit -a`
   - D. `git add *`

### 15. **Comment poussez-vous une nouvelle branche vers un dépôt distant pour la première fois ?**
   - A. `git push origin main`
   - B. `git push origin --all`
   - C. `git push origin [nom-de-branche]`
   - D. `git upload [nom-de-branche]`


### 16.  Quelle commande utilise-t-on pour initialiser (ou créer) un nouveau dépôt Git (repository) ?**  
*Choix unique. (5 points)*  
- git clone  
- git new  
- git init  
- git start

### 17. Quelle commande montre l'état actuel de votre espace de travail ?**  
*Choix unique. (3.5 points)*  
- git show  
- git display  
- git view  
- git status

### 18. Comment ajoutez-vous tous les changements de l'espace de travail à l'index ?**  
*Choix unique. (4 points)*  
- git add .  
- git commit .  
- git push .  
- git update .

### 19. Quelle commande est utilisée pour voir l'historique des commits ?**  
*Choix unique. (2 points)*  
- git logs  
- git history  
- git log  
- git commit-history

### 20. Comment revenez-vous à un commit précédent en utilisant son hash ?**  
*Choix unique. (0.5 points)*  
- git revert [hash]  
- git reset [hash]  
- git return [hash]  
- git back [hash]

### 21. Quelle commande est utilisée pour créer une nouvelle branche ?**  
*Choix unique. (4 points)*  
- git new [branch-name]  
- git create [branch-name]  
- git branch [branch-name]  
- git make [branch-name]

### 22. Comment passez-vous d'une branche à une autre ?**  
*Choix multiples. (4 points)*  
- git checkout [branch-name]  
- git switch [branch-name]  
- git move [branch-name]  
- git jump [branch-name]

### 23. Quelle commande fusionne une branche avec votre branche actuelle ?**  
*Choix unique. (4 points)*  
- git merge [branch-name]  
- git join [branch-name]  
- git fuse [branch-name]  
- git combine [branch-name]

### 24. Comment renommez-vous une branche locale ?**  
*Choix unique. (2 points)*  
- git rename [old-name] [new-name]  
- git branch -m [old-name] [new-name]  
- git mv [old-name] [new-name]  
- git change [old-name] [new-name]

### 25. Comment supprimez-vous une branche locale ?**  
*Choix unique. (0.5 points)*  
- git remove [branch-name]  
- git branch -d [branch-name]  
- git delete [branch-name]  
- git branch -r [branch-name]

### 26. Comment clonez-vous un dépôt distant ?**  
*Choix unique. (5 points)*  
- git copy [url]  
- git download [url]  
- git get [url]  
- git clone [url]

### 27. Quelle commande est utilisée pour voir les différences non indexées ?**  
*Choix unique. (3 points)*  
- git differences  
- git diff  
- git changes  
- git compare

### 28. Comment annulez-vous les modifications non commitées dans un fichier ?**  
*Choix unique. (1 point)*  
- git restore [file]  
- git undo [file]  
- git reverse [file]  
- git return [file]

### 29. Quelle commande est utilisée pour réinitialiser l'index et l'espace de travail, où [commit] est le hash du commit ?**  
*Choix unique. (2 points)*  
- git reset --hard [commit]  
- git revert --hard [commit]  
- git clear --hard [commit]  
- git drop --hard [commit]

### 30. Comment configurez-vous votre email pour Git ?**  
*Choix unique. (5 points)*  
- git config user.email [your-email]  
- git set user.email [your-email]  
- git user email [your-email]  
- git email --config [your-email]

**31. Comment poussez-vous vos changements vers une branche spécifique d'un dépôt distant ?**  
*Choix unique. (5 points)*  
- git push [remote-name] [branch-name]  
- git upload [remote-name] [branch-name]  
- git send [remote-name] [branch-name]  
- git transfer [remote-name] [branch-name]

### 32. Comment récupérez-vous les changements d'une branche spécifique depuis un dépôt distant ?**  
*Choix multiples. (4 points)*  
- git pull [remote-name] [branch-name]  
- git fetch [remote-name] [branch-name] && git merge [remote-name]/[branch-name]  
- git download [remote-name] [branch-name]  
- git get [remote-name] [branch-name]

### 33. Quelle commande est utilisée pour lister toutes les branches locales ?**  
*Choix unique. (5 points)*  
- git list  
- git show-branches  
- git branches  
- git branch

### 34. Comment annulez-vous le dernier commit ?**  
*Choix unique. (0.5 points)*  
- git undo  
- git reset HEAD^  
- git revert HEAD  
- git drop HEAD

### 35. Quelle commande est utilisée pour attacher la HEAD à un commit spécifique ?**  
*Choix unique. (3 points)*  
- git attach HEAD [commit]  
- git connect HEAD [commit]  
- git link HEAD [commit]  
- git checkout [commit]

### 36. Comment fusionnez-vous deux commits en un seul ?**  
*Choix unique. (0.5 points)*  
- git fuse [commit1] [commit2]  
- git combine [commit1] [commit2]  
- git squash [commit1] [commit2]  
- git merge [commit1] [commit2]

### 37. Quelle commande montre les branches qui ont été fusionnées avec la branche actuelle ?**  
*Choix unique. (0.5 points)*  
- git branch --merged  
- git branch --fused  
- git branch --combined  
- git branch --joined

### 38. Comment modifiez-vous le dernier commit sans changer son message de commit ?**  
*Choix unique. (0.5 points)*  
- git commit --amend  
- git commit --edit  
- git commit --redo  
- git commit --modify

### 39. Quelle commande montre les changements entre la branche actuelle et une autre branche ?**  
*Choix unique. (2 points)*  
- git diff [branch-name]  
- git compare [branch-name]  
- git changes [branch-name]  
- git review [branch-name]

### 40. Comment créez-vous un alias pour une commande Git ?**  
*Choix unique. (0.5 points)*  
- git alias [alias-name] [git-command]  
- git config --global alias.[alias-name] [git-command]  
- git shortcut [alias-name] [git-command]  
- git link [alias-name] [git-command]

### 41. Quelle commande est utilisée pour voir la configuration de Git ?**  
*Choix multiples. (2 points)*  
- git settings  
- git show-config  
- git view-config  
- git config --list  
- cat .git/config

### 42. Comment supprimez-vous un fichier de l'index ?**  
*Choix unique. (2 points)*  
- git delete [file-name]  
- git remove [file-name]  
- git unindex [file-name]  
- git rm [file-name]

### 43. Comment modifiez-vous le message du dernier commit ?**  
*Choix unique. (2 points)*  
- git modify-message  
- git edit-message  
- git commit --amend -m "New message"  
- git redo-commit -m "New message"

### 44. Quelle commande est utilisée pour initialiser un nouveau dépôt ?**  
*Choix unique. (0.5 points)*  
- git init --nude  
- git init --bare  
- git init --empty  
- git start --none

### 45. Comment créez-vous une archive de votre dépôt ?**  
*Choix unique. (0.5 points)*  
- git pack  
- git archive  
- git zip  
- git bundle




### 46. Quel est le rôle de la commande `git init` ?
   - A. Initialiser un nouveau dépôt Git.
   - B. Ajouter un fichier au suivi de Git.
   - C. Fusionner des branches.
   - D. Supprimer un dépôt Git.

### 47. **Comment ajouter tous les fichiers modifiés et nouveaux fichiers au staging area (zone d'indexation) ?**
   - A. `git add *`
   - B. `git add .`
   - C. `git add -A`
   - D. `git commit -a`

### 48. **Quelle commande permet de commiter des changements avec un message ?**
   - A. `git save -m "message"`
   - B. `git commit -m "message"`
   - C. `git commit`
   - D. `git save`

### 49. **Que fait la commande `git pull` ?**
   - A. Elle envoie les modifications locales vers le dépôt distant.
   - B. Elle fusionne le dépôt distant avec le dépôt local.
   - C. Elle récupère les changements du dépôt distant et les fusionne dans la branche courante.
   - D. Elle crée une nouvelle branche.

### 50. **Comment basculer vers une autre branche dans Git ?**
   - A. `git change [branch-name]`
   - B. `git branch [branch-name]`
   - C. `git checkout [branch-name]`
   - D. `git switch [branch-name]`

### 51. **Quelle commande permet de lister toutes les branches, locales et distantes ?**
   - A. `git branch`
   - B. `git branch --all`
   - C. `git branch --list`
   - D. `git checkout`

### 52. **Quelle commande fusionne les changements d'une branche dans la branche courante ?**
   - A. `git pull`
   - B. `git merge [branch-name]`
   - C. `git rebase [branch-name]`
   - D. `git checkout [branch-name]`

### 53. **Comment appliquer les modifications enregistrées temporairement avec `git stash` ?**
   - A. `git stash apply`
   - B. `git stash pop`
   - C. `git stash pull`
   - D. `git stash push`

### 54. **Comment annuler le dernier commit sans supprimer les modifications locales ?**
   - A. `git reset --soft HEAD~1`
   - B. `git reset --hard HEAD~1`
   - C. `git revert HEAD`
   - D. `git reset HEAD~1`

### 55. **Quelle commande permet de réécrire l'historique Git en combinant plusieurs commits en un seul ?**
   - A. `git squash`
   - B. `git rebase -i`
   - C. `git merge --squash`
   - D. `git commit --amend`

### 56. **Comment récupérer les modifications du dépôt distant sans les fusionner ?**
   - A. `git fetch`
   - B. `git pull`
   - C. `git merge`
   - D. `git sync`

### 57. **Quel est le rôle de la commande `git checkout -b [branch-name]` ?**
   - A. Créer une nouvelle branche et y basculer.
   - B. Supprimer une branche.
   - C. Afficher l'historique des commits.
   - D. Fusionner une branche dans la branche courante.

### 58. **Quelle commande permet de lister toutes les modifications enregistrées par `git stash` ?**
   - A. `git stash list`
   - B. `git stash show`
   - C. `git stash logs`
   - D. `git stash view`

### 59. **Comment supprimer une branche locale ?**
   - A. `git branch -d [branch-name]`
   - B. `git branch --delete [branch-name]`
   - C. `git remove [branch-name]`
   - D. `git branch -rm [branch-name]`

### 60. **Quelle est la différence entre `git merge` et `git rebase` ?**
   - A. `git merge` crée un commit de fusion, `git rebase` réapplique les commits sur la branche cible.
   - B. `git merge` supprime l'historique, `git rebase` le conserve.
   - C. `git merge` réécrit l'historique, `git rebase` non.
   - D. `git merge` ne peut être utilisé que pour les branches locales, `git rebase` pour les branches distantes.

### 61. **Que se passe-t-il lorsque vous utilisez `git rebase` sur une branche avec des conflits ?**
   - A. Git résout automatiquement les conflits.
   - B. Git vous demande de résoudre les conflits manuellement.
   - C. Git annule le rebase et revient à l'état précédent.
   - D. Git crée une nouvelle branche.

### 62. **Quelle commande est utilisée pour combiner des commits dans un dépôt sans changer leur ordre ?**
   - A. `git merge`
   - B. `git rebase`
   - C. `git cherry-pick`
   - D. `git commit --amend`

### 63. **Comment supprimer définitivement des modifications locales sans les commiter ?**
   - A. `git reset --hard`
   - B. `git reset --soft`
   - C. `git stash`
   - D. `git checkout`

### 64. **Quelle commande permet de faire un commit rapide de tous les fichiers modifiés et suivis ?**
   - A. `git commit -a -m "message"`
   - B. `git commit -m "message"`
   - C. `git commit -A`
   - D. `git add . && git commit -m "message"`

### 65. **Comment forcer le push d'une branche vers le dépôt distant en écrasant l'historique distant ?**
   - A. `git push --force`
   - B. `git push --force-with-lease`
   - C. `git push origin --all`
   - D. `git push -f`

### 66. **Comment résoudre un conflit de fusion dans Git ?**
   - A. Modifier les fichiers concernés, puis utiliser `git add` et `git commit`.
   - B. Utiliser `git reset --hard` pour annuler la fusion.
   - C. Utiliser `git stash` pour ignorer les changements.
   - D. Supprimer le fichier en conflit.

### 67. **Quelle commande permet de supprimer tous les changements locaux non suivis ?**
   - A. `git clean -f`
   - B. `git reset --hard`
   - C. `git stash clear`
   - D. `git remove --untracked`

### 68. **Comment cloner un dépôt Git distant vers votre machine locale ?**
   - A. `git init [URL]`
   - B. `git clone [URL]`
   - C. `git pull [URL]`
   - D. `git checkout [URL]`

### 69. **Que fait la commande `git log --oneline` ?**
   - A. Affiche tous les commits avec une vue simplifiée.
   - B. Affiche le détail de chaque commit.
   - C. Affiche uniquement les branches.
   - D. Montre les différences entre les branches.

### 70. **Comment voir la différence entre deux commits dans un projet ?**
   - A. `git diff`
   - B. `git log`
   - C. `git merge`
   - D. `git status`

### 71. **Comment renommer une branche Git locale ?**
   - A. `git rename [old-name] [new-name]`
   - B. `git branch -m [new-name]`
   - C. `git branch --move [new-name]`
   - D. `git change [new-name]`

### 72. **Quelle commande permet de visualiser l’état actuel des fichiers suivis et non suivis dans le dépôt local ?**
   - A. `git status`
   - B. `git diff`
   - C. `git log`
   - D. `git show`

### 73. **Que fait la commande `git cherry-pick` ?**
   - A. Elle permet de sélectionner un ou plusieurs commits spécifiques à appliquer sur une autre branche.
   - B. Elle crée une nouvelle branche à partir d’un commit spécifique.
   - C. Elle permet de fusionner des commits en conflit.
   - D. Elle supprime un commit spécifique.

### 74. **Quelle commande est utilisée pour rétablir un fichier supprimé dans un dépôt local avant un commit ?**
   - A. `git reset --hard`
   - B. `git restore [file]`
   - C. `git checkout -- [file]`
   - D. `git revert [file]`

### 75. **Comment ajouter un tag annoté à un commit pour indiquer une version ?**
   - A. `git tag -a v1.0 -m "Version 1.0"`
   - B. `git tag v1.0`
   - C. `git commit --tag v1.0`
   - D. `git tag --annotate v1.0`
