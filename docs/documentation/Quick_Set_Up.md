# Commandes pour la méthode 1

**Sur VSCode**

```bash
   git init
   git add .
   git commit -m "Mon premier commit"
```
**Sur GitHub**

`New → votre-nom.github.io → Create repository`

**Sur VSCode**

```bash
   git remote add origin git@github.com:votre-nom/votre-nom.github.io.git
   git branch -M main
   git push -u origin main
```

**Sur GitHub**

`Settings → Pages → Source : Deploy from a branch → main → Save`

**Dans un navigateur**

Accèdez à `https://votre-nom.github.io`

## Remarques

- Veuillez modifier le nom du repository par le votre.
- Veuillez changer le contenu du fichier `index.html`, qui se trouve sous la racine, par les données de votre propre CV.
- Accédez à votre CV en local sur http://localhost:1313

# Commandes pour la méthode 2

**Sur VSCode**

```bash
git submodule add https://github.com/darshanbaral/aafu.git themes/aafu
```

*à remplir*

**Sur VSCode**

```bash
   git init
   git add .
   git commit -m "Mon premier commit"
```
**Sur GitHub**

`New → Repo name : votre-nom.github.io → Create repository`

**Sur VSCode**

```bash
   git remote add origin git@github.com:votre-nom/votre-nom.github.io.git
   git branch -M main
   git push -u origin main
```

**Sur GitHub**

`Settings → Pages → Source : GitHub Actions → browse all workflows → Hugo → Configure → Save → Commit Changes`

**Dans un navigateur**

Accèdez à `https://votre-nom.github.io`

## Remarques

- Veuillez modifier le nom du repository par le votre.
- Veuillez changer le contenu du fichier `index.html`, qui se trouve sous la racine, par les données de votre propre CV.