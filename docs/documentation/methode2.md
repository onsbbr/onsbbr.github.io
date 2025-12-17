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

## Étape 2 : Activer et configurer GitHub Pages

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

## Étape 3 : Vérifier le déploiement

1. Allez dans l'onglet `Actions` de votre repository

![Configuration du workflow GitHub Actions](/docs/pictures/pipeline.png "Fichier workflow Hugo")

2. Vérifiez que le workflow s'exécute correctement

![Configuration du workflow GitHub Actions](/docs/pictures/success.png "Fichier workflow Hugo")

3. Une fois terminé, votre site sera accessible

Votre site sera accessible à l'adresse : `https://ton_pseudo.github.io/repo_name/`