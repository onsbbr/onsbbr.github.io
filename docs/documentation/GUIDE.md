# Guide pratique

## 1. Introduction

Ce guide présente les étapes essentielles pour démarrer rapidement vos projets, les connecter à GitHub, créer un CV basé sur un portfolio Hugo, et publier votre site en ligne grâce à GitHub Pages.

## 2.  Comment faire

-   Comment connecter VS Code à GitHub ?
-   Comment créer un CV à partir d'un portfolio spécifique ?
-   Comment créer des pages GitHub ?
-   Comment installer et configurer un thème spécifique ?

## 3. Réponses

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

### 2. Créez un CV basé sur un portfolio spécifique

Pour créer un CV avec un thème Hugo, il faut d'abord choisir un portfolio adapté.

Rendez-vous sur [la galerie officielle](https://themes.gohugo.io/), ensuite choisissez un thème.
Exemple utilisé dans ce guide [le thème Aafu](https://themes.gohugo.io/themes/aafu/).

![Architecture de séquence](/docs/pictures/download.png "Architecture de séquences")

#### Étapes de création du CV à partir du thème Aafu

Pour utiliser **aafu** comme thème dans votre propre projet Hugo :

1. Ajouter le thème :

```bash
git submodule add https://github.com/darshanbaral/aafu.git themes/aafu
```

2. Copiez les fichiers/dossiers suivants depuis ```aafu/``` vers la racine de votre projet :

**Fichiers :**

- config.yaml
- package.json
- tailwind.config.js

**Dossiers :**

- assets/
- static/

3. Activez le thème en le configurant dans le fichier ```config.yaml``` :
```bash
theme: aafu
```

4. Modifiez le fichier ```layouts/index.html``` pour personnaliser vos informations personnelles (nom, expériences, compétences, etc.).

5. Installez les dépendances et démarrez le serveur de développement :

```bash
npm install
hugo server
```
6. Accédez à votre CV sur http://localhost:1313

### 3. Créer des pages GitHub

Une fois votre CV créé, vous pouvez le publier en ligne facilement grâce à GitHub Pages.

1. Assurez-vous que votre dépôt se nomme : ```votre-nom.github.io```
2. Poussez votre projet Hugo sur GitHub.
3. Ajoutez un workflow GitHub Actions pour générer votre site, pour cela créer le fichier ```.github/workflows/deploy.yml``` avec le contenu proposé par **Hugo**.
4. GitHub générera automatiquement votre site.
5. Votre CV sera accessible en ligne à l’adresse : ```https://votre-nom.github.io/```

### 4. Installer et configurer un thème spécifique

Pour installer un thème spécifique il faut tout d'abord choisir ce thème. Pour cela, veuillez visiter `https://themes.gohugo.io/` pour explorer les thèmes disponibles.

Dans notre cas, on va utilisé le thème `aafu`.

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
theme : aafu
```

4. Installez les dépendances et démarrez le serveur de développement :
```bash
npm install
hugo server
```

5. Personnalisez le thème en modifiant le fichier `config.yaml`
6. Remplacez `profile.jpg` dans `static/images` par votre propre image de profil