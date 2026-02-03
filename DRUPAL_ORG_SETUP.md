# Guide de Soumission sur Drupal.org

Publier ton module sur drupal.org lui donnera une visibilité maximale auprès de la communauté Drupal et permettra une installation simplifiée via Composer.

## Pourquoi Publier sur Drupal.org ?

- ✅ Visibilité auprès de 1 million+ de sites Drupal
- ✅ Recherche native dans l'interface d'administration Drupal
- ✅ Installation via `composer require drupal/metatag_ai_generate`
- ✅ Statistiques d'utilisation officielles
- ✅ Intégration avec drupal.org (issues, releases, documentation)

## Prérequis

1. **Compte Drupal.org** : Créer un compte sur https://www.drupal.org/user/register
2. **Vérification d'email** : Confirmer ton email
3. **Git Access** : Demander l'accès au système Git de drupal.org

## Étape 1 : Demander l'Accès Git

1. Va sur https://www.drupal.org/node/1011196
2. Lis les instructions complètes
3. Configure ta clé SSH sur drupal.org :
   - Va sur https://www.drupal.org/user/[ton-username]/edit/git
   - Ajoute ta clé SSH publique

## Étape 2 : Créer un Projet Module

1. Va sur https://www.drupal.org/node/add/project-module
2. Remplis le formulaire :

### Project Information

- **Project title** : `Metatag AI Generate`
- **Project name** : `metatag_ai_generate` (machine name)
- **Short description** :
  ```
  AI-powered SEO meta description generator using Anthropic Claude, Mistral AI, OpenRouter, or OpenAI
  ```

### Project Details

- **Project type** : Module
- **Maintenance status** : Actively maintained
- **Development status** : Full version (Drupal 10 and 11 compatible)
- **Categories** :
  - SEO
  - Artificial Intelligence
  - Content

### Description

Copie le contenu de ton README.md (sections principales)

### License

- **License** : GNU General Public License v2.0 or later

### Version Control

- **Import from existing repository** : OUI
- **Repository URL** : `https://github.com/elektrorl/metatag_ai_generate`

3. Clique sur **"Save"**

## Étape 3 : Configurer le Dépôt Git Drupal.org

Une fois le projet créé sur drupal.org, tu recevras l'URL du dépôt Git :

```
git@git.drupal.org:project/metatag_ai_generate.git
```

### Option A : Synchronisation GitHub → Drupal.org

Tu peux garder GitHub comme source principale et pousser vers drupal.org :

```bash
cd /Users/elektrorl/WebDev/Local\ Landos/metatag_ai_generate_release

# Ajouter drupal.org comme remote
git remote add drupal git@git.drupal.org:project/metatag_ai_generate.git

# Pousser vers drupal.org
git push drupal main

# Pousser les tags
git push drupal --tags
```

### Option B : Script de Synchronisation Automatique

Créer un script pour synchroniser automatiquement :

```bash
#!/bin/bash
# sync-to-drupal.sh

git push origin main --tags
git push drupal main --tags
echo "✅ Synchronisé avec GitHub et Drupal.org"
```

## Étape 4 : Créer des Releases Drupal

Sur drupal.org, les versions suivent un format spécifique :

```
[core]-[major].[minor].[patch]
```

Pour Drupal 10 et 11 :
- **1.0.0** → `10.x-1.0` et `11.x-1.0`

Créer les releases sur drupal.org :

1. Va sur ton projet : `https://www.drupal.org/project/metatag_ai_generate`
2. Clique sur **"Add new release"**
3. Remplis :
   - **Version** : `1.0.0` (le système ajoutera automatiquement le préfixe)
   - **Release notes** : Copie les notes de ta release GitHub
   - **Tag** : `1.0.0`

## Étape 5 : Métadonnées du Projet

Configure les métadonnées sur la page du projet :

### Categories

- SEO
- Artificial Intelligence
- Content Management

### Project Images

Upload des screenshots montrant :
1. Le bouton "Generate with AI" dans l'éditeur
2. La configuration du module
3. Un exemple de génération réussie

### Documentation

Créer des pages de documentation :
- Installation guide
- Configuration guide
- Troubleshooting
- FAQ

## Étape 6 : Soumettre pour Review (Optionnel)

Pour obtenir le statut **"Full Project"** (recommandé) :

1. Va sur https://www.drupal.org/node/1587704
2. Demande une review de ton code
3. Un reviewer vérifiera :
   - Conformité aux standards Drupal
   - Sécurité
   - Bonnes pratiques

Une fois approuvé, ton projet sera "promoted" et aura plus de visibilité.

## Installation par les Utilisateurs

Une fois publié sur drupal.org, installation simplifiée :

```bash
composer require drupal/metatag_ai_generate
drush en metatag_ai_generate -y
```

## Workflow de Release Complet

Pour chaque nouvelle version :

```bash
# 1. Créer le tag et la release GitHub
git tag -a v1.1.0 -m "Release v1.1.0"
git push origin v1.1.0
gh release create v1.1.0 --title "v1.1.0" --notes "Release notes..."

# 2. Pousser vers drupal.org
git push drupal main --tags

# 3. Créer la release sur drupal.org
# (via l'interface web)
```

## Statistiques et Suivi

Une fois publié, tu pourras suivre :
- **Downloads** : Nombre d'installations
- **Issues** : Bugs reportés et feature requests
- **Stars** : Utilisateurs qui ont mis le projet en favoris
- **Usage statistics** : Sites utilisant ton module

## Resources

- Documentation officielle : https://www.drupal.org/docs/develop/git/getting-started-with-git
- Project applications : https://www.drupal.org/node/1011698
- Release naming conventions : https://www.drupal.org/node/1015226

---

**Prêt ?** Commence par créer ton compte sur https://www.drupal.org ! 🚀

**Note** : La publication sur drupal.org est un processus manuel qui nécessite une review. Cela peut prendre quelques jours/semaines selon la charge des reviewers.
