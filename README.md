# Investigation Pathways (Jekyll Starter)

This repository contains the starter framework for the **Archivory Investigation Pathways** interactive exhibit.

It is now set up as a **Jekyll site**, so you can:
- Run it locally with `bundle exec jekyll serve`
- Deploy it via GitHub Pages
- Later merge it into the main Archivory Jekyll workspace.

> **⚠️ Important:** Before running the site, you must download the actual Alpine.js library (see [Running locally](#running-locally) section below). The current `assets/js/vendor/alpine.min.js` is a placeholder and will not provide full functionality.

## Structure

```text
.
├── _config.yml
├── README.md
├── index.html
├── pathways.js
├── pathways.css
│
├── _layouts/
│   └── default.html
│
├── _includes/
│   ├── step-card.html
│   ├── object-card.html
│   └── pathway-selector.html
│
├── _data/
│   ├── objects.yml
│   ├── methods.yml
│   └── pathways.yml
│
└── assets/
    ├── css/
    │   └── reset.css
    ├── images/
    │   ├── placeholders/
    │   │   └── placeholder.jpg
    │   └── objects/
    └── js/
        └── vendor/
            └── alpine.min.js
```

## Running locally

1. **Download Alpine.js** (required for interactive functionality):
   - Download the latest Alpine v3 build from https://alpinejs.dev
   - Replace `assets/js/vendor/alpine.min.js` with the downloaded file
   - Direct link: https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js
   - Or install via npm: `npm install alpinejs`

2. Install Jekyll and Bundler if you don't have them:
   ```bash
   gem install bundler jekyll
   ```

3. Install dependencies:
   ```bash
   bundle install
   ```

4. From this repo directory, run:
   ```bash
   bundle exec jekyll serve
   ```

5. Open your browser at `http://localhost:4000`.

## How data flows

- YAML files in `_data/` (objects, methods, pathways) are loaded by Jekyll at build time.
- Jekyll injects that data into the page via `window.PATHWAYS_DATA` in the layout.
- Alpine.js (`pathwaysApp`) reads `window.PATHWAYS_DATA` and powers the interactive UI.

This means **no backend**, no fetch calls, and no extra YAML parsing library are required.