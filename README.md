# ImgToPDF

A single-page, fully client-side web app that converts up to 40 images (JPG, PNG, WEBP) into a single downloadable PDF — directly in your browser. Nothing is uploaded; everything runs locally.

**Live demo:** https://dhatsme.github.io/img-to-pdf/

---

## Features

- **Mobile-first** — tap to open a native file picker (`accept="image/*"`)
- **Drag & drop** — drop files straight onto the page
- **Drag to reorder** — rearrange thumbnail cards before converting (works on mobile too)
- **Canvas compression** — images are resized to a max of 1600 px wide and compressed to JPEG at your chosen quality (40–95 %) before being embedded, keeping file sizes manageable
- **Page size options** — A4, US Letter, or Fit-to-image (page exactly matches each image's dimensions)
- **Progress bar** — tracks per-image processing and final PDF generation
- **Zero dependencies at build time** — jsPDF is loaded from a CDN; no npm, no bundler, no build step
- **Dark theme, monospace UI** — minimal and readable

---

## How to Use

1. Open the app in any modern browser
2. Tap / click the upload area or drag images onto it
3. Reorder thumbnails by dragging them into the desired sequence
4. Choose a page size and compression quality
5. Click **generate PDF**
6. Click **download PDF** when it appears

---

## Run Locally

No build step needed — it is a single HTML file.

```bash
# Option 1: open directly
open index.html          # macOS
xdg-open index.html      # Linux

# Option 2: serve with Python
python3 -m http.server 8080
# → http://localhost:8080

# Option 3: serve with Node.js
npx serve .
# → http://localhost:3000
```

> **Note:** Opening `index.html` directly via `file://` works in most browsers, but serving it over HTTP is recommended to avoid any same-origin quirks.

---

## Deploy to GitHub Pages

### Option A — Automatic (GitHub Actions, already configured)

This repository includes `.github/workflows/pages.yml`. Every push to `main` automatically builds and deploys the site. No extra setup needed after cloning.

### Option B — Manual (branch source)

1. Fork or clone this repository
2. Go to **Settings → Pages**
3. Under **Source**, choose `Deploy from a branch`
4. Select `main` branch, `/ (root)` folder
5. Click **Save**
6. Your app will be live at `https://<your-username>.github.io/img-to-pdf/` within a minute

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| HTML / CSS / JS | Vanilla — no frameworks |
| PDF generation | [jsPDF 2.5.1](https://github.com/parallax/jsPDF) via CDN |
| Image compression | Browser Canvas API |
| Hosting | GitHub Pages |
| Build | None |

---

## Privacy

All processing happens in your browser tab. No images, no PDF data, and no metadata leave your device.

---

## License

MIT
