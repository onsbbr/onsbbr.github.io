# Guide pratique

## 1. Introduction

Ce guide présente les étapes essentielles pour démarrer rapidement vos projets, les connecter à GitHub, créer un CV basé sur un portfolio Hugo, et publier votre site en ligne grâce à GitHub Pages.

## 2.  Comment faire

-   Comment connecter VS Code à GitHub ?
-   Comment installer Hugo ?
-   Quelles sont les étapes de création du CV à partir du thème Aafu

## 3. Réponses

### Connectez VScode à GitHub

Pour connecter votre projet créé dans VS Code à votre compte GitHub, suivez les étapes ci-dessous :

1. Ouvrez votre projet dans VS Code  
2. Dans le terminal, initialisez Git :

```bash
git init
git add .
git commit -m "first commit"
```
![Architecture de séquence](/docs/pictures/terminal1.png "Architecture de séquences")

3. Copiez l’URL de votre dépôt GitHub :

![Architecture de séquence](/docs/pictures/lien.png "Architecture de séquences")

4. Ajoutez ce lien comme dépôt distant :

```bash
git remote add origin https://github.com/onsbbr/onsbbr.github.io.git
```

5. Vérifiez que la connexion est correcte :

```bash
git remote -v
```
![Architecture de séquence](/docs/pictures/terminal2.png "Architecture de séquences")

6. Poussez votre projet vers GitHub :

```bash
git branch -M main
git push -u origin main
```
![Architecture de séquence](/docs/pictures/terminal3.png "Architecture de séquences")

7. Mise à jour du projet :

```bash
git init
git add .
git commit -m "votre message"
```

### Installer Hugo

Hugo est un générateur de sites statiques compatible avec plusieurs systèmes d’exploitation, notamment Windows, Linux et macOS. Les méthodes d’installation peuvent varier selon le système utilisé.

Dans ce projet, l’installation a été réalisée sur Windows. Les étapes suivies sont les suivantes :

1. Accédez au site officiel de Hugo : `https://gohugo.io`
2. Dans la section Download, téléchargez la version Hugo Extended pour Windows (fichier .zip), car elle est nécessaire pour les thèmes utilisant des outils comme SCSS.
3. Décompressez le fichier téléchargé et récupérez le fichier hugo.exe.
4. Placez le fichier hugo.exe dans un dossier dédié, par exemple :

### Étapes de création du CV à partir du thème Aafu

Pour installer le thème `aafu` veuillez suivre les étapes suivantes :

1. Ajoutez le thème 
```bash
git submodule add https://github.com/darshanbaral/aafu.git themes/aafu
```

2. Copiez les fichiers/dossiers suivants de `aafu/` vers la racine de votre projet :

- Fichiers : 
    
    - config.yaml
    - package.json
    - tailwind.config.js

- Dossiers :

    - assets/
    - static/
    
3. Activez le thème en le configurant dans le fichier `config.yaml` :
```bash
theme: aafu
```

4. Modifiez le fichier `layouts/index.html` pour personnaliser vos informations personnelles (nom, expériences, compétences, etc.).
5. Remplacez `profile.jpg` dans `static/images` par votre propre image de profil
6. Installez les dépendances et démarrez le serveur de développement :
```bash
npm install
hugo server
```
7. Accédez à votre CV sur http://localhost:1313
