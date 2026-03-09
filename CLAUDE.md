# CLAUDE.md

## Project Overview

**Tilou (Formations IA)** — A static single-page landing website for professional AI training courses (French language). Built with vanilla HTML5, CSS3, and JavaScript — no frameworks or build tools.

The page follows the **AIDA marketing framework** (Attention → Interest → Desire → Action) to drive lead generation for 12 AI training programs across beginner, intermediate, and advanced levels.

## File Structure

```
Tilou/
├── index.html    # Main HTML (640 lines) — page structure and content
├── styles.css    # All styling (1273 lines) — light theme, responsive
├── script.js     # Vanilla JS (200 lines) — interactivity and animations
└── CLAUDE.md     # This file
```

There are no subdirectories, no config files, no package manager, and no build pipeline. The entire site is three files.

## How to Run

Serve the files with any static HTTP server:

```bash
python3 -m http.server 8000
# or: npx serve
# or: php -S localhost:8000
```

Then open `http://localhost:8000` in a browser.

## No Build, No Tests, No Linting

- No package.json, no node_modules, no build step
- No test framework or test files
- No ESLint, Prettier, or stylelint configs
- No CI/CD pipeline or GitHub Actions

All quality is maintained through consistent manual conventions.

## Architecture & Page Sections

The page is structured as sequential sections following the AIDA funnel:

| Section ID | Purpose | AIDA Phase |
|---|---|---|
| `#hero` | Headline, CTA, urgency badges | Attention |
| `#stats-bar` | Animated counter statistics | Interest |
| `#probleme-solution` | Problem/solution comparison cards | Interest |
| `#formations` | Course catalog with level filtering | Interest |
| `#resultats` | Success metrics and proof | Desire |
| `#methode` | Methodology explanation | Desire |
| `#temoignages` | Testimonials with star ratings | Desire |
| `#garanties` | Risk-reversal guarantees | Desire |
| `#contact` | Lead capture form | Action |
| `#faq` | FAQ accordion | Action |
| `footer` | Links, legal, social proof | — |

## Naming Conventions

### CSS
- **BEM-like with dashes**: `.formation-card`, `.nav-links`, `.filter-btn`
- **State classes**: `.active`, `.hidden`, `.scrolled`
- **Level badges**: `.badge-debutant`, `.badge-intermediaire`, `.badge-avance`
- **CSS custom properties** for theming are defined in `:root` (e.g., `--primary`, `--bg`, `--text`)

### JavaScript
- **camelCase** for variables and functions
- Modern APIs: `IntersectionObserver`, `requestAnimationFrame`
- DOM selection via `document.querySelector` / `querySelectorAll`
- Data attributes for behavior: `data-level`, `data-filter`, `data-target`

### HTML
- Semantic elements: `<nav>`, `<section>`, `<footer>`, `<form>`
- Section IDs for anchor navigation
- `aria-label` attributes for accessibility

## Design System (CSS Variables)

| Variable | Value | Usage |
|---|---|---|
| `--primary` | `#4f46e5` | Indigo — buttons, links, accents |
| `--secondary` | `#0ea5e9` | Sky blue — secondary elements |
| `--accent` | `#f59e0b` | Amber — highlights, badges |
| `--success` | `#10b981` | Green — positive indicators |
| `--danger` | `#ef4444` | Red — urgency elements |
| `--bg` | `#ffffff` | White background |
| `--text` | `#334155` | Dark gray body text |

Standard border-radius: `12px` (cards), `20px` (large elements). Transitions: `0.3s cubic-bezier`.

## Key Interactive Features (script.js)

- **Navbar**: Adds `.scrolled` class with backdrop blur on scroll
- **Mobile menu**: Hamburger toggle for `nav-links`
- **Course filtering**: Filters `.formation-card` elements by `data-level` attribute
- **FAQ accordion**: One-open-at-a-time toggle on `.faq-item` elements
- **Counter animation**: `IntersectionObserver` triggers `animateCounters()` on `#stats-bar`
- **Fade-up animations**: `IntersectionObserver` adds `.fade-up` class to cards on scroll
- **Smooth scroll**: Anchor links scroll smoothly to target sections

## Responsive Breakpoints

- **Desktop**: Default styles
- **Tablet**: `@media (max-width: 768px)`
- **Mobile**: `@media (max-width: 480px)`

## Content Details

12 training courses organized by level:

- **Debutant** (Beginner): 3 courses, 1 day (7h), ~490 EUR
- **Intermediaire** (Intermediate): 4 courses, 2 days (14h), 890-990 EUR
- **Avance** (Advanced): 5 courses, 2-5 days, 990-2490 EUR

## Guidelines for AI Assistants

- **Language**: All user-facing content is in **French**. Preserve French text, accents, and formatting.
- **No frameworks**: Do not introduce React, Vue, Tailwind, or any framework. Keep it vanilla HTML/CSS/JS.
- **No build tools**: Do not add webpack, vite, npm, or any build pipeline unless explicitly requested.
- **Single-page**: All content lives in `index.html`. Do not split into multiple pages.
- **CSS variables**: Use existing custom properties for colors/theming rather than hardcoding values.
- **Minimal dependencies**: The only external resource is Google Fonts (Inter). Avoid adding CDN libraries.
- **Consistency**: Follow the existing naming patterns (dash-case CSS, camelCase JS, semantic HTML).
- **Mobile-first awareness**: Test changes against the existing responsive breakpoints.
