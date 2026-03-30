# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static HTML personal blog ("陈大剩博客"). It is a pure static site — no build system, no package.json, no compilation step. All files are served directly as-is.

## Development

Since there is no build process, development is simply editing HTML/CSS files and previewing in a browser. To serve locally:

```bash
python3 -m http.server 8080
# or
npx serve .
```

There are no tests, linters, or CI pipelines.

## Architecture

### Pages
- `index.html` — Home page with article list and sidebar
- `article.html` — Article detail page
- `about.html` — Author profile page
- `time.html` — Timeline page (career/blog history)

### CSS Structure
- `css/common.css` — Shared layout, navigation, header, footer, responsive behavior
- `css/article.css`, `css/about.css`, `css/time.css` — Page-specific styles

### Design System
- Primary accent: `#e74c3c`
- Dark header/footer background: `#1a2332`
- Page background: `#f0f4f8`
- Fonts: system stack with Chinese fallbacks (`PingFang SC`, `Microsoft YaHei`)
- Responsive breakpoints: 768px (tablet), 600px, 480px (mobile)

### Page Structure Pattern
Every page follows the same shell:
1. Top bar (welcome message + login link)
2. Sticky header with nav (Home, PHP, Frontend, About, Timeline)
3. Main content area — 2-column grid (with sidebar) on index/article, 1-column on about/time
4. Footer
5. Back-to-top button + mobile hamburger nav (vanilla JS, no dependencies)

### Content
All article content and comments are hardcoded HTML — there is no CMS or backend. Dynamic values (view counts, comment counts) are placeholder text. The site is authored in Chinese (zh-CN).
