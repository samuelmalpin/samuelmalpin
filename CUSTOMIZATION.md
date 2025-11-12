# 🎨 Guide de Personnalisation du Profil GitHub

Ce guide vous aidera à personnaliser votre profil GitHub pour le rendre unique et refléter votre personnalité !

## 📝 Sections à Personnaliser

### 1. En-tête Animé
```markdown
<img src="https://readme-typing-svg.herokuapp.com?..." />
```
**Comment personnaliser :**
- Modifiez le texte dans `lines=` en remplaçant `Salut+%F0%9F%91%8B+Je+suis+Samuel+Malpin` par votre nom
- Changez la couleur avec le paramètre `color=` (ex: `color=00FF00` pour vert)
- Ajustez la vitesse avec `duration=` et `pause=`

### 2. À Propos de Moi
Remplacez les sections suivantes avec vos informations :
- ✏️ Votre description personnelle
- 🔭 Sur quoi vous travaillez actuellement
- 🌱 Ce que vous apprenez
- 👯 Type de collaborations recherchées
- ⚡ Un fait amusant vous concernant

### 3. Technologies & Outils

#### Ajouter/Retirer des Badges
Utilisez [shields.io](https://shields.io) pour créer des badges personnalisés.

**Format de base :**
```markdown
![Nom](https://img.shields.io/badge/Nom-Couleur?style=for-the-badge&logo=nom-logo&logoColor=white)
```

**Exemples de technologies populaires :**

**Langages :**
```markdown
![Rust](https://img.shields.io/badge/Rust-000000?style=for-the-badge&logo=rust&logoColor=white)
![Go](https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white)
![PHP](https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white)
![Ruby](https://img.shields.io/badge/Ruby-CC342D?style=for-the-badge&logo=ruby&logoColor=white)
![Swift](https://img.shields.io/badge/Swift-FA7343?style=for-the-badge&logo=swift&logoColor=white)
![Kotlin](https://img.shields.io/badge/Kotlin-0095D5?style=for-the-badge&logo=kotlin&logoColor=white)
```

**Frameworks supplémentaires :**
```markdown
![Vue.js](https://img.shields.io/badge/Vue.js-35495E?style=for-the-badge&logo=vuedotjs&logoColor=4FC08D)
![Angular](https://img.shields.io/badge/Angular-DD0031?style=for-the-badge&logo=angular&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white)
![Laravel](https://img.shields.io/badge/Laravel-FF2D20?style=for-the-badge&logo=laravel&logoColor=white)
![Spring](https://img.shields.io/badge/Spring-6DB33F?style=for-the-badge&logo=spring&logoColor=white)
```

**Outils supplémentaires :**
```markdown
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazon-aws&logoColor=white)
![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=black)
![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=for-the-badge&logo=jenkins&logoColor=white)
```

### 4. Statistiques GitHub

Les statistiques se mettent à jour automatiquement avec votre nom d'utilisateur. Vous pouvez changer le thème :

**Thèmes disponibles :**
- `tokyonight` (actuel)
- `radical`
- `merko`
- `gruvbox`
- `dark`
- `default`
- `highcontrast`
- `dracula`
- `github_dark`
- `monokai`

**Pour changer le thème, remplacez `theme=tokyonight` par votre thème préféré.**

### 5. Liens Sociaux

Mettez à jour vos liens dans la section "Connectons-nous !" :

```markdown
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/votre-profil)
```

**Remplacez :**
- `https://linkedin.com/in/votre-profil` → votre vrai lien LinkedIn
- `https://twitter.com/votre-profil` → votre compte Twitter/X
- `mailto:votre.email@example.com` → votre email
- `https://votre-portfolio.com` → votre site web

**Réseaux supplémentaires à ajouter :**
```markdown
[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://instagram.com/votre-profil)
[![YouTube](https://img.shields.io/badge/YouTube-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://youtube.com/@votre-chaine)
[![Discord](https://img.shields.io/badge/Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/votre-serveur)
[![Stack Overflow](https://img.shields.io/badge/Stack_Overflow-FE7A16?style=for-the-badge&logo=stack-overflow&logoColor=white)](https://stackoverflow.com/users/votre-id)
```

### 6. Animation du Serpent (Snake)

L'animation du serpent nécessite une GitHub Action. Voici comment l'activer :

1. Créez le fichier `.github/workflows/snake.yml` :

```yaml
name: Generate Snake

on:
  schedule:
    - cron: "0 0 * * *"  # Tous les jours à minuit
  workflow_dispatch:

jobs:
  generate:
    runs-on: ubuntu-latest
    timeout-minutes: 10
    
    steps:
      - name: Generate github-contribution-grid-snake.svg
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          
      - name: Push github-contribution-grid-snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

2. Allez dans Settings → Actions → General et activez les workflows
3. Exécutez manuellement le workflow une fois dans l'onglet Actions
4. L'animation sera générée et apparaîtra sur votre profil !

## 🎨 Personnalisations Avancées

### Ajouter une Bannière Personnalisée

Remplacez l'en-tête animé par une image personnalisée :
```markdown
<div align="center">
  <img src="URL_DE_VOTRE_BANNIERE" alt="Bannière" width="100%"/>
</div>
```

**Outils pour créer des bannières :**
- [Canva](https://www.canva.com)
- [Banner.io](https://banner.io)
- [Photopea](https://www.photopea.com)

### Ajouter des Cartes de Projets

```markdown
[![Nom du Projet](https://github-readme-stats.vercel.app/api/pin/?username=samuelmalpin&repo=nom-du-repo&theme=tokyonight)](https://github.com/samuelmalpin/nom-du-repo)
```

### Ajouter un Blog ou Articles

```markdown
## 📝 Derniers Articles

<!-- BLOG-POST-LIST:START -->
<!-- BLOG-POST-LIST:END -->
```

Pour automatiser, utilisez [blog-post-workflow](https://github.com/gautamkrishnar/blog-post-workflow)

### Compteur de Visiteurs Personnalisé

Changez le style du compteur :
```markdown
<!-- Style flat -->
[![Profile Views](https://komarev.com/ghpvc/?username=samuelmalpin&style=flat)](https://github.com/samuelmalpin)

<!-- Style flat-square avec couleur personnalisée -->
[![Profile Views](https://komarev.com/ghpvc/?username=samuelmalpin&color=blue&style=flat-square)](https://github.com/samuelmalpin)

<!-- Style plastic -->
[![Profile Views](https://komarev.com/ghpvc/?username=samuelmalpin&style=plastic)](https://github.com/samuelmalpin)
```

## 🔧 Dépannage

### Les badges ne s'affichent pas
- Vérifiez que l'URL est correcte
- Assurez-vous que le nom du logo est correct (consultez [simpleicons.org](https://simpleicons.org))

### Les statistiques GitHub ne se chargent pas
- Cela peut prendre quelques minutes après la première visite
- Vérifiez que votre nom d'utilisateur est correct dans toutes les URLs

### L'animation du serpent ne fonctionne pas
- Vérifiez que le workflow est activé dans les paramètres
- Assurez-vous que le workflow s'est exécuté au moins une fois
- Vérifiez qu'il y a une branche `output` dans votre repo

## 📚 Ressources Utiles

- [Awesome GitHub Profile README](https://github.com/abhisheknaiidu/awesome-github-profile-readme)
- [GitHub README Stats](https://github.com/anuraghazra/github-readme-stats)
- [Shields.io](https://shields.io)
- [Simple Icons](https://simpleicons.org)
- [Emoji Cheat Sheet](https://github.com/ikatyang/emoji-cheat-sheet)

## 💡 Conseils

1. **Gardez-le à jour** : Mettez régulièrement à jour vos compétences et projets
2. **Soyez authentique** : Montrez votre vraie personnalité
3. **Moins c'est plus** : N'en faites pas trop, gardez-le lisible
4. **Testez** : Prévisualisez vos changements avant de commiter
5. **Inspirez-vous** : Regardez d'autres profils pour des idées

---

**Bon codage ! 🚀**
