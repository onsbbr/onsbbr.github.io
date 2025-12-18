# Guide pratique

## Introduction

Ce guide présente les étapes essentielles pour démarrer rapidement vos projets, les connecter à GitHub, créer un CV basé sur un portfolio Hugo, et publier votre site en ligne grâce à GitHub Pages.

## Questions

-   Comment connecter VS Code à GitHub ?
-   Comment installer Hugo ?
-   Quelles sont les étapes de création du CV à partir du thème Aafu

## Réponses

### 1. Connectez VScode à GitHub

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

### 2. Installer Hugo

Hugo est un générateur de sites statiques compatible avec plusieurs systèmes d’exploitation, notamment Windows, Linux et macOS. Les méthodes d’installation peuvent varier selon le système utilisé.

Dans ce projet, l’installation a été réalisée sur Windows. Les étapes suivies sont les suivantes :

1. Ouvrir PowerShell en mode administrateur
2. Autoriser l'exécution des scripts avec la commande :

```bash
Set-ExecutionPolicy Bypass -Scope Process -Force
```

3. Installer Chocolately

```bash
[System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```

4. Vérifier l'installation :

```bash
choco --version
```

![Architecture de séquence](/docs/pictures/choco_install.png "Initialiser Git")

5. Ouvrir PowerShell en mode administrateur
6. Installer Hugo :

```bash
choco install hugo-extended
```

![Architecture de séquence](/docs/pictures/hugo_install.png "Initialiser Git")

### 3. Étapes de création du CV à partir du thème Aafu

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