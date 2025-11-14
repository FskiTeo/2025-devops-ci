# 2025-devops-ci

## Description

Ce projet est une application Todo développée avec React, TypeScript et Vite. Il utilise Drizzle pour la gestion de la base de données, Tailwind CSS pour le styling, et est entièrement containerisé avec Docker pour faciliter le développement et le déploiement.

## Prérequis

- Docker
- Docker Compose

## Installation

1. Clonez le repository :
   ```bash
   git clone https://github.com/FskiTeo/2025-devops-ci.git
   cd 2025-devops-ci
   ```

2. Copiez le fichier d'exemple des variables d'environnement :
   ```bash
   cp .env.example .env
   ```

3. Lancez les services avec Docker Compose :
   ```bash
   docker compose up -d
   ```

**Note :** Ne lancez pas le projet avec `pnpm` sur votre machine hôte. Tout doit être exécuté dans les containers Docker.

## Utilisation

Une fois les containers démarrés, l'application sera accessible sur `http://localhost:3000` (ou le port configuré dans votre `.env`).

## Développement

Pour effectuer des tâches de développement telles que lancer les tests, le linting ou le build, connectez-vous au container de l'application :

```bash
docker compose exec -it app bash
```

À l'intérieur du container, vous pouvez utiliser les commandes suivantes :

- **Tests unitaires :**
  ```bash
  pnpm test
  ```

- **Tests end-to-end :**
  ```bash
  pnpm playwright test
  ```

- **Linting :**
  ```bash
  pnpm lint
  ```

- **Build :**
  ```bash
  pnpm build
  ```

- **Migrations de base de données :**
  ```bash
  pnpm drizzle-kit generate
  pnpm drizzle-kit push
  ```

## Structure du projet

- `src/` : Code source de l'application
- `e2e/` : Tests end-to-end avec Playwright
- `drizzle/` : Migrations de base de données
- `public/` : Assets statiques
- `Dockerfile` : Configuration Docker pour l'application
- `Migrator.dockerfile` : Configuration Docker pour les migrations
- `docker-compose.yml` : Configuration des services

## Technologies utilisées

- React
- TypeScript
- Vite
- Drizzle ORM
- Tailwind CSS
- Playwright
- Vitest
- ESLint
