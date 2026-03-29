# CLAUDE.md

This is Alex Kim's personal website built with al-folio (Jekyll).

## Key paths
- `_config.yml` — Main site config (URL, name, features)
- `_pages/about.md` — Home page (layout: about, permalink: /)
- `_posts/` — Blog posts (YYYY-MM-DD-title.md)
- `_projects/` — Project pages
- `_bibliography/papers.bib` — Publications (BibTeX)
- `_data/cv.yml` — CV in RenderCV format
- `_data/socials.yml` — Social links
- `assets/img/` — Images (prof_pic.jpg, blog/, projects/)

## Build
```bash
bundle install
bundle exec jekyll serve --port 4000
```

## Deployment
Push to `main` branch. GitHub Actions auto-deploys to GitHub Pages.

## Blog tags
fundamentals, paper-review, system-design, project, personal
