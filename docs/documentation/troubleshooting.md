# ⚠️ Troubleshooting 1 : Résolution des Problèmes de push

Si vous rencontrez une erreur lors du push, comme celle ci :

![Architecture de séquence](/docs/pictures/gitpushTSH.png "Architecture de séquences")

Veuillez suivre ces étapes pour configurer une clé SSH :

1. **Générer une clé SSH**
```bash
   ssh-keygen -t ed25519 -C "votre-email-github@example.com"
```
![Architecture de séquence](/docs/pictures/sshkeygen.png "Architecture de séquences")

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
![Architecture de séquence](/docs/pictures/addkey.png "Architecture de séquences")

5. **Ajouter la clé à GitHub**
   - Connectez-vous à GitHub
   - Allez dans `Settings → SSH and GPG keys`
   - Cliquez sur `New SSH key`
   - Collez la clé copiée et cliquez sur `Add SSH key`

![Architecture de séquence](/docs/pictures/newSSHkey.png "Architecture de séquences")
![Architecture de séquence](/docs/pictures/sshKEYcreated.png "Architecture de séquences")


6. **Retenter le push**

   - La commande `git push` devrait maintenant fonctionner

![Architecture de séquence](/docs/pictures/gitpushaftersshkey.png "Architecture de séquences")