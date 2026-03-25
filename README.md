# 🌟 Free CDNs

A curated list of free Content Delivery Networks (CDNs) for serving open-source libraries and files.

## 📋 Table of Contents

- [🔀 Multi-Source CDNs](#-multi-source-cdns)
- [📦 npm CDNs](#-npm-cdns)
- [📚 Popular Library CDNs](#-popular-library-cdns)
- [🐙 Git-Only CDNs](#-git-only-cdns)
- [🔗 URL Conversion Guide](#-url-conversion-guide)

---

## 🔀 Multi-Source CDNs

CDNs that can serve files from multiple sources (npm, Git repos, etc.).

| CDN | Sources | Base URL |
|-----|---------|----------|
| [jsDelivr](https://www.jsdelivr.com) | npm, GitHub, WordPress | `https://cdn.jsdelivr.net/` |
| [cdnjs](https://cdnjs.com) | npm, GitHub (curated) | `https://cdnjs.cloudflare.com/ajax/libs/` |
| [Statically](https://statically.io) | GitHub, GitLab, Bitbucket, Codeberg, WordPress | `https://cdn.statically.io/` |
| [Raw Githack](https://raw.githack.com) | GitHub, GitLab, Bitbucket, Gitea/Codeberg | `https://rawcdn.githack.com/` |
| [PageCDN](https://pagecdn.io) | npm, GitHub (curated) | `https://pagecdn.io/lib/` |

---

## 📦 npm CDNs

CDNs that serve packages directly from the npm registry.

| CDN | Description | Base URL |
|-----|-------------|----------|
| [unpkg](https://unpkg.com) | Fast global CDN for every npm package | `https://unpkg.com/` |
| [Skypack](https://skypack.dev) | npm packages optimized for modern browsers (ESM) | `https://cdn.skypack.dev/` |
| [esm.sh](https://esm.sh) | Modern ESM CDN for npm packages | `https://esm.sh/` |
| [esm.run](https://esm.run) | jsDelivr-powered ESM CDN | `https://esm.run/` |
| [JSPM](https://jspm.org) | npm packages as native ES modules via import maps | `https://ga.jspm.io/npm:` |

---

## 📚 Popular Library CDNs

CDNs maintained by major companies that host curated, widely-used libraries.

| CDN | Hosted Libraries | Base URL |
|-----|-----------------|----------|
| [Google Hosted Libraries](https://developers.google.com/speed/libraries) | jQuery, Angular, Bootstrap, D3.js, and more | `https://ajax.googleapis.com/ajax/libs/` |
| [Microsoft Ajax CDN](https://learn.microsoft.com/en-us/aspnet/ajax/cdn/overview) | jQuery, Bootstrap, Knockout.js, and more | `https://ajax.aspnetcdn.com/ajax/` |
| [BootstrapCDN](https://www.bootstrapcdn.com) | Bootstrap, Font Awesome, Bootswatch | `https://cdn.bootstrapcdn.com/` |

---

## 🐙 Git-Only CDNs

CDNs that serve raw files directly from Git repositories.

| CDN | Sources | Base URL |
|-----|---------|----------|
| [Combinatronics](https://combinatronics.io) | GitHub | `https://combinatronics.io/` |

---

## 🔗 URL Conversion Guide

Easily convert raw file URLs from popular Git hosting platforms into fast CDN delivery URLs.

### jsDelivr (GitHub only)

> Supports GitHub repositories. Use a specific tag/commit for long-term cache stability.

| Raw GitHub URL | jsDelivr CDN URL |
|----------------|-----------------|
| `https://github.com/{user}/{repo}/blob/{branch}/{file}` | `https://cdn.jsdelivr.net/gh/{user}/{repo}@{branch}/{file}` |
| `https://raw.githubusercontent.com/{user}/{repo}/{branch}/{file}` | `https://cdn.jsdelivr.net/gh/{user}/{repo}@{branch}/{file}` |

**Example:**
```
https://raw.githubusercontent.com/jquery/jquery/3.7.1/dist/jquery.min.js
→ https://cdn.jsdelivr.net/gh/jquery/jquery@3.7.1/dist/jquery.min.js
```

---

### Statically (GitHub, GitLab, Bitbucket, Codeberg)

> Supports multiple Git platforms with a unified URL scheme.

| Platform | Raw URL | Statically CDN URL |
|----------|---------|-------------------|
| **GitHub** | `https://raw.githubusercontent.com/{user}/{repo}/{branch}/{file}` | `https://cdn.statically.io/gh/{user}/{repo}/{branch}/{file}` |
| **GitLab** | `https://gitlab.com/{user}/{repo}/-/raw/{branch}/{file}` | `https://cdn.statically.io/gl/{user}/{repo}/{branch}/{file}` |
| **Bitbucket** | `https://bitbucket.org/{user}/{repo}/raw/{branch}/{file}` | `https://cdn.statically.io/bb/{user}/{repo}/{branch}/{file}` |
| **Codeberg** | `https://codeberg.org/{user}/{repo}/raw/branch/{branch}/{file}` | `https://cdn.statically.io/codeberg/{user}/{repo}/{branch}/{file}` |

**Examples:**
```
# GitHub
https://raw.githubusercontent.com/twbs/bootstrap/v5.3.0/dist/css/bootstrap.min.css
→ https://cdn.statically.io/gh/twbs/bootstrap/v5.3.0/dist/css/bootstrap.min.css

# GitLab
https://gitlab.com/user/repo/-/raw/main/script.js
→ https://cdn.statically.io/gl/user/repo/main/script.js

# Bitbucket
https://bitbucket.org/user/repo/raw/main/style.css
→ https://cdn.statically.io/bb/user/repo/main/style.css

# Codeberg
https://codeberg.org/user/repo/raw/branch/main/script.js
→ https://cdn.statically.io/codeberg/user/repo/main/script.js
```

---

### Raw Githack (GitHub, GitLab, Bitbucket, Gitea/Codeberg)

> Converts raw Git URLs to served-with-correct-MIME-type CDN URLs. Use the production URL (`rawcdn.githack.com` / `gl.githack.com` etc.) for stable, cached delivery.

| Platform | Raw URL | Raw Githack CDN URL |
|----------|---------|---------------------|
| **GitHub** | `https://raw.githubusercontent.com/{user}/{repo}/{commit}/{file}` | `https://rawcdn.githack.com/{user}/{repo}/{commit}/{file}` |
| **GitLab** | `https://gitlab.com/{user}/{repo}/-/raw/{commit}/{file}` | `https://gl.githack.com/{user}/{repo}/-/raw/{commit}/{file}` |
| **Bitbucket** | `https://bitbucket.org/{user}/{repo}/raw/{commit}/{file}` | `https://bb.rawcdn.githack.com/{user}/{repo}/raw/{commit}/{file}` |
| **Gitea / Codeberg** | `https://{host}/{user}/{repo}/raw/branch/{branch}/{file}` | `https://gitea.rawcdn.githack.com/{user}/{repo}/raw/branch/{branch}/{file}` |

> ⚠️ Note: The Gitea subdomain (`gitea.rawcdn.githack.com`) proxies files from known Gitea instances (including Codeberg). For self-hosted or less common Gitea instances, paste your raw URL into [raw.githack.com](https://raw.githack.com) to generate the correct CDN URL.

> 💡 **Tip:** For long-term stability, always pin to a specific **commit hash** or **tag** instead of a branch name (e.g., `main`), since CDNs cache URLs indefinitely.

---

### Gitee (China)

> Gitee raw files can be served directly from Gitee's CDN or via Statically.

| Raw Gitee URL | Served URL |
|---------------|-----------|
| `https://gitee.com/{user}/{repo}/raw/{branch}/{file}` | `https://gitee.com/{user}/{repo}/raw/{branch}/{file}` *(direct, CDN-backed)* |

> ⚠️ Note: Gitee raw file access may require the repository to be **public**. For more reliable global delivery, mirror your Gitee repo to GitHub and use jsDelivr or Statically.

---

## 🤗 Contact Me

- Check you did all things perfectly before contacting [ Warning ]
- For any Support contact [@OshekherO](https://t.me/OshekherO) at Telegram

---
<h4 align='center'>© 2022 ツ ѕнєкнєя</h4>

<!-- DO NOT REMOVE THIS CREDIT 🤬 🤬 -->

