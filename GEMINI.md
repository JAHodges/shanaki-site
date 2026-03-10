# Shanaki Martial Arts Website

This project is a modernized, mobile-responsive static website for **Shanaki Martial Arts**, a martial arts studio located in Wytheville, VA. It replaces a legacy 2010-era site with a high-performance architecture built using **Astro**.

## Project Overview

- **Purpose:** Provide information about programs (Pre-K, After School, Youth/Adult), philosophy (Bushido), and instructors.
- **Technologies:**
  - **Framework:** [Astro](https://astro.build/) (Static Site Generator)
  - **Styling:** Vanilla CSS (Flexbox/Grid) with a "Modern Warrior" aesthetic (Red/Black/White).
  - **Deployment:** GitHub Pages via GitHub Actions.
- **Key Features:**
  - Dedicated pages for specialized programs like **Kids Kikkin' It (Pre-K)** and **After School**.
  - Verbatim, third-person instructor biographies.
  - Interactive elements like a functional mobile hamburger menu and a static "Members Only" password gate.
  - Optimized for local SEO in Wytheville, VA.

## Directory Structure

- `/src/pages`: Contains the site's routes. Nested directories like `/programs` and `/instructors` manage sub-pages.
- `/src/layouts`: Contains `MainLayout.astro`, the base template for all pages.
- `/src/components`: Reusable UI elements like `Navigation.astro`, `Footer.astro`, `Logo.astro`, and `ProgramCard.astro`.
- `/public`: Static assets like images and global files.

## Building and Running

### Prerequisites
- Node.js (v18.14.1 or higher recommended)
- Git (configured in your system's PATH)

### Key Commands
- **Install Dependencies:** `npm install`
- **Local Development:** `npm run dev` (Site runs at `http://localhost:4321`)
- **Production Build:** `npm run build` (Static files generated in `/dist`)
- **Preview Build:** `npm run preview` (Preview the production build locally)

## Development Conventions

### Subpath Deployment
Since the site is deployed to a GitHub subpath (`/shanaki-site/`), all internal links **must** be prefixed with the `BASE_URL`.

**Pattern for links:**
```astro
---
const base = import.meta.env.BASE_URL;
---
<a href={`${base}/your-page`}>Link</a>
```

### Aesthetic Standards
- **Typography:** OSWALD for headings, ROBOTO for body text.
- **Color Palette:**
  - Primary Red: `#A50000`
  - Primary Black: `#121212`
  - Background Light: `#F4F4F4`
- **Animations:** Use the `.animate` class for subtle fade-in effects on entry.

### Image Placeholders
The site currently uses stylized SVG placeholders. To replace them, place high-resolution images in `public/images/` and update the relevant components or pages with `<img>` tags or the Astro `<Image />` component.

## Deployment

The site is automatically built and deployed to GitHub Pages via the workflow in `.github/workflows/deploy.yml` whenever changes are pushed to the `main` branch.

- **Production URL:** [https://jahodges.github.io/shanaki-site/](https://jahodges.github.io/shanaki-site/)
