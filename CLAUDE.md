# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static HTML5 portfolio website for Lech Jankowski, built on the FREEHTML5.co "Voltage" responsive template. Pure frontend — no build system, no package manager, no backend.

## Running Locally

Serve with any static HTTP server:
```
python -m http.server 8000
```
Then open `http://localhost:8000`. Opening `index.html` directly via `file://` also works.

There is no build step, no linter, and no test suite.

## SASS Compilation

Source SASS lives in `sass/`. CSS in `css/` is already compiled. To recompile after editing SASS:
```
sass sass/style.scss css/style.css
```

## Architecture

- **`index.html`** — Main landing page with navigation, hero section, project grid, "Why Me?" features, testimonials, and footer
- **`proj_*.html`** (7 files) — Individual project detail pages, each following the same template structure: nav header, project description, screenshot thumbnails, and a lines-of-code counter
- **`js/main.js`** — All custom JavaScript in a single IIFE. Handles: full-height sections, parallax (Stellar.js), scroll-triggered counters (Waypoints + countTo), off-canvas mobile menu, sticky navbar on scroll, and Magnific Popup lightbox
- **`css/style.css`** / **`sass/_style.scss`** — Primary custom styles. Color theme defined via SASS variable `$fh5co-primary` (currently `#6173f4`)
- **`css/cards.css`** / **`sass/cards.scss`** — Project card grid styles
- **`css/custom.css`** — Page loader overlay styles only

## Key Libraries (all vendored locally)

jQuery 1.9.1, Bootstrap 3, Animate.css, Owl Carousel, Magnific Popup, Stellar.js (parallax), Waypoints, WOW.js, countTo. Google Fonts loaded externally (Open Sans, Montserrat, Merriweather).

## Conventions

- All pages share the same nav/footer structure and link back to `index.html`
- Scroll animations use WOW.js classes (`wow`) with `data-wow-duration` and `data-wow-delay` attributes
- Parallax sections use `data-stellar-background-ratio` attributes
- Mobile breakpoint at 769px triggers off-canvas menu and overflow classes
- Images are in `images/` (backgrounds) and `screenshots/` (project screenshots); testimonial photos in `people/`
