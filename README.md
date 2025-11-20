# EMAC Jekyll Site

Static website for the EMAC group, built with Jekyll. The site uses the Beautiful Jekyll theme via `remote_theme` (the theme code is not vendored in this repo).

## Local Development

- Prerequisites
  - Ruby 3.3 and Bundler installed
  - No Node.js required

- Install dependencies
  - `bundle install`

- Run the dev server
  - `bundle exec jekyll serve --livereload`
  - Open `http://127.0.0.1:4000`

- Build for production
  - `bundle exec jekyll build`
  - Output is generated in `_site/`

- Optional: build against multiple Jekyll versions (theme compatibility)
  - `bundle exec appraisal install`
  - `bundle exec appraisal jekyll build`

## Project Structure

- `_config.yml` — main site config; references the theme via `remote_theme` and configures `plugins`.
- `_posts/` — blog posts (`YYYY-MM-DD-title.md`).
- Root content pages — `index.html`, `people.md`, `research.*`, `tags.html`, `404.html`, `feed.xml`.
- `_data/ui-text.yml` — site copy.
- `assets/` — static assets; store images in `assets/img/`.
- No local `_layouts/` or `_includes/` — the theme provides templates. Only add files there if you need to override specific templates.

## Configuration

- Navigation (`navbar-links`), social links, colors, analytics, and comments are configured in `_config.yml`.
- Prefer absolute asset paths like `/assets/img/...`.
- Update any image references in page front‑matter to match actual filenames in `assets/img/`.

## Continuous Integration

- GitHub Actions builds the site via `.github/workflows/ci.yml`.
- CI installs dependencies, sets a preview `baseurl`, and builds with Appraisal against Jekyll 3 and 4.

## Troubleshooting

- If `jekyll serve` fails on Ruby 3+, ensure `webrick` is installed (included in the Gemfile).
- Port already in use? Run with `--port 4001` or stop the existing server.

