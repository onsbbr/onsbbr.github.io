# Guide de Création d'un CV en Ligne avec GitHub Pages

Ce guide vous explique comment créer et déployer votre propre CV en ligne en utilisant GitHub Pages. Deux méthodes sont disponibles selon vos préférences.

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

2. **Initialiser Git dans VSCode**
   - Ouvrez le terminal dans VSCode (Git Bash recommandé)
   - Exécutez les commandes suivantes :
```bash
   git init
   git add .
   git commit -m "Premier commit - CV en ligne"
```

3. **Lier le projet local à GitHub**
   - Copiez les commandes fournies par GitHub après la création du repository
   - Exécutez dans le terminal :
```bash
   git remote add origin git@github.com:votre-nom/votre-nom.github.io.git
   git branch -M main
   git push -u origin main
```

### Résolution des Problèmes (Troubleshooting)

Si vous rencontrez une erreur lors du push, suivez ces étapes pour configurer une clé SSH :

1. **Générer une clé SSH**
```bash
   ssh-keygen -t ed25519 -C "votre-email-github@example.com"
```

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

5. **Ajouter la clé à GitHub**
   - Connectez-vous à GitHub
   - Allez dans `Settings → SSH and GPG keys`
   - Cliquez sur `New SSH key`
   - Collez la clé copiée et cliquez sur `Add SSH key`

6. **Retenter le push**
   - La commande `git push` devrait maintenant fonctionner

### Étape 3 : Activer GitHub Pages

1. Allez dans les paramètres du repository : `Settings → Pages`
2. Sous "Source", sélectionnez `Deploy from a branch`
3. Choisissez la branche `main` et le dossier `/root`
4. Cliquez sur `Save`

Votre CV sera accessible à l'adresse : `https://votre-nom.github.io`

## Méthode 2 : Déploiement Automatique avec GitHub Actions

Cette méthode est moins manuelle et reconstruit automatiquement votre site à chaque modification (push).

**Avantages :**
- Déploiement automatique à chaque push
- Pas besoin de déploiement manuel
- Idéal pour les mises à jour fréquentes

**Configuration :**
- Créez un workflow GitHub Actions dans `.github/workflows/`
- GitHub reconstruira votre site automatiquement à chaque commit

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