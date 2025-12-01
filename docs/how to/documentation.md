# Documentation

## 1. Introduction

Ce document vous permet de savoir les étapes basiques à suivre qui facilitent la création des projets. 

## 2.  How to

-   How to connect VScode to GitHub
-   ...
-   ...

## 3. Guide
### 1. Connect VScode to GitHub

Afin de connecter votre projet sur VScode à votre compte GitHub, veuillez suivre les étapes suivantes :

Après avoir créer votre projet sur VScode, il ne vous reste que de faire :
- git init
- git add .
- git commit -m "votre message"

Après cela, copie le lien de ton projet GitHub :

![Architecture de séquence](/docs/pictures/lien.png "Architecture de séquences")

- Reviens à VScode et tape :
git remote add origin https://github.com/onsbbr/onsbbr.github.io.git

- Vérifie que le chemin a bien été pris en charge :
git remote -v

Ensuite, tape :
- git branch -M main
- git push -u origin main
