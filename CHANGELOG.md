# Changelog

All notable changes to this project will be documented in this file.

## [v1.2.0] - 2025-12-18

### 🚀 Added
- **Languages:** Added support for **Java 25**, **Node.js 24**, **Python 3.8**, **Python 3.13**, and **Python 3.14**
- **Web Frameworks:** Added dedicated containers for **React**, **Next.js**, **Vue.js**, and **Angular**
  - Optimized for dev/prod environments
  - Based on Node.js 22 for maximum compatibility
  - Support for Vite, CRA, Vue CLI, and Angular CLI

### 🔄 Updated
- **Documentation:** Complete overhaul to match `pterodactyl-eggs` repository style
  - Added Changelog badge linking to this file
  - Added Web Frameworks section  - Standardized version listings
  - Updated usage examples with new versions and frameworks
- **Dockerfiles:** Changed author from "Shadow-x78" to "RED SHADOWS | RS" across all containers

### 🗑️ Removed
- **Copyright Headers:** Removed `<!-- © Copyright RED SHADOWS | RS -->` from all source files to clean up codebase
- **Timezone:** Removed Timezone (tzdata) dependencies and TZ environment variables from all Dockerfiles and entrypoints

## [v1.1.0] - 2025-12-18

### 🔄 Changed
- Removed copyright headers from all source files to clean up codebase
- Removed Timezone (tzdata) dependencies and TZ environment variables from all Dockerfiles and entrypoints
- Refactored `README.md` to match the standard style of `pterodactyl-eggs` repository
- Updated footer copyright to simple text format "RED SHADOWS | RS"

## [v1.0.0] - 2024-08-01

### 🎉 Initial Release
- **Launch:** Initial release of Pterodactyl Containers
- **Support:** Basic support for:
  - Java 8, 11, 17, 21
  - Node.js 18, 20, 22
  - Python 3.9, 3.10, 3.11, 3.12
- **Features:** Multi-arch builds (AMD64/ARM64), automated CI/CD, minimal secure base images
