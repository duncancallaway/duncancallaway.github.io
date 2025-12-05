# Repository Guidelines

## Project Structure & Module Organization
- Jekyll site using the Beautiful Jekyll theme.
- Key paths:
  - `_config.yml` — site-wide configuration.
  - `_layouts/`, `_includes/` — theme templates/partials.
  - `_posts/` — blog posts (`YYYY-MM-DD-title.md`).
  - `_data/` — site copy (e.g., `_data/ui-text.yml`).
  - `assets/` — CSS, JS, and images (store images in `assets/img/`).
  - Content pages at the root: `index.html`, `people.md`, `research.html`, etc.
  - `.github/` — CI and contribution templates; `staticman.yml` for comments.

## Build, Test, and Development Commands
- Prereqs: Ruby and Bundler (CI uses Ruby 3.3).
- `bundle install` — install dependencies.
- `bundle exec jekyll serve --livereload` — run locally at `http://127.0.0.1:4000`.
- `bundle exec jekyll build` — build site into `_site/`.
- Optional (theme compatibility): `bundle exec appraisal install` then `bundle exec appraisal jekyll build` to build against multiple Jekyll versions.

## Coding Style & Naming Conventions
- Use 2‑space indentation for YAML, HTML/Liquid, SCSS, and JS.
- Filenames in kebab-case (`people.md`, `my-page.html`); assets similarly (`assets/img/hero-photo.jpg`).
- Posts: `YYYY-MM-DD-my-post.md` with YAML front matter (`layout: post`, `title`, `tags`).
- Keep diffs small, avoid trailing whitespace, and prefer absolute asset paths (`/assets/...`).

## Testing Guidelines
- No unit tests; validate by building locally and browsing key pages.
- Ensure GitHub Actions CI passes (it builds with Jekyll 3 and 4 via Appraisal).

## Commit & Pull Request Guidelines
- Commits: clear, imperative messages (e.g., `fix: correct nav link`).
- PRs: use the template, describe changes, link issues, and include screenshots for visual updates.
- Keep PRs focused; optimize images and avoid committing large binaries.

## Security & Configuration Tips
- Do not commit secrets. Configure analytics/comments via `_config.yml` and `_includes/*`.
- For external JS/CSS, prefer `ext-js`/`ext-css` with SRI when possible.

