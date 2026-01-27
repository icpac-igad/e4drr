# Local Development Guide for E4DRR Blog

This guide explains how to preview and test blog posts locally before pushing to GitHub.

> **Important:** This site requires **Hugo Extended v0.125.2** or later.
> The HugoBlox theme uses features not available in older Hugo versions.

## How the Site Works

When you push to the `main` branch on GitHub:
1. GitHub Actions triggers the workflow (`.github/workflows/publish.yaml`)
2. Hugo builds the static site from content in `content/blog/`
3. Pagefind generates the search index
4. The site is deployed to GitHub Pages at https://icpac-igad.github.io/e4drr/

## Prerequisites

### 1. Install Hugo (Extended Version)

The site requires **Hugo Extended v0.125.2** (or compatible version).

**Debian/Ubuntu:**

> **Note:** The Debian apt repository has an older version (0.111.x) which is
> incompatible with HugoBlox theme. You must install from GitHub releases.

```bash
# Remove old Hugo if installed via apt
sudo apt remove hugo

# Download Hugo extended 0.125.2
wget https://github.com/gohugoio/hugo/releases/download/v0.125.2/hugo_extended_0.125.2_linux-amd64.deb

# Install
sudo dpkg -i hugo_extended_0.125.2_linux-amd64.deb

# Verify installation
hugo version
# Should show: hugo v0.125.2+extended ...
```

**Using Snap (gets latest extended):**
```bash
sudo snap install hugo --channel=extended
```

**Using Homebrew on Linux:**
```bash
brew install hugo
```

**macOS (Homebrew):**
```bash
brew install hugo
```

**Windows (Chocolatey):**
```bash
choco install hugo-extended
```

### 2. Install Go

Hugo modules require Go 1.19 or later.

**Debian/Ubuntu:**
```bash
sudo apt install golang-go

# Verify
go version
```

**Or download from:** https://go.dev/dl/

### 3. Install Node.js (for Pagefind search)

Required only if you want to test the search functionality locally.

```bash
# Using apt
sudo apt install nodejs npm

# Or using nvm (recommended)
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash
nvm install --lts
```

## Running the Local Development Server

### Quick Start (Most Common)

From the project root directory:

```bash
cd /home/roller/Documents/08-2023/working_notes_jupyter/ignore_nka_gitrepos/e4drr

# Start Hugo development server
hugo server
```

This will:
- Start a local server at http://localhost:1313/
- Watch for file changes and auto-reload
- Show draft posts (if any)

### Common Hugo Server Options

```bash
# Basic server with live reload
hugo server

# Include draft posts
hugo server -D

# Include future-dated posts
hugo server -F

# Specify a different port
hugo server --port 1314

# Bind to all interfaces (access from other devices)
hugo server --bind 0.0.0.0

# Disable live reload
hugo server --disableLiveReload

# Combined: show drafts, future posts, on custom port
hugo server -D -F --port 1314
```

## Building the Site Locally

To generate the static files (like the GitHub Action does):

```bash
# Build the site
hugo

# Build with minification (production-like)
hugo --minify

# Build and generate search index
hugo --minify && npx pagefind --source "public"
```

The output will be in the `public/` directory.

## Blog Post Structure

Blog posts are located in `content/blog/` with this structure:

```
content/blog/
├── 2024-12-dcv/
│   └── index.md          # Main content file
├── 2025-03-tech-stack/
│   ├── index.md          # Main content
│   └── featured.png      # Optional featured image
└── _index.md             # Blog section configuration
```

### Creating a New Blog Post

1. Create a new folder with date prefix:
```bash
mkdir -p content/blog/2025-01-27-my-new-post
```

2. Create `index.md` with frontmatter:
```markdown
---
title: My New Blog Post Title
summary: A brief description of the post for previews.
date: 2025-01-27

authors:
  - Nishadh

tags:
  - Climate
  - Forecasting
---

## Introduction

Your content here...
```

### Frontmatter Options

| Field | Description | Example |
|-------|-------------|---------|
| `title` | Post title | `"My Post Title"` |
| `summary` | Short description | `"Brief summary..."` |
| `date` | Publication date | `2025-01-27` |
| `authors` | List of authors | `- Nishadh` |
| `tags` | Topic tags | `- Climate` |
| `draft` | Hide from production | `true` |
| `featured` | Pin to top | `true` |

## Troubleshooting

### "can't evaluate field Process" or template errors

This error occurs when Hugo version is too old:
```
error calling partial: ... can't evaluate field Process in type resource.Resource
```

**Solution:** Upgrade Hugo to v0.125.2 or later:
```bash
# Check current version
hugo version

# If older than 0.125.2, upgrade:
wget https://github.com/gohugoio/hugo/releases/download/v0.125.2/hugo_extended_0.125.2_linux-amd64.deb
sudo dpkg -i hugo_extended_0.125.2_linux-amd64.deb
```

### "module not found" error

Run Hugo's module download:
```bash
hugo mod get -u
hugo mod tidy
```

### Styles not loading

Ensure you have Hugo **Extended** version (includes CSS processing):
```bash
hugo version
# Must show "+extended"
```

### Port already in use

Use a different port:
```bash
hugo server --port 1314
```

### Cache issues

Clear Hugo's cache:
```bash
rm -rf resources/
hugo server
```

## Workflow Summary

```
┌─────────────────────────────────────────────────────────┐
│                   LOCAL DEVELOPMENT                      │
├─────────────────────────────────────────────────────────┤
│  1. Edit content/blog/YYYY-MM-DD-name/index.md          │
│  2. Run: hugo server                                     │
│  3. Preview at: http://localhost:1313/blog/             │
│  4. Make changes → auto-reload                           │
└─────────────────────────────────────────────────────────┘
                           │
                           ▼
┌─────────────────────────────────────────────────────────┐
│                    GIT & GITHUB                          │
├─────────────────────────────────────────────────────────┤
│  1. git add content/blog/your-post/                     │
│  2. git commit -m "Add new blog post"                   │
│  3. git push origin main                                │
└─────────────────────────────────────────────────────────┘
                           │
                           ▼
┌─────────────────────────────────────────────────────────┐
│                  GITHUB ACTIONS                          │
├─────────────────────────────────────────────────────────┤
│  Automatic on push to main:                             │
│  • Checkout repo                                        │
│  • Build with Hugo 0.125.2                              │
│  • Generate Pagefind search index                       │
│  • Deploy to GitHub Pages                               │
│                                                         │
│  Live at: https://icpac-igad.github.io/e4drr/          │
└─────────────────────────────────────────────────────────┘
```

## Quick Reference

| Task | Command |
|------|---------|
| Start dev server | `hugo server` |
| Preview with drafts | `hugo server -D` |
| Build site | `hugo --minify` |
| Update modules | `hugo mod get -u` |
| Clear cache | `rm -rf resources/` |
| Check version | `hugo version` |
