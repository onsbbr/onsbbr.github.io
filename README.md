# Documentation de conception de CV

## Objectif du Projet

Ce projet propose **deux méthodes différentes** pour créer et mettre en ligne votre CV.  
Vous pouvez choisir celle qui correspond le mieux à vos besoins et à votre niveau technique.
Sachant que le CV peut être consulté en local pendant le développement, ou directement en ligne après déploiement.

## Méthodes pour Générer et Afficher le CV

### 1. Méthode Locale (sur votre machine)

Cette méthode repose sur un fichier **HTML statique** (`index.html`) et un déploiement simple via **GitHub Pages**.  
Elle est idéale pour débuter et pour garder un contrôle total sur le code du CV.

#### Principe
- Le CV est écrit directement en **HTML/CSS**
- Les modifications sont faites localement avec **VS Code**
- Chaque `git push` met automatiquement à jour le CV en ligne

#### Étapes principales
1. Créer la structure du projet (`index.html`, `docs/`, `README.md`)
2. Éditer le CV dans le fichier `index.html`
3. Initialiser Git et pousser le projet sur GitHub
4. Activer GitHub Pages depuis les paramètres du repository

#### Accès au CV
Une fois GitHub Pages activé, le CV est accessible à l’adresse : `https://votre-nom.github.io/`

#### Avantages
- Simple à comprendre et à mettre en place  
- Aucun outil supplémentaire requis  
- Contrôle total du HTML et du CSS  
- Idéal pour un premier CV en ligne

### 2. Méthode 2 : CV avec Hugo et Déploiement Automatique via GitHub Actions

Cette méthode utilise **Hugo**, un générateur de site statique, combiné à **GitHub Actions** pour automatiser le déploiement.  
Elle est recommandée pour un CV plus structuré, évolutif et professionnel.

#### Principe
- Le CV est généré à partir d’un **thème Hugo**
- Le site est testé localement avec le serveur Hugo
- Chaque `git push` déclenche automatiquement :
  - la génération du site
  - le déploiement via GitHub Pages

#### Étapes principales
1. Installer Hugo sur la machine
2. Choisir et configurer un thème Hugo
3. Tester le site en local avec `hugo server -D`
4. Pousser le projet sur GitHub
5. Activer GitHub Pages avec GitHub Actions
6. Utiliser le workflow Hugo généré automatiquement

#### Accès au CV
Après le déploiement automatique, le site est accessible à l’adresse : `https://votre-nom.github.io/`

#### Avantages

- Déploiement entièrement automatique
- Mise à jour rapide et sans action manuelle
- Large choix de thèmes professionnels
- Structure claire et maintenable
- Idéal pour des mises à jour fréquentes

## Termes Clés

### Hugo

Générateur de sites statiques permettant de créer des sites rapides à partir de fichiers Markdown, HTML et templates.
Il convertit les fichiers du projet en un site complet dans le dossier **public/**.

### Git

Outil de gestion de versions permettant de suivre les modifications et de collaborer. Il permet d’enregistrer, revenir en arrière, et synchroniser le code.

### GitHub

Plateforme en ligne permettant d’héberger des projets Git. C’est ici que le code du CV est stocké et mis à jour.

### GitHub Pages

Service de GitHub permettant d’héberger gratuitement un site web statique. Il prend le dossier généré par Hugo et le rend accessible via une URL publique (ex : onsbbr.github.io).

### GitHub Actions

Système d’automatisation de GitHub. Dans ce projet, il sert à :

- Reconstruire le site Hugo
- Publier automatiquement les fichiers sur GitHub Pages
- Mettre à jour le site sans intervention manuelle

---

## Référence

**Méthode 1 :**

- Site CV : `https://onsbbr.github.io/gitons.github.io/`
- Nom repo : gitons.github.io
- Lien repo : `https://github.com/onsbbr/gitons.github.io`

**Méthode 2 :**

- Site CV : `https://onsbbr.github.io/gitcv.github.io/`
- Nom repo : gitcv.github.io
- Lien repo : `https://github.com/onsbbr/gitcv.github.io`