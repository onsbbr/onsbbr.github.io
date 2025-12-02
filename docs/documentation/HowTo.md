# Guide pratique

## 1. Introduction

Ce document vous permet de savoir les étapes basiques à suivre qui facilitent la création des projets. 

## 2.  How to

-   How to connect VScode to GitHub ?
-   How to create a CV based on a specific portfolio ?
-   How to create a GitHub pages ?

## 3. Answers
### 1. Connect VScode to GitHub

Afin de connecter votre projet sur VScode à votre compte GitHub, veuillez suivre les étapes suivantes :

Après avoir créer votre projet sur VScode, il ne vous reste que de faire :
- ```git init```
- ```git add .```
- ```git commit -m "votre message"```

![Architecture de séquence](/docs/pictures/terminal1.png "Architecture de séquences")

Après cela, copie le lien de ton projet GitHub :

![Architecture de séquence](/docs/pictures/lien.png "Architecture de séquences")

- Reviens à VScode et tape :
```git remote add origin https://github.com/onsbbr/onsbbr.github.io.git```

- Vérifie que le chemin a bien été pris en charge :
```git remote -v```

![Architecture de séquence](/docs/pictures/terminal2.png "Architecture de séquences")

Ensuite, tape :
- ```git branch -M main```
- ```git push -u origin main```

![Architecture de séquence](/docs/pictures/terminal3.png "Architecture de séquences")

Ensuite, à chaque fois vous ajoutez une chose il suffit de faire :
- ```git add .```
- ```git commit -m "votre message"```
- ```git push```

### 2. Create a CV based on a specific portfolio

First of all, you have to chose a portfolio based on what you're working on.

You can check this [link](https://themes.gohugo.io/) to chose the one you want.

For example, for making a CV i chosed this [theme](https://themes.gohugo.io/themes/aafu/) of portfolio.

Now let's see the steps on how to create your own CV based on the chosen portfolio.

- Download the portfolio chosen

![Architecture de séquence](/docs/pictures/download.png "Architecture de séquences")

- 

### 3. Create a GitHub pages