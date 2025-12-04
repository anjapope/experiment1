# Investigation Pathways (Jekyll Starter)

This repository contains the starter framework for the **Archivory Investigation Pathways** interactive exhibit.

It is now set up as a **Jekyll site**, so you can:
- Run it locally with `bundle exec jekyll serve`
- Deploy it via GitHub Pages
- Later merge it into the main Archivory Jekyll workspace.

> **✨ Note:** Alpine.js v3 is loaded from CDN, so the site is ready to use without any additional setup.

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
    │   │   └── placeholder.svg  # Replace with actual .jpg images
    │   └── objects/
    └── js/
        └── vendor/
```

## Running locally

1. Install Jekyll and Bundler if you don't have them:
   ```bash
   gem install bundler jekyll
   ```

2. Install dependencies:
   ```bash
   bundle install
   ```

3. From this repo directory, run:
   ```bash
   bundle exec jekyll serve
   ```

4. Open your browser at `http://localhost:4000`.

## How data flows

- YAML files in `_data/` (objects, methods, pathways) are loaded by Jekyll at build time.
- Jekyll injects that data into the page via `window.PATHWAYS_DATA` in the layout.
- Alpine.js (`pathwaysApp`) reads `window.PATHWAYS_DATA` and powers the interactive UI.

This means **no backend**, no fetch calls, and no extra YAML parsing library are required.