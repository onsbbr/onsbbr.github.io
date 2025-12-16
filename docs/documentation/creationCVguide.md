# Guide de Création d'un CV en Ligne avec GitHub Pages

Ce guide vous explique comment créer et déployer votre propre CV en ligne en utilisant GitHub Pages. Deux méthodes sont disponibles selon vos préférences :

- Méthode 1 : Configuration avec VSCode et GitHub
- Méthode 2 : Déploiement automatiquement avec GitHub Actions

## Méthode 1 : Configuration avec VSCode et GitHub (Recommandée)

### Prérequis
- Un compte GitHub
- VSCode installé sur votre ordinateur
- Git installé sur votre système

### Étape 1 : Configuration du Projet Local

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
![Architecture de séquence](/docs/pictures/structureGITHUB.png "Architecture de séquences")

3. **Description des fichiers**
   - `index.html` : Contient le code HTML de votre CV
   - `README.md` : Explique l'objectif de votre projet (avoir un CV en ligne)
   - `docs/` : Dossier pour fichiers et ressources supplémentaires
   - `docs/documentation/` : Documentations détaillées pour aider à comprendre le projet
   - `docs/pictures/` : Toutes les images du projet

### Étape 2 : Déploiement sur GitHub

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
![Architecture de séquence](/docs/pictures/gitPush.png "Architecture de séquences")

---

#### ⚠️ Troubleshooting : Résolution des Problèmes de push

Si vous rencontrez une erreur lors du push, comme celle ci :

![Architecture de séquence](/docs/pictures/gitpushTSH.png "Architecture de séquences")

Veuillez suivre ces étapes pour configurer une clé SSH :

1. **Générer une clé SSH**
```bash
   ssh-keygen -t ed25519 -C "votre-email-github@example.com"
```
![Architecture de séquence](/docs/pictures/sshkeygen.png "Architecture de séquences")

2. **Lancer l'agent SSH**
```bash
   eval "$(ssh-agent -s)"
```

3. **Ajouter la clé à l'agent**
```bash
   ssh-add ~/.ssh/id_ed25519
```

4. **Copier la clé publique**
```bash
   cat ~/.ssh/id_ed25519.pub
```
![Architecture de séquence](/docs/pictures/addkey.png "Architecture de séquences")

5. **Ajouter la clé à GitHub**
   - Connectez-vous à GitHub
   - Allez dans `Settings → SSH and GPG keys`
   - Cliquez sur `New SSH key`
   - Collez la clé copiée et cliquez sur `Add SSH key`

![Architecture de séquence](/docs/pictures/newSSHkey.png "Architecture de séquences")
![Architecture de séquence](/docs/pictures/sshKEYcreated.png "Architecture de séquences")


6. **Retenter le push**

   - La commande `git push` devrait maintenant fonctionner

![Architecture de séquence](/docs/pictures/gitpushaftersshkey.png "Architecture de séquences")

---

### Étape 3 : Activer GitHub Pages

1. Allez dans les paramètres du repository : `Settings → Pages`
2. Sous "Source", sélectionnez `Deploy from a branch`
3. Choisissez la branche `main` et le dossier `/ (root)`
4. Cliquez sur `Save`

![Architecture de séquence](/docs/pictures/githubpages.png "Architecture de séquences")

Votre CV sera accessible à l'adresse : `https://votre-nom.github.io`

## Méthode 2 : Déploiement Automatique avec GitHub Actions

Cette méthode utilise Hugo (un générateur de site statique) et reconstruit automatiquement votre site à chaque modification (push).

