# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal academic website for William Radaic (PhD student, UC Berkeley Economics). Built with Hugo using the hugo-bearblog theme, deployed to GitHub Pages at radaic.me.

## Commands

- **Local development**: `hugo server` (runs at localhost:1313)
- **Build**: `hugo --minify`
- **Create new content**: `hugo new content/<filename>.md`

## Architecture

### Hugo Structure
- `hugo.toml` - Site configuration (base URL, theme, menus, params)
- `content/` - Markdown content files with TOML frontmatter
- `layouts/` - Template overrides for the hugo-bearblog theme
- `static/` - Static assets (CV PDF, images, photos, favicon)
- `themes/hugo-bearblog/` - Theme submodule

### Custom Shortcodes (`layouts/shortcodes/`)
- `gallery` - Masonry photo gallery with GLightbox lightbox; format: `path | title | location | date` per line
- `twocol` - Two-column responsive layout; use `<!--right-->` to separate left (60%) and right (40%) content
- `mail` - Email display with base64 obfuscation for spam protection
- `center` - Center-align content
- `hOne` - Custom h1 styling

### Theme Customization (`layouts/partials/`)
- `custom_head.html` - Custom CSS variables, fonts (IBM Plex Sans/Serif), dark mode support
- `footer.html` - Footer override

### Deployment
GitHub Actions workflow (`.github/workflows/hugo.yml`) builds and deploys to GitHub Pages on push to main. Uses Hugo extended v0.124.1.
