# Méthode 1 : Configuration avec VSCode et GitHub

Cette méthode utilise une configuration manuelle de CV et reconstruit automatiquement votre site à chaque modification (push).

## Prérequis
- Un compte GitHub
- VSCode installé sur votre ordinateur
- Git installé sur votre système

## Étape 1 : Configuration du Projet Local

Veuillez appliquer cette structure pour pouvoir suivre les démarches qui suivent :

1. **Créer la structure du projet**
   - Créez un dossier vide sur votre ordinateur (par exemple `GITHUB` sur votre bureau)
   - Ouvrez VSCode et ouvrez ce dossier : `File → Open Folder → GITHUB → Select folder`

2. **Structure recommandée du projet**
```
   GITHUB/
   ├── docs/
   │   ├── documentation/
   │   └── pictures/
   ├── index.html
   └── README.md
```

3. **Description des fichiers**
   - `index.html` : Contient le code HTML de votre CV
   - `README.md` : Explique l'objectif de votre projet (avoir un CV en ligne)
   - `docs/` : Dossier pour fichiers et ressources supplémentaires
   - `docs/documentation/` : Documentations détaillées pour aider à comprendre le projet
   - `docs/pictures/` : Toutes les images du projet

## Étape 2 : Déploiement sur GitHub

1. **Créer un nouveau repository sur GitHub**

   - Connectez-vous à votre compte GitHub
   - Créez un nouveau repository (de préférence nommé `votre-nom.github.io`)

![Architecture de séquence](/docs/pictures/CreateNewRepo.png "Architecture de séquences")
![Architecture de séquence](/docs/pictures/NameNewRepo.png "Architecture de séquences")
![Architecture de séquence](/docs/pictures/configurationPublic.png "Architecture de séquences")
![Architecture de séquence](/docs/pictures/boutonCreation.png "Architecture de séquences")

2. **Initialiser Git dans VSCode**

   - Ouvrez le terminal dans VSCode (Git Bash recommandé)
   - Exécutez les commandes suivantes :
```bash
   git init
   git add .
   git commit -m "Mon premier commit"
```
![Architecture de séquence](/docs/pictures/phase1.png "Architecture de séquences")

3. **Lier le projet local à GitHub**

   - Copiez les commandes fournies par GitHub après la création du repository
   - Exécutez dans le terminal :
```bash
   git remote add origin git@github.com:votre-nom/votre-nom.github.io.git
   git branch -M main
   git push -u origin main
```

## Étape 3 : Activer GitHub Pages

1. Allez dans les paramètres du repository : `Settings → Pages`
2. Sous "Source", sélectionnez `Deploy from a branch`
3. Choisissez la branche `main` et le dossier `/ (root)`
4. Cliquez sur `Save`

![Architecture de séquence](/docs/pictures/githubpages.png "Architecture de séquences")

---

Votre CV sera accessible à l'adresse : `https://votre-nom.github.io`