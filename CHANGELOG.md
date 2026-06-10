# Changelog

All notable changes to this project will be documented in this file.

## [v12.0.0] - 2026-06-10

### 🚀 Added
- **Arabic README:** Added `README_AR.md` with full Arabic translation and language toggle.
- **Language Toggle:** Added tab-style language switcher between English and Arabic.

### 🔄 Updated
- **Version Bump:** All Dockerfiles updated from v11.0.0 → v12.0.0.
- **Code Cleanup:** Removed blank lines from entrypoint headers, normalized `\$` escaping.
- **Formatting:** Fixed CMD format inconsistency in Java Dockerfiles. Removed redundant `.dockerignore` patterns.
- **README:** Complete redesign — clean, professional layout with table of contents, organized sections, and proper language icons.
- **Logo:** Removed `assets/logo.svg`. Using clean text-based header instead.

## [v11.0.0] - 2026-06-10

### 🚀 Added
- **Softwares:** New `src/softwares/` category added.
- **code-server:** Added code-server image (Debian 12 bookworm-slim, multi-arch, auto-latest).
- **CI/CD:** Added `concurrency` group to prevent duplicate builds.
- **Robustness:** Added `SHELL pipefail` directive to all Dockerfiles.
- **`.dockerignore` / `.gitignore`:** Added project-level ignore files.
- **Logo:** Added project SVG logo in `assets/logo.svg`.

### 🔄 Updated
- **CI/CD:** Updated `docker/build-push-action` from `v5` to `v6`.
- **Reproducibility:** Removed `apt-get upgrade -y` from all Dockerfiles (rely on base image rebuilds).
- **DEBIAN_FRONTEND:** Added `noninteractive` to all non-Python Dockerfiles.
- **Entrypoints:** Normalized formatting across all entrypoint scripts.
- **Repository URL:** Fixed OCI labels across all 21 Dockerfiles to point to `red-shadows-rs/pterodactyl-containers`.
- **Version Labels:** Updated all Dockerfile `LABEL version` to `11.0.0`.
- **code-server:** Now fetches latest release dynamically via GitHub API instead of hardcoded v4.123.0.
- **README:** Complete redesign with professional layout, tables, badges, and project logo.
- **Image Tags:** Removed commit SHA tags from framework images. Removed code-server `:v4.123.0` tag (only `:latest` remains for dynamic builds).

### 🗑️ Deprecated
- **Node.js 18:** EOL since April 2025, marked as deprecated.
- **Python 3.8:** EOL since October 2024, marked as deprecated.
- **Python 3.9:** EOL since October 2025, marked as deprecated.

## [v10.0.0] - 2025-12-18

### 🚀 Added
- **Java:** Added support for **Java 25**.
- **Node.js:** Added support for **Node.js 24**.
- **Python:** Added support for **Python 3.13** and **3.14**.
- **Web Frameworks:** Added dedicated containers for **React**, **Next.js**, **Vue.js**, and **Angular**.

### 🔄 Updated
- **Workflow:** Updated GitHub Actions to build new versions and frameworks.
- **Documentation:** Complete overhaul of README to match `pterodactyl-eggs` style.

## [v9.2] - 2025-06-24

### 🔄 Updated
- **Entrypoint:** Fixed entrypoint for direct command execution.

## [v9.1] - 2025-06-24

### 🔄 Updated
- **Documentation:** Fixed README formatting and typos.

## [v9.0] - 2025-06-24

### 🔄 Updated
- **Maintenance:** Updated Dockerfile paths for all images.

## [v8.0] - 2025-06-23

### 🗑️ Removed
- **Node.js:** Removed deprecated versions (v14, v16).
- **Cleanup:** Updated base images to `bookworm` and `bullseye`.

## [v7.0] - 2025-06-23

### 🔄 Changed
- **Refactor:** Major reorganization of eggs into specific Language/Framework folders.

## [v6.5] - 2025-06-23

### 🔄 Changed
- **Standardization:** Unified variable names across all languages.
- **CI/CD:** Improved pipeline cleanup.

## [v4.0] - 2025-06-23

### 🚀 Added
- **Web Frameworks:** Introduced initial support for React, Next.js, Vue, and Angular.

## [v3.0] - 2025-06-23

### 🚀 Added
- **Node.js:** Native TypeScript support and new egg architecture.

## [v2.0] - 2025-06-23

### 🔄 Updated
- **Optimization:** General cleanup and Docker image optimizations.

## [v1.0] - 2025-06-15

### 🎉 Initial Release
- **Launch:** Initial release of Pterodactyl Containers.
- **Support:**
  - Java 8, 11, 17, 21
  - Node.js 18, 20
  - Python 3.9, 3.10, 3.11, 3.12
