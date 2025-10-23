# Abdulla Al Kafy — Personal Academic Portfolio

This repository contains a static HTML/CSS/JS single-page academic portfolio for Dr. Abdulla Al Kafy. The site is implemented as plain HTML with Tailwind CSS via CDN and some lightweight inline JavaScript for UI interactions (mobile menu, gallery, publication toggles, filters).

## Status (Oct 23, 2025)
- Primary site files: `index.html`, `code.html` (both are variants of the same page).
- Assets folder: `site-assets/` contains profile image, gallery images, and a CV document.
- Recent maintenance done:
  - Fixed duplicated "Show more/Show less" publication buttons and JS syntax errors.
  - Imported full publication list from `about.txt` into the publications section.
  - Removed hrefs from publication entries (they are plain text now).
  - Moved a subset of images and CV to `site-assets/` and updated HTML references.

## How to preview locally
1. Open `index.html` or `code.html` in any modern browser (double-click or use `File > Open`).
2. For a proper local server environment (recommended), run a small HTTP server in the project root:

PowerShell (Windows):

```powershell
# if you have Python installed
python -m http.server 8000
# then open http://localhost:8000/index.html
```

## Quick checklist / priorities for future improvements
Below are prioritized items with concrete steps, estimated effort, and acceptance criteria.

1) Normalize asset filenames and paths
- Why: Spaces and special characters in filenames can break URLs and tooling (CI, hosting).
- What to do:
  - Rename files in `site-assets/` to lowercase, hyphen-separated names (e.g., `main-profile-photo.jpg`, `cv-abdulla-al-kafy-2025.docx`).
  - Update all references in `index.html` and `code.html`.
- Estimated effort: 15–30 minutes.
- Acceptance: All pages load images and the CV link works locally and on GitHub Pages.

2) Convert CV to PDF and provide both DOCX and PDF downloads
- Why: PDFs are more widely supported for downloads and previews in browsers.
- What to do:
  - Export/convert the DOCX to PDF (local tool or Google Docs).
  - Add a `download` link for both formats; prefer `cv-abdulla-al-kafy-2025.pdf` as primary.
- Estimated effort: 10–20 minutes (file conversion + link update).

3) Optimize gallery images (resize + web-friendly formats)
- Why: Faster page load, smaller repo size, better mobile UX.
- What to do:
  - Generate web-optimized versions (WebP and appropriately sized JPEGs) using an image tool (ImageMagick or a GUI app).
  - Replace gallery src with optimized versions and add `loading="lazy"` to `<img>` tags.
- Estimated effort: 30–60 minutes for a small set of images.

4) Add a build step and asset pipeline (optional)
- Why: Easier to maintain, process assets, and minify CSS/JS.
- What to do:
  - Initialize a minimal npm project: `npm init -y`.
  - Add `parcel` or `vite` for bundling, add PostCSS/Tailwind config if you want to build Tailwind locally.
  - Move inline JS to a small `main.js` and import styles.
- Estimated effort: 2–4 hours.

5) Improve accessibility and semantic HTML
- Why: Better SEO and usability.
- What to do:
  - Add meaningful alt attributes (already partially present), ensure <main>/<header>/<nav> are used correctly.
  - Fix any heading order issues, ensure color contrast meets WCAG AA.
- Estimated effort: 1–2 hours.

6) Add tests / automated checks
- Why: Prevent regressions.
- What to do:
  - Add a simple HTML validator step (e.g., GitHub Action that runs an HTML linter or validator).
  - Add a GitHub Pages deployment workflow (if desired) to automatically deploy from `master` branch.
- Estimated effort: 30–60 minutes.

## Small UX Improvements (low effort)
- Add `loading="lazy"` to gallery `<img>` tags.
- Add `rel="noopener"` to external links with `target="_blank"`.
- Consider a lightbox for gallery images (e.g., [GLightbox], [Fancybox]) for nicer viewing.

## Suggested next concrete tasks I can do for you now
- Rename `site-assets` files to URL-friendly names and update HTML references. (I can do this now.)
- Convert the CV to PDF (I can't convert binaries here, but I can add a placeholder and instructions or update links if you provide the PDF).
- Optimize gallery images and add lazy loading.

If you want me to proceed with any of the suggested tasks, tell me which one and I'll update the todo list and start. If you prefer custom wording for this README, I can adjust it before committing.
