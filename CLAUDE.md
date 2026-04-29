# CLAUDE.md

Personal website for Alex J. Kim, built with al-folio (Jekyll).

## Site purpose
Public hub tracking ML learning and research. Two content tracks:
- **notes** — ML/DL fundamentals framed through modern practice (e.g., "BatchNorm vs LayerNorm vs RMSNorm for VLM training")
- **research** — Paper implementations and deep dives with repos as artifacts

## Key paths
- `_config.yml` — Site config
- `_pages/about.md` — Homepage (layout: about, permalink: /)
- `_posts/` — Blog posts (YYYY-MM-DD-title.md)
- `_pages/research.md` — Publications + patents (was publications.md)
- `_pages/projects.md` — Project showcases
- `_pages/cv.md` — Embedded PDF resume
- `_data/socials.yml` — Social links (email + github)
- `assets/img/` — Images (prof_pic.jpeg, blog/)
- `assets/pdf/` — Resume PDF

## Blog tags
- `notes` — ML/DL fundamentals (study → teach posts)
- `research` — Paper implementations, deep dives, research posts
- `personal` — Non-technical

## Build
```bash
bundle install
bundle exec jekyll serve --port 4000
```

## Deploy
Push to `main`. GitHub Actions builds and deploys to `gh-pages` → alexjunghokim.github.io.

## Content workflow
1. Work on implementations in ~/workspace/fundamentals/ or ~/workspace/papers/
2. Write draft post alongside the code
3. When ready: copy polished post to _posts/, push implementation to its own GitHub repo
4. Add project card to _pages/projects.md if applicable
5. Never publish half-finished work — site should only show polished output
