
# Atelier Git : Maîtriser les Fondamentaux

Bienvenue dans notre atelier Git ! Ce document vous guidera à travers les différentes étapes de notre session, en mettant l'accent sur les bonnes pratiques, la gestion des branches, et la résolution de problèmes courants avec Git.

## 1. Introduction à Git

Git est un système de contrôle de version décentralisé qui permet de suivre les modifications apportées aux fichiers. Chaque modification est enregistrée sous forme de "commit", identifié par un SHA unique. Laissez moi vous expliquez un petit plus ! 

Demo de comment Git marche ! 

### Commandes de base :

- Initialiser un dépôt Git : **`git init`**

- Cloner un dépôt existant : **`git clone [url]`**

- Vérifier l'état des fichiers : **`git status`**

- Ajouter des fichiers à un commit : **`git add [fichier]`**

- Créer un commit : **`git commit -m "message du commit"`**

## 2. Bonnes Pratiques d'Utilisation de Git

Pourquoi ne pas coder sur la main branche ? Quels autres pratiques à appliquées ?

### .gitignore

Pour éviter de suivre des fichiers inutiles, utilisez un fichier **`gitignore`**.

```bash
# Exemple de .gitignore
node_modules/
*.log
.idea/
```

### Nomination

- **Branches** : Utilisez des noms descriptifs, par exemple `feature/add-login-page`.

- **Commits** : Les messages doivent être clairs et refléter les modifications, par exemple `git commit -m "Ajout de la page de connexion"`.

## 3. Gestion des Branches

### Créer une branche

Pour travailler sur une nouvelle fonctionnalité sans affecter la branche principale :

```bash
git branch feature/nouvelle-fonctionnalite
git checkout feature/nouvelle-fonctionnalite
``` 
Ou plus simplement : `git checkout -b feature/nouvelle-fonctionnalite`

**HERE** vous devez créer une branche pour acceuillir la nouvelle feature `cart`. 

### Ajouter du contenu 
Vous le contenu que vous allez devoir ajouter.
**HERE** Vous trouverez le contenu à ajouter dans le dossier `content_to_add``

### Fusionner les branches

Pour fusionner votre branche de fonctionnalité avec la branche `develop` :
```bash
git checkout develop
git merge feature/nouvelle-fonctionnalite
```

**HERE** vous devez fusionner votre branche avec la branche develop.

### Résoudre les conflits

Si des conflits surviennent, Git vous indiquera les fichiers concernés. Ouvrez-les, résolvez les conflits manuellement, vous serez souvent aidés par votre IDE ! Puis :
```bash
git add [fichier résolu]
git commit
```

### Exemple de conflict editor
(insérer example conflict editor)

## 4. Jouer du versionning 

Exceptionnellement vous travaillerez directement sur la branche develop. Cela peut arriver mais doit rester exceptionnel. 
Vous allez ici effectuer des modifications et les envoyées pour avoir un nouveau commit.

**HERE** Vous ajouterez le contenu sur la feature `shop` sur la branche develop.

```bash
git checkout develop
# Effectuez vos modifications
git add .
git commit -m "Ajout direct sur develop"
git push
```

### Annuler des Modifications

Pour revenir à un état antérieur :

- Revert : Crée un nouveau commit qui annule les modifications : `git revert[SHA du commit]`
- Reset : Supprime l'historique des commits : `git reset --hard [SHA du commit précédent]`

Vous avez peut-être déjà vu cette syntaxe avec des valeurs relatives :
```bash
$ git reset actuel~2 (Utilisation d'une valeur relative avant le tag "actuel")
```

**HERE** Vous retournez sur le commit précédent votre ajout de la feature `shop`

## 5. Gestion des Fichiers Volumineux

### Pousser un fichier volumineux (Exemple d'erreur)
```bash
git add fichier-volumineux.png
git commit -m "Ajout d'une image volumineuse"
git push
# Git affichera une erreur concernant la taille du fichier
```

### Solution alternative: Git LFS
```bash
git lfs install
git lfs track "*.png"
git add .gitattributes
git add fichier-volumineux.png
git commit -m "Ajout d'une image avec Git LFS"
git push
```

## 6. Conclusion

Nous espérons que cet atelier vous a donné une bonne introduction à Git et à ses fonctionnalités clés. N'oubliez pas que la pratique régulière est essentielle pour maîtriser Git. N'hésitez pas à expérimenter et à poser des questions si vous en avez.

Bonne continuation et bon codage !