### Prérequis
- Un compte GitHub
- VSCode installé sur votre ordinateur
- Git installé sur votre système
- Hugo installé ([Guide d'installation Hugo](https://gohugo.io/installation/))

### Avantages
- Déploiement automatique à chaque push
- Pas besoin de déploiement manuel
- Idéal pour les mises à jour fréquentes
- Large choix de thèmes professionnels
- Génération rapide du site

### Étape 1 : Configuration du Projet

1. **Créer un nouveau repository sur GitHub**
   - Connectez-vous à votre compte GitHub
   - Créez un nouveau repository (exemple : `onsbbr.github.io`)

2. **Initialiser un projet Hugo localement**
```bash
   hugo new site onsbbr.github.io
   cd onsbbr.github.io
   git init
```

3. **Choisir et installer un thème**

   - Visitez `https://themes.gohugo.io/` pour explorer les thèmes disponibles
   - Exemple avec le thème [aafu](https://github.com/darshanbaral/aafu) :
```bash
   git submodule add https://github.com/darshanbaral/aafu.git themes/aafu
```

4. **Configurer le thème**
   - Suivez les instructions d'installation spécifiques au thème choisi (vous trouverez les étapes dans ```/docs/documentation/GUIDE.md```)
   - Modifiez le fichier `config.toml` ou `hugo.toml` selon les recommandations du thème
   - Personnalisez le contenu dans le dossier `content/`

![Exemple de configuration du thème AAFU](/docs/pictures/aafutheme.png "Configuration du thème AAFU")

5. **Tester localement**
```bash
   hugo server -D
```
   Visitez `http://localhost:1313` pour prévisualiser votre site

6. **Commit et push initial**
```bash
   git add .
   git commit -m "Mon premier commit"
   git remote add origin git@github.com:votre-nom/onsbbr.github.io.git
   git branch -M main
   git push -u origin main
```

### Étape 2 : Activer et configurer GitHub Pages

1. Allez dans les paramètres du repository : `Settings → Pages`
2. Sous "Source", sélectionnez `GitHub Actions`
3. Cliquez sur `brwose all workflows` et cherche le workflow `hugo`

![Configuration du workflow GitHub Actions](/docs/pictures/workflowhugo.png "Fichier workflow Hugo")

GitHub créera automatiquement un fichier de workflow situé dans `.github/workflows/hugo.yml`. Ce fichier contient une configuration prête à l’emploi pour construire et déployer un site Hugo.

![Configuration du workflow GitHub Actions](/docs/pictures/hugoyml.png "Fichier workflow Hugo")

4. Enregistrer le workflow

Aucune modification n’est nécessaire. Validez simplement avec **Commit changes**.
Dès que vous poussez du nouveau contenu dans votre dépôt, GitHub génèrera automatiquement votre site Hugo. Ensuite, sur VS Code, faites un `pull`. Le workflow se déclenchera automatiquement à chaque push.

![Configuration du workflow GitHub Actions](/docs/pictures/commitchanges.png "Fichier workflow Hugo")

### Étape 3 : Vérifier le déploiement

1. Allez dans l'onglet `Actions` de votre repository

![Configuration du workflow GitHub Actions](/docs/pictures/pipeline.png "Fichier workflow Hugo")

2. Vérifiez que le workflow s'exécute correctement

![Configuration du workflow GitHub Actions](/docs/pictures/success.png "Fichier workflow Hugo")

3. Une fois terminé, votre site sera accessible

Votre site sera accessible à l'adresse : `https://ton_pseudo.github.io/repo_name/`

### Mise à jour du site

Pour mettre à jour votre CV :
1. Modifiez le fichier `index.html`
2. Testez localement avec `hugo server -D`
3. Commit et push vos modifications
4. GitHub Actions déploiera automatiquement les changements

---

## Notes Importantes

- La première méthode est recommandée pour les débutants
- Assurez-vous que votre repository est public pour utiliser GitHub Pages gratuitement
- Le nom du repository `votre-nom.github.io` vous donnera une URL personnalisée
- Les modifications peuvent prendre quelques minutes avant d'être visibles en ligne

## Ressources Supplémentaires

- [Documentation GitHub Pages](https://docs.github.com/pages)
- [Guide Git](https://git-scm.com/doc)
- [Documentation VSCode](https://code.visualstudio.com/docs)
- [Documentation Hugo](https://gohugo.io/documentation/)
- [Thèmes Hugo](https://themes.gohugo.io/)