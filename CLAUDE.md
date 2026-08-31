# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal portfolio website for Manny Negrete, hosted on GitHub Pages. Live at [https://mgnegrete.github.io](https://mgnegrete.github.io).

## Development

**No build step.** Open `index.html` directly in a browser to preview. No npm, no bundler, no server required.

**Editing styles:** The source styles live in `assets/sass/`. The compiled output is `assets/css/main.css`. If you edit the SASS source, you need a SASS compiler to regenerate `main.css`. If no SASS compiler is available, edit `assets/css/main.css` directly instead.

## Architecture

Everything is a single file: `index.html` (~600 lines). All portfolio sections (Home, Projects, About, Contact) are rendered as `<article>` panels inside a `<div id="main">`. Navigation between them is handled by `assets/js/main.js`, which listens to URL hash changes (`#intro`, `#work`, `#about`, `#contact`) to show/hide the corresponding panel.

**Key layout elements in `index.html`:**
- `#wrapper` — top-level container
- `#header` — navigation bar with FontAwesome icon links
- `#main` — contains all section `<article>` panels
- Each panel: `<article id="<section>" class="panel">`

**Assets layout:**
- `assets/sass/libs/` — SASS partials (vars, mixins, breakpoints, grid)
- `assets/js/main.js` — panel switching, responsive nav behavior
- `images/` — all project screenshots and profile photos

## Adding a Project

Add a new card inside the `#work` article in `index.html`. Follow the existing card markup pattern (`.work-item` / `.image.fit` structure with hover overlay).
