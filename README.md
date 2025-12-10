# Documentation du Projet CV en Ligne

## 🎯 Objectif du Projet

Ce projet a pour but de créer et publier un **CV interactif en ligne**.  
Il utilise **Hugo** pour générer le site, et **GitHub Pages** pour l’hébergement.  
Le CV peut être consulté en local pendant le développement, ou directement en ligne après déploiement.

---

## 🧩 Méthodes pour Générer et Afficher le CV

### ✅ 1. Méthode Locale (sur votre machine)

Cette méthode permet de tester et modifier le CV avant de le mettre en ligne.

1. Installer Hugo  
2. Ouvrir le projet dans VS Code ou dans un terminal  
3. Lancer le serveur local : ```hugo server -D```

```bash
hugo server -D
```
4. Accéder au CV dans un navigateur : ```http://localhost:1313```

Avantage : aperçu instantané après chaque modification.

### ✅ 2. Méthode en Ligne (hébergée sur GitHub Pages)

Après avoir poussé le projet sur GitHub, le CV est automatiquement publié à l’adresse : ```https://onsbbr.github.io/```

Chaque mise à jour envoyée sur GitHub déclenche une reconstruction automatique du site via GitHub Actions.

Avantage : CV consultable par n’importe qui, simplement via le lien.

---

## 📚 Termes Clés

### Hugo

Générateur de sites statiques permettant de créer des sites rapides à partir de fichiers Markdown, HTML et templates.
Il convertit les fichiers du projet en un site complet dans le dossier **public/**.

### Git

Outil de gestion de versions permettant de suivre les modifications et de collaborer.
Il permet d’enregistrer, revenir en arrière, et synchroniser le code.

### GitHub

Plateforme en ligne permettant d’héberger des projets Git.
C’est ici que le code du CV est stocké et mis à jour.

### GitHub Pages

Service de GitHub permettant d’héberger gratuitement un site web statique.
Il prend le dossier généré par Hugo et le rend accessible via une URL publique (ex : onsbbr.github.io).

### GitHub Actions

Système d’automatisation de GitHub.
Dans ce projet, il sert à :

- reconstruire le site Hugo
- publier automatiquement les fichiers sur GitHub Pages
- mettre à jour le site sans intervention manuelle

---

## Résumé

Ce projet permet de :

- Construire un CV moderne
- L'afficher localement via ```http://localhost:1313```
- Le publier en ligne via ```https://onsbbr.github.io/```
- Automatiser le déploiement grâce à GitHub Actions



















# CV Design Documentation

## 1. Introduction

Ce projet explique comment créer, modifier et publier un CV en local ou en ligne à l’aide de **Hugo**, **GitHub** et **GitHub Pages**.  
Il guide pas à pas depuis la création du dépôt jusqu’à la mise en ligne du site final.

---

## 2.  Prérequis

Avant de commencer, assurez-vous d'avoir :

-   Un compte **GitHub**
-   Installer **Hugo** sur votre machine
-   **VS Code** ou un autre éditeur
-   **Git** installé

---

## 3. Étapes de création
### 1. Login to GitHub

![Architecture de séquence](/docs/pictures/login.png "Architecture de séquences")

### 2. Create a new repository 

![Architecture de séquence](/docs/pictures/newrepo.png "Architecture de séquences")

#### Remarque

Garde le projet public.

![Architecture de séquence](/docs/pictures/public.png "Architecture de séquences")


### 3. Go to your project

![Architecture de séquence](/docs/pictures/project.png "Architecture de séquences")
