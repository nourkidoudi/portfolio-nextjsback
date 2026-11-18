# portfolio-nextjs

> Portfolio de **nour kidoudi** — généré automatiquement via [Backstage](https://backstage.io).

## 🚀 Stack technique

| Couche | Technologie |
|--------|------------|
| Frontend | Next.js 16 (App Router) + Tailwind CSS |
| Conteneurisation | Docker (multi-stage build) |
| CI/CD | GitHub Actions |
| Registry | Docker Hub (`nourki2003/portfolio-nextjs`) |
| Orchestration | docker-compose |

## 📦 Démarrage rapide

### Développement local

```bash
npm install
npm run dev
```

Ouvrir [http://localhost:3000](http://localhost:3000).

### Avec Docker

```bash
docker compose up -d
```

L'application est accessible sur [http://localhost:3000](http://localhost:3000).

## 🔄 Pipeline CI/CD

Le pipeline GitHub Actions (`build-publish-deploy`) s'exécute automatiquement à chaque `push` sur `main` :

1. **Build** — Construction de l'image Docker multi-stage
2. **Push** — Publication vers Docker Hub avec tag versionné + `latest`
3. **Deploy** — Déploiement local via `docker compose` (self-hosted runner)

Vous pouvez aussi déclencher le pipeline manuellement avec un numéro de version personnalisé via `workflow_dispatch`.

## 📂 Structure du projet

```
├── app/
│   ├── page.tsx          # Page principale du portfolio
│   ├── layout.tsx         # Layout racine
│   └── globals.css        # Styles globaux (Tailwind)
├── public/                # Assets statiques
├── Dockerfile             # Build multi-stage optimisé
├── docker-compose.yml     # Déploiement local
├── .github/workflows/
│   └── ci.yml             # Pipeline CI/CD
├── catalog-info.yaml      # Métadonnées Backstage
└── package.json
```

## 🏗 Généré par Backstage

Ce projet a été créé via le template **portfolio-nextjs-template** dans Backstage, qui automatise :

- La génération du code Next.js
- La création du dépôt GitHub
- La configuration Docker (Dockerfile, .dockerignore, docker-compose.yml)
- Le pipeline CI/CD (GitHub Actions)
- L'enregistrement dans le catalogue Backstage
