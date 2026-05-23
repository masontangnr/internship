# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **Studio Kairos internship project** built on [reveal.js](https://revealjs.com/) v6.0.1 — an HTML presentation framework. The repository is used to create and host web-based presentations for internship curriculum content (business, marketing, AI, etc.), with `day1.md` as an example curriculum outline.

## Commands

```bash
npm start            # Start Vite dev server
npm run build        # Full production build (core + plugins + styles)
npm run build:core   # Build core JS only
npm run build:styles # Build CSS/themes only
npm run build:es5    # Build ES5-compatible bundle
npm test             # Run QUnit tests via Puppeteer
npm run package      # Create distributable zip

# React wrapper (in /react subdirectory)
npm run react:build  # Build React wrapper
npm run react:demo   # Run React demo app
npm run react:test   # Test React wrapper
```

## Architecture

```
/js          - TypeScript source (core framework)
  /components  - UI components (controls, overlays, etc.)
  /controllers - Logic controllers (keyboard, touch, fragments, etc.)
  /utils       - Shared utilities
/css         - SCSS stylesheets
  /theme       - Bundled themes (black, white, moon, sky, etc.)
  /print       - Print/PDF styles
/plugin      - Official plugins: highlight, markdown, math, notes, search, zoom
/react       - React wrapper package (separate npm package)
  /src         - React source
  /demo        - React integration demo
/dist        - Built output (gitignored from source, committed in releases)
/scripts     - Build utilities (add-banner.js, build-es5.js, zip.js, test.js)
/examples    - Usage examples
```

**Build system:** Vite + Rollup. Two Vite configs: `vite.config.ts` (JS library) and `vite.config.styles.ts` (CSS). The `npm run build` script orchestrates both.

**Output formats:** ES module (`dist/reveal.mjs`), CommonJS (`dist/reveal.js`), plus CSS and TypeScript type definitions.

**Testing:** QUnit tests run headlessly via Puppeteer (`node-qunit-puppeteer`). Tests live in `/test`.

## Internship Context

`day1.md` is a curriculum outline for Studio Kairos interns. Interns include:
- **Abdullah** — building web pages for Clear Lake Tutor (CLT) website
- **Lauren** — creating chemistry education content and cheat sheets
- **Roshan** — producing YouTube videos
- **Emma** — doing marketing research and social media content

Presentations built with reveal.js are the primary deliverable format for curriculum content.
