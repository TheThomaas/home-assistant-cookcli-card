# CookCLI Card pour Home Assistant

Carte Lovelace personnalisée pour Home Assistant qui affiche la **liste de toutes vos recettes** exposées par l'intégration [ha-cookcli](https://git.thethomaas.net/TheThomaas/ha-cookcli), et permet de **naviguer vers la page de détail** de chaque recette générée par la stratégie [ha-cookcli-strategy](https://git.thethomaas.net/TheThomaas/ha-cookcli-strategy).

## ✨ Fonctionnalités

- 📋 **Liste toutes vos recettes** de cuisine dans une carte unique
- 🧭 **Navigation** vers la page de détail d'une recette au clic
- 🎨 **Carte Lovelace personnalisée** (`custom:cookcli-card`) intégrable dans n'importe quel tableau de bord
- 🔌 Fonctionne avec les données exposées par l'intégration [ha-cookcli](https://git.thethomaas.net/TheThomaas/ha-cookcli)

## 🧩 Architecture

Cette carte fait partie d'un ensemble de trois composants qui fonctionnent ensemble :

| Composant | Rôle | Dépôt |
|---|---|---|
| **Intégration** | Se connecte au serveur CookCLI et expose les recettes à Home Assistant | [ha-cookcli](https://git.thethomaas.net/TheThomaas/ha-cookcli) |
| **Stratégie de tableau de bord** | Crée automatiquement une page par recette (ingrédients + étapes) | [ha-cookcli-strategy](https://git.thethomaas.net/TheThomaas/ha-cookcli-strategy) |
| **Carte personnalisée** | Liste toutes les recettes et permet de naviguer vers le détail d'une recette | *ce dépôt* |

## 📦 Installation

### Prérequis

- Une instance **Home Assistant** fonctionnelle (version récente recommandée)
- L'intégration **[ha-cookcli](https://git.thethomaas.net/TheThomaas/ha-cookcli)** installée et configurée
- La stratégie **[ha-cookcli-strategy](https://git.thethomaas.net/TheThomaas/ha-cookcli-strategy)** installée (pour les pages de détail)
- **[HACS](https://hacs.xyz/)** installé (recommandé)

### Installation via HACS

1. Ouvrez **HACS** dans Home Assistant.
2. Allez dans **Tableaux de bord** → menu (⋮) → **Dépôts personnalisés**.
3. Ajoutez l'URL du dépôt :
   ```
   https://git.thethomaas.net/TheThomaas/ha-cookcli-card
   ```
   Catégorie : **Dashboard** (ou **Lovelace**)
4. Recherchez **CookCLI Card** dans HACS et installez-le.
5. **Videz le cache du navigateur** ou rechargez les ressources Lovelace.

### Installation manuelle

1. Téléchargez ou clonez ce dépôt.
2. Copiez le fichier `dist/cookcli-card.js` dans votre répertoire `config/www/`.
3. Ajoutez la ressource dans **Paramètres** → **Tableaux de bord** → **Ressources** :
   ```yaml
   url: /local/cookcli-card.js
   type: module
   ```
4. Rechargez les ressources Lovelace.

## ⚙️ Configuration

### Ajout de la carte

Ajoutez la carte `cookcli-card` à n'importe quel tableau de bord. Exemple minimal en YAML :

```yaml
type: custom:cookcli-card
```

### Exemple avec titre

```yaml
type: custom:cookcli-card
title: Mes recettes
```

> Consultez le fichier `dist/cookcli-card.js` pour la liste complète des options supportées (filtres, tri, titre, etc.).

### Via l'éditeur visuel

1. Ouvrez un tableau de bord en mode édition.
2. Cliquez sur **+ Ajouter une carte**.
3. Recherchez **CookCLI Card**.
4. Configurez les options puis validez.

## 🚀 Utilisation

1. La carte affiche la **liste de toutes vos recettes** récupérées depuis l'intégration.
2. **Cliquez sur une recette** pour être redirigé vers sa **page de détail** (générée par la stratégie).
3. La page de détail affiche les **ingrédients** et les **étapes** de préparation.

## 📄 Licence

Ce projet est distribué sous licence présente dans le fichier [LICENSE](./LICENSE) du dépôt.

## 🔗 Liens

- **Intégration** : https://git.thethomaas.net/TheThomaas/ha-cookcli
- **Stratégie** : https://git.thethomaas.net/TheThomaas/ha-cookcli-strategy
- **Carte** : https://git.thethomaas.net/TheThomaas/ha-cookcli-card
- **CookCLI** : https://github.com/cooklang/CookCLI
- **Cooklang** : https://cooklang.org/
