# Guide de contribution — Groupe 6

Ce guide explique comment **chaque membre** configure son ordinateur et
comment on travaille ensemble sur ce dépôt sans écraser le travail des autres.
Comptez environ 5 minutes la première fois.

> ⚠️ Ce dépôt est **public**. N'y mettez jamais de mot de passe, de jeton
> (token), de clé d'API, ni vos coordonnées personnelles (téléphone, e-mail
> privé…).

---

## 1. Installer Git

| Système | Commande / lien |
|---|---|
| Windows | Télécharger et installer [Git for Windows](https://git-scm.com/download/win) (options par défaut) |
| macOS | `xcode-select --install` dans le Terminal |
| Ubuntu / Debian | `sudo apt install git` |

Vérifier : `git --version`

## 2. Se connecter à GitHub (chacun avec SON compte)

**Option recommandée — GitHub CLI :**

1. Installer [GitHub CLI](https://cli.github.com/) (`sudo apt install gh` sous Ubuntu).
2. Lancer :
   ```bash
   gh auth login
   ```
   Choisir `GitHub.com` → `HTTPS` → `Login with a web browser`, puis valider
   dans le navigateur avec votre propre compte.

Sous Windows, Git for Windows ouvre aussi automatiquement une fenêtre de
connexion GitHub au premier `git push` : c'est suffisant.

> Ne partagez jamais votre mot de passe ou votre jeton avec un autre membre,
> même pour « dépanner ».

## 3. Régler votre nom et votre e-mail Git

Git signe chaque commit avec un nom et un e-mail. Comme le dépôt est public,
utilisez l'**adresse anonyme fournie par GitHub** plutôt que votre vrai e-mail.

1. Sur GitHub : **Settings → Emails**.
2. Cochez **« Keep my email addresses private »**.
3. Copiez l'adresse affichée, de la forme :
   `12345678+votre-pseudo@users.noreply.github.com`
4. Dans un terminal :
   ```bash
   git config --global user.name "votre-pseudo-github"
   git config --global user.email "12345678+votre-pseudo@users.noreply.github.com"
   ```
5. Vérifier :
   ```bash
   git config --global user.name
   git config --global user.email
   ```

## 4. Récupérer le dépôt

```bash
git clone https://github.com/marcedoun-byte/D-p-t-de-groupe-6.git
cd D-p-t-de-groupe-6
```

---

## 5. Comment on travaille ensemble

**Règle d'or : on ne pousse jamais directement sur `main`.** Chacun travaille
sur sa propre branche, puis propose ses changements via une *pull request*
(PR) qu'un autre membre relit.

### À chaque nouvelle tâche

```bash
# 1. Partir de la dernière version de main
git switch main
git pull

# 2. Créer une branche pour la tâche : prenom/ce-que-je-fais
git switch -c prenom/page-accueil

# 3. Travailler, puis enregistrer
git add .
git commit -m "Ajoute la page d'accueil"

# 4. Envoyer la branche sur GitHub
git push -u origin prenom/page-accueil
```

5. Sur GitHub, cliquer sur **« Compare & pull request »**, décrire ce qui a
   été fait, puis demander une relecture à un autre membre.
6. Une fois la PR approuvée, on la fusionne (**Merge**) et on supprime la branche.

### Bonnes habitudes

- **`git pull` sur `main` avant de commencer** : on part toujours du travail le plus récent.
- **Petits commits, messages clairs** : « Corrige le calcul de la moyenne » plutôt que « modif ».
- **Une branche = une tâche** : plus facile à relire et à annuler si besoin.
- **Conflit ?** Pas de panique : prévenez le groupe, on le règle ensemble
  plutôt que d'écraser le travail de quelqu'un.
- Avant de pousser, vérifiez avec `git status` qu'aucun fichier privé
  (mot de passe, `.env`, fichier personnel) n'est inclus.

---

## 6. Pour l'administrateur du dépôt

Pour que la règle « pas de push direct sur `main` » soit appliquée
automatiquement : **Settings → Branches → Add branch protection rule**,
motif `main`, cocher **« Require a pull request before merging »**
(et éventuellement **« Require approvals »** = 1).

## Membres

| Pseudo GitHub | Rôle |
|---|---|
| [@marcedoun-byte](https://github.com/marcedoun-byte) | administrateur |
| [@ADKfull-dev](https://github.com/ADKfull-dev) | membre |
| [@Reine-hub3](https://github.com/Reine-hub3) | membre |
