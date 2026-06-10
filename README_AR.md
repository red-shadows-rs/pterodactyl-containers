<div align="center">

# حاويات Pterodactyl

صور Docker جاهزة للإنتاج للوحة Pterodactyl

[![الإصدار](https://img.shields.io/badge/version-12.0.0-2563eb?style=flat-square&logo=semver)](CHANGELOG.md)
[![الترخيص](https://img.shields.io/badge/license-MIT-dc2626?style=flat-square)](LICENSE)
![البناء](https://img.shields.io/badge/build-passing-16a34a?style=flat-square&logo=githubactions)
![المعمارية](https://img.shields.io/badge/arch-amd64%20%7C%20arm64-9333ea?style=flat-square&logo=docker)

</div>

---

## 🌐 اللغة

<a href="README.md">🇬🇧 English</a> · <a href="README_AR.md">🇸🇦 العربية</a>

---

## 📋 المحتويات

- [الصور المدعومة](#الصور-المدعومة)
- [بداية سريعة](#بداية-سريعة)
- [هيكل المشروع](#هيكل-المشروع)
- [المساهمة](#المساهمة)
- [الترخيص](#الترخيص)

---

<a id="الصور-المدعومة"></a>
## 🐳 الصور المدعومة

### <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original.svg" width="16" height="16"> جافا

| الإصدار | اسم الصورة |
|---------|-----------|
| 8 | `ghcr.io/red-shadows-rs/pterodactyl-containers/java:v8` |
| 11 | `ghcr.io/red-shadows-rs/pterodactyl-containers/java:v11` |
| 17 | `ghcr.io/red-shadows-rs/pterodactyl-containers/java:v17` |
| 21 | `ghcr.io/red-shadows-rs/pterodactyl-containers/java:v21` |
| 25 | `ghcr.io/red-shadows-rs/pterodactyl-containers/java:v25` |

**المميزات:** OpenJDK · G1GC · ShenandoahGC · String Deduplication

- - -

### <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nodejs/nodejs-original.svg" width="16" height="16"> نود.جے‌اس

| الإصدار | اسم الصورة |
|---------|-----------|
| 18 | `ghcr.io/red-shadows-rs/pterodactyl-containers/nodejs:v18` ⚠️ منتهي |
| 20 | `ghcr.io/red-shadows-rs/pterodactyl-containers/nodejs:v20` |
| 22 | `ghcr.io/red-shadows-rs/pterodactyl-containers/nodejs:v22` |
| 24 | `ghcr.io/red-shadows-rs/pterodactyl-containers/nodejs:v24` |

**المميزات:** Yarn · NPM · pnpm · npx · TypeScript · Corepack

- - -

### <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" width="16" height="16"> بايثون

| الإصدار | اسم الصورة |
|---------|-----------|
| 3.8 | `ghcr.io/red-shadows-rs/pterodactyl-containers/python:v3.8` ⚠️ منتهي |
| 3.9 | `ghcr.io/red-shadows-rs/pterodactyl-containers/python:v3.9` ⚠️ منتهي |
| 3.10 | `ghcr.io/red-shadows-rs/pterodactyl-containers/python:v3.10` |
| 3.11 | `ghcr.io/red-shadows-rs/pterodactyl-containers/python:v3.11` |
| 3.12 | `ghcr.io/red-shadows-rs/pterodactyl-containers/python:v3.12` |
| 3.13 | `ghcr.io/red-shadows-rs/pterodactyl-containers/python:v3.13` |
| 3.14 | `ghcr.io/red-shadows-rs/pterodactyl-containers/python:v3.14` |

**المميزات:** Pip · Virtualenv

---

### 🌐 أُطر العمل

| الإطار | اسم الصورة | المميزات |
|-----------|-----------|----------|
| <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/react/react-original.svg" width="14" height="14"> React | `ghcr.io/red-shadows-rs/pterodactyl-containers/react:latest` | Vite, CRA |
| <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nextjs/nextjs-original.svg" width="14" height="14"> Next.js | `ghcr.io/red-shadows-rs/pterodactyl-containers/nextjs:latest` | SSR, SSG |
| <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/vuejs/vuejs-original.svg" width="14" height="14"> Vue.js | `ghcr.io/red-shadows-rs/pterodactyl-containers/vue:latest` | Vue CLI, Vite |
| <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/angularjs/angularjs-original.svg" width="14" height="14"> Angular | `ghcr.io/red-shadows-rs/pterodactyl-containers/angular:latest` | Angular CLI, SSR |

### 💻 البرمجيات

| البرنامج | اسم الصورة | المنفذ |
|----------|-----------|------|
| <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/vscode/vscode-original.svg" width="14" height="14"> كود-سيرفر | `ghcr.io/red-shadows-rs/pterodactyl-containers/code-server:latest` | 8080 |

> كود-سيرفر يجلب أحدث إصدار تلقائياً من GitHub.

---

<a id="بداية-سريعة"></a>
## 🚀 بداية سريعة

```bash
# سحب وتشغيل نود.جے‌اس 22
docker run -it --rm \
  -e STARTUP="node --version" \
  ghcr.io/red-shadows-rs/pterodactyl-containers/nodejs:v22

# سحب وتشغيل كود-سيرفر
docker run -d --rm \
  -p 8080:8080 \
  -e STARTUP="code-server --bind-addr 0.0.0.0:8080 --auth none ." \
  ghcr.io/red-shadows-rs/pterodactyl-containers/code-server:latest
```

---

<a id="هيكل-المشروع"></a>
## 🏗️ هيكل المشروع

```
.
├── src/
│   ├── languages/     # جافا، نود.جے‌اس، بايثون
│   ├── frameworks/    # رياكت، نكست.جے‌اس، فيو، أنقولار
│   └── softwares/     # كود-سيرفر
├── .github/workflows/ # CI/CD
├── CHANGELOG.md
└── LICENSE
```

---

<a id="المساهمة"></a>
## 🤝 المساهمة

1. انسخ المستودع (Fork)
2. أنشئ فرع ميزة: `git checkout -b feature/my-feature`
3. أضف تغييراتك
4. ارفع إلى الفرع
5. قدم طلب سحب (Pull Request)

---

<a id="الترخيص"></a>
## 📜 الترخيص

موزع تحت [MIT (غير تجاري)](LICENSE).

---

<div align="center">

بُني بواسطة <a href="https://github.com/shadow-x78">SHADOW_x78</a> -
<a href="https://github.com/red-shadows-rs">RED SHADOWS | RS</a> ·
[سجل التغييرات](CHANGELOG.md)

<sub>&copy; 2025 RED SHADOWS | RS</sub>

</div>
