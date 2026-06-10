<div align="center">

# Pterodactyl Containers

Production-ready Docker images for the Pterodactyl Panel

[![Version](https://img.shields.io/badge/version-12.0.0-2563eb?style=flat-square&logo=semver)](CHANGELOG.md)
[![License](https://img.shields.io/badge/license-MIT-dc2626?style=flat-square)](LICENSE)
![Build](https://img.shields.io/badge/build-passing-16a34a?style=flat-square&logo=githubactions)
![Arch](https://img.shields.io/badge/arch-amd64%20%7C%20arm64-9333ea?style=flat-square&logo=docker)

</div>

---

## 🌐 Language

<a href="README.md">🇬🇧 English</a> · <a href="README_AR.md">🇸🇦 العربية</a>

---

## 📋 Table of Contents

- [Supported Images](#supported-images)
- [Quick Start](#quick-start)
- [Project Structure](#project-structure)
- [Contributing](#contributing)
- [License](#license)

---

## 🐳 Supported Images

### <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original.svg" width="16" height="16"> Java

| Version | Image |
|---------|-------|
| 8 | `ghcr.io/red-shadows-rs/pterodactyl-containers/java:v8` |
| 11 | `ghcr.io/red-shadows-rs/pterodactyl-containers/java:v11` |
| 17 | `ghcr.io/red-shadows-rs/pterodactyl-containers/java:v17` |
| 21 | `ghcr.io/red-shadows-rs/pterodactyl-containers/java:v21` |
| 25 | `ghcr.io/red-shadows-rs/pterodactyl-containers/java:v25` |

**Features:** OpenJDK · G1GC · ShenandoahGC (v17+) · String Deduplication

---

### <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nodejs/nodejs-original.svg" width="16" height="16"> Node.js

| Version | Image |
|---------|-------|
| 18 | `ghcr.io/red-shadows-rs/pterodactyl-containers/nodejs:v18` ⚠️ EOL |
| 20 | `ghcr.io/red-shadows-rs/pterodactyl-containers/nodejs:v20` |
| 22 | `ghcr.io/red-shadows-rs/pterodactyl-containers/nodejs:v22` |
| 24 | `ghcr.io/red-shadows-rs/pterodactyl-containers/nodejs:v24` |

**Features:** Yarn · NPM · TypeScript · Corepack

---

### <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" width="16" height="16"> Python

| Version | Image |
|---------|-------|
| 3.8 | `ghcr.io/red-shadows-rs/pterodactyl-containers/python:v3.8` ⚠️ EOL |
| 3.9 | `ghcr.io/red-shadows-rs/pterodactyl-containers/python:v3.9` ⚠️ EOL |
| 3.10 | `ghcr.io/red-shadows-rs/pterodactyl-containers/python:v3.10` |
| 3.11 | `ghcr.io/red-shadows-rs/pterodactyl-containers/python:v3.11` |
| 3.12 | `ghcr.io/red-shadows-rs/pterodactyl-containers/python:v3.12` |
| 3.13 | `ghcr.io/red-shadows-rs/pterodactyl-containers/python:v3.13` |
| 3.14 | `ghcr.io/red-shadows-rs/pterodactyl-containers/python:v3.14` |

**Features:** Pip · Virtualenv

---

### 🌐 Web Frameworks

| Framework | Image | Features |
|-----------|-------|----------|
| <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/react/react-original.svg" width="14" height="14"> React | `ghcr.io/red-shadows-rs/pterodactyl-containers/react:latest` | Vite, CRA |
| <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nextjs/nextjs-original.svg" width="14" height="14"> Next.js | `ghcr.io/red-shadows-rs/pterodactyl-containers/nextjs:latest` | SSR, SSG |
| <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/vuejs/vuejs-original.svg" width="14" height="14"> Vue.js | `ghcr.io/red-shadows-rs/pterodactyl-containers/vue:latest` | Vue CLI, Vite |
| <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/angularjs/angularjs-original.svg" width="14" height="14"> Angular | `ghcr.io/red-shadows-rs/pterodactyl-containers/angular:latest` | Angular CLI, SSR |

### 💻 Softwares

| Software | Image | Port |
|----------|-------|------|
| <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/vscode/vscode-original.svg" width="14" height="14"> code-server | `ghcr.io/red-shadows-rs/pterodactyl-containers/code-server:latest` | 8080 |

> code-server automatically fetches the latest version from GitHub.

---

## 🚀 Quick Start

```bash
# Pull and run a Node.js 22 container
docker run -it --rm \
  -e STARTUP="node --version" \
  ghcr.io/red-shadows-rs/pterodactyl-containers/nodejs:v22

# Pull and run code-server
docker run -d --rm \
  -p 8080:8080 \
  -e STARTUP="code-server --bind-addr 0.0.0.0:8080 --auth none ." \
  ghcr.io/red-shadows-rs/pterodactyl-containers/code-server:latest
```

---

## 🏗️ Project Structure

```
.
├── src/
│   ├── languages/     # Java, Node.js, Python
│   ├── frameworks/    # React, Next.js, Vue, Angular
│   └── softwares/     # code-server
├── .github/workflows/ # CI/CD pipeline
├── CHANGELOG.md
└── LICENSE
```

---

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/my-feature`
3. Commit your changes
4. Push to the branch
5. Submit a Pull Request

---

## 📜 License

Distributed under the [MIT License (Non-Commercial)](LICENSE).

---

<div align="center">

Built by [RED SHADOWS | RS](https://github.com/red-shadows-rs) ·
[Changelog](CHANGELOG.md)

<sub>&copy; 2025 RED SHADOWS | RS</sub>

</div>
