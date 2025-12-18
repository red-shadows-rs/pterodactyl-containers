# Pterodactyl Containers 🔨

![Pterodactyl](https://img.shields.io/badge/Pterodactyl-0e4688?style=for-the-badge&logo=pterodactyl&logoColor=white)
[![Changelog](https://img.shields.io/badge/Changelog-v1.2-blue?style=for-the-badge)](CHANGELOG.md)
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)

## ✨ Features

- 🏗️ **Multi-arch builds**: AMD64 & ARM64
- 🤖 **CI/CD**: Automated GitHub Actions pipeline
- 🛡️ **Security**: Minimal, secure base images
- 🚀 **Production ready**: Optimized for Pterodactyl
- ⚡ **Fast**: Efficient caching

## 🐳 Supported Containers

### <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original.svg" alt="Java" width="20" height="20"/> Java

- **Versions:** 8, 11, 17, 21, 25
- **Base:** Eclipse Temurin (Ubuntu Jammy)

### <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nodejs/nodejs-original.svg" alt="Node.js" width="20" height="20"/> Node.js

- **Versions:** 18, 20, 22, 24
- **Base:** Official Node.js (Debian Bullseye Slim)

### <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="Python" width="20" height="20"/> Python

- **Versions:** 3.8, 3.9, 3.10, 3.11, 3.12, 3.13, 3.14
- **Base:** Python Slim (Debian)

## 🌐 Web Frameworks

### <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/react/react-original.svg" alt="React" width="20" height="20"/> React
- **Base:** Node.js 22
- **Features:** CRA, Vite, Custom Builds
- **Startup:** `npm start` (or custom)

### <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nextjs/nextjs-original.svg" alt="Next.js" width="20" height="20"/> Next.js
- **Base:** Node.js 22
- **Features:** SSR, ISR, Static Export
- **Startup:** `npm run start` (or `npm run dev`)

### <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/vuejs/vuejs-original.svg" alt="Vue.js" width="20" height="20"/> Vue.js
- **Base:** Node.js 22
- **Features:** Vue CLI, Vite
- **Startup:** `npm run serve` (or custom)

### <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/angularjs/angularjs-original.svg" alt="Angular" width="20" height="20"/> Angular
- **Base:** Node.js 22
- **Features:** Angular CLI
- **Startup:** `npm start` (ensure host is 0.0.0.0)

## 🚀 Usage

> **Authentication Required:**
> To push images to GitHub Container Registry (GHCR), you must create a **Classic Personal Access Token (classic PAT)** with the following scopes:
>
> - `write:packages`
> - `read:packages`
> - `delete:packages`
>
> After creating the token, add it to your repository secrets as **GHCR_TOKEN** under:
>
> `GitHub Repository → Settings → Secrets and variables → Actions`
>
> This token will be used for authentication during the image push process in GitHub Actions.

### 🐳 Pull from GitHub Container Registry

```bash
# Java 25
docker pull ghcr.io/red-shadows-rs/pterodactyl-containers/java:v25

# Node.js 24
docker pull ghcr.io/red-shadows-rs/pterodactyl-containers/nodejs:v24

# Python 3.14
docker pull ghcr.io/red-shadows-rs/pterodactyl-containers/python:v3.14

# React
docker pull ghcr.io/red-shadows-rs/pterodactyl-containers/react:latest

# Next.js
docker pull ghcr.io/red-shadows-rs/pterodactyl-containers/nextjs:latest

# Vue.js
docker pull ghcr.io/red-shadows-rs/pterodactyl-containers/vue:latest

# Angular
docker pull ghcr.io/red-shadows-rs/pterodactyl-containers/angular:latest
```

> Change the tag/version as needed.

### 🔨 Build locally

```bash
# Java 25
docker build -f src/languages/java/v25/Dockerfile -t ghcr.io/red-shadows-rs/pterodactyl-containers/java:v25 src/languages/java/

# Node.js 24
docker build -f src/languages/nodejs/v24/Dockerfile -t ghcr.io/red-shadows-rs/pterodactyl-containers/nodejs:v24 src/languages/nodejs/

# Python 3.14
docker build -f src/languages/python/v3.14/Dockerfile -t ghcr.io/red-shadows-rs/pterodactyl-containers/python:v3.14 src/languages/python/

# React
docker build -f src/frameworks/react/Dockerfile -t ghcr.io/red-shadows-rs/pterodactyl-containers/react:latest src/frameworks/react/

# Next.js
docker build -f src/frameworks/nextjs/Dockerfile -t ghcr.io/red-shadows-rs/pterodactyl-containers/nextjs:latest src/frameworks/nextjs/

# Vue.js
docker build -f src/frameworks/vue/Dockerfile -t ghcr.io/red-shadows-rs/pterodactyl-containers/vue:latest src/frameworks/vue/

# Angular
docker build -f src/frameworks/angular/Dockerfile -t ghcr.io/red-shadows-rs/pterodactyl-containers/angular:latest src/frameworks/angular/
```

### ⚙️ Environment Variables

| Variable  | Description                | Default | Required |
|-----------|----------------------------|---------|----------|
| `STARTUP` | Startup Command            | -       | ✅       |

### 📁 Volume

- `/home/container` — App files & data


### 🥚 Pterodactyl Eggs

Find official Eggs and setup guides here:

[![Pterodactyl Eggs](https://img.shields.io/badge/Pterodactyl%20Eggs-Repository-blue?logo=github)](https://github.com/red-shadows-rs/pterodactyl-eggs/blob/main/README.md)

## 🤖 GitHub Actions

- Builds all images on push to `main` or release
- Multi-platform (AMD64/ARM64)
- Uses build cache for speed

## 🤝 Contributing

1. Fork & branch
2. Make changes
3. Test locally
4. Pull request

## 📜 License

MIT — see [LICENSE](LICENSE)

---

<span style="font-weight:bold;vertical-align:middle;">&#169; 2025 Copyright</span>
**RED SHADOWS | RS** - <span style="font-weight:bold;vertical-align:middle;">All rights reserved</span>
