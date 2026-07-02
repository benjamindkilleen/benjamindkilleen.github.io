# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Benjamin D. Killeen's personal academic website (served at `benjamindkilleen.com`, hosted on GitHub Pages). It is a Jekyll site built on the **academicpages** template, itself a detached fork of the **Minimal Mistakes** theme. Most files under `_includes/`, `_layouts/`, `_sass/`, and `assets/` are inherited theme code — content lives in the collections and `_pages/`.

## Commands

Local development (Ruby/Bundler + Jekyll):

```bash
bundle install                    # install gems (delete Gemfile.lock first if it errors)
bundle exec jekyll serve --livereload   # serve at localhost:4000 with live reload
bundle exec jekyll serve          # serve without live reload
```

`_config.dev.yml` is a local override (disables analytics, sets `url` to localhost). Apply it with:

```bash
bundle exec jekyll serve --livereload --config _config.yml,_config.dev.yml
```

Note: `_config.yml` is **not** reloaded on change — restart the server after editing it.

JavaScript build (only when editing `assets/js/`):

```bash
npm run build:js                  # uglify + concat plugins into assets/js/main.min.js
npm run watch:js                  # rebuild main.min.js on JS change
```

## Deployment

Push to `main` → GitHub Actions (`.github/workflows/deploy.yaml`, `helaili/jekyll-action`) builds and publishes to GitHub Pages. There is no separate deploy step: **committing to `main` publishes the live site.** `CNAME` maps the custom domain.

### `files/cv_killeen.pdf` is auto-generated — do not hand-edit

The CV PDF is built and pushed automatically by a workflow in the **separate `benjamindkilleen/cv` repo** (`.github/workflows/publish-cv.yml`): a push there compiles `cv_killeen.tex` with `latexmk`, then commits the resulting `files/cv_killeen.pdf` into this repo (via a write deploy key), which in turn triggers the Pages deploy above. To update the CV, edit the LaTeX in the `cv` repo and push — never edit the PDF here, it will be overwritten. Commits authored by `cv-publish-bot` are these auto-updates.

## Content architecture

Site config is `_config.yml` (site-wide settings, plus the `collections`, `defaults`, and author block). Content is Markdown with YAML front matter, organized as Jekyll collections declared in `_config.yml`:

- `_posts/` — blog posts (`YYYY-MM-DD-slug.md`); `_drafts/` for unpublished
- `_teaching/` — teaching collection entries
- `_publications/`, `_talks/`, `_portfolio/` — declared collections (create the dir to add entries; not all exist yet)
- `_pages/` — standalone pages (about, cv, publications, talks, teaching, contact, etc.); each routes via its `permalink` front-matter key

Site-wide data lives in `_data/`: `navigation.yml` (top nav), `authors.yml` (author-profile sidebar), `ui-text.yml` (theme strings). Uploaded PDFs/assets go in `files/` and are served at `/files/...`; images in `images/`.

## Generators (optional tooling)

`markdown_generator/` converts TSV (`publications.tsv`, `talks.tsv`) into per-item Markdown for the `publications`/`talks` collections. Each has a `.py` script and an equivalent documented `.ipynb`.

`talkmap.py` / `talkmap.ipynb` scrape the `location:` field from talk `.md` files, geocode them (geopy/Nominatim, requires `getorg`), and emit a Leaflet cluster map into `talkmap/`. Run from the talks collection directory. Enable the link with `talkmap_link: true` in `_config.yml`.

## Editing the theme vs. patching upstream

Because this is a detached fork of academicpages/Minimal Mistakes, theme changes (`_includes/`, `_layouts/`, `_sass/`) diverge from upstream — pulling upstream will conflict. Prefer changing content/config over theme internals unless a layout change is genuinely required.
