# Méthode 2 : Déploiement Automatique avec GitHub Actions

Cette méthode utilise Hugo (un générateur de site statique) et reconstruit automatiquement votre site à chaque modification (push).

## Prérequis
- Un compte GitHub
- VSCode installé sur votre ordinateur
- Git installé sur votre système
- Hugo installé ([Guide d'installation Hugo](https://gohugo.io/installation/))

## Avantages
- Déploiement automatique à chaque push
- Pas besoin de déploiement manuel
- Idéal pour les mises à jour fréquentes
- Large choix de thèmes professionnels
- Génération rapide du site

## Étape 1 : Configuration du Projet

1. **Créer la structure du projet**
   - Créez un dossier vide sur votre ordinateur (par exemple `GITHUB` sur votre bureau)
   - Ouvrez VSCode et ouvrez ce dossier : `File → Open Folder → GITHUB → Select folder`

2. **Choisir, installer et configurer un thème**

   - Visitez `https://themes.gohugo.io/` pour explorer les thèmes disponibles
   - Suivez les instructions d'installation et de modifications spécifiques au thème choisi (vous trouverez les étapes dans `/docs/documentation/GUIDE.md`)

4. **Tester localement**
```bash
   hugo server -D
```
Visitez `http://localhost:1313` pour prévisualiser votre site

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

3. **Lier le projet local à GitHub**

   - Copiez les commandes fournies par GitHub après la création du repository
   - Exécutez dans le terminal :
```bash
   git remote add origin git@github.com:votre-nom/votre-nom.github.io.git
   git branch -M main
   git push -u origin main
```

2. **Activer GitHub Pages et Actions**

   - Allez dans les paramètres du repository : `Settings` → `Pages`
   - Sous `Source`, sélectionnez `GitHub Actions`
   - Cliquez sur browse all workflows et cherche le workflow `hugo`, ensuite `Configure`

![Configuration du workflow GitHub Actions](/docs/pictures/workflowhugo.png "Fichier workflow Hugo")

GitHub créera automatiquement un fichier de workflow situé dans `.github/workflows/hugo.yml`. Ce fichier contient une configuration prête à l’emploi pour construire et déployer un site Hugo.

![Configuration du workflow GitHub Actions](/docs/pictures/hugoyml.png "Fichier workflow Hugo")

3. **Enregistrer le workflow**

Aucune modification n’est nécessaire. Validez simplement avec **Commit changes**.
Dès que vous poussez du nouveau contenu dans votre dépôt, GitHub génèrera automatiquement votre site Hugo. Ensuite, sur VS Code, faites un `pull`. Le workflow se déclenchera automatiquement à chaque push.

![Configuration du workflow GitHub Actions](/docs/pictures/commitchanges.png "Fichier workflow Hugo")

## Étape 3 : Vérifier le déploiement

1. Allez dans l'onglet `Actions` de votre repository

![Configuration du workflow GitHub Actions](/docs/pictures/actions.png "Fichier workflow Hugo")


2. Vérifiez que le workflow s'exécute correctement

![Configuration du workflow GitHub Actions](/docs/pictures/pipeline.png "Fichier workflow Hugo")

3. Une fois terminé, votre site sera accessible

Votre site sera accessible à l'adresse : `https://ton_pseudo.github.io/`

## Remarque :
Veuillez changer le contenu du fichier `layouts/index.html` avec vos données personnelles concernant le CV.