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
- `_students/` — collection of student pages (one Markdown file per student).
- No local `_layouts/` or `_includes/` — the theme provides templates. Only add files there if you need to override specific templates.

## Configuration

- Navigation (`navbar-links`), social links, colors, analytics, and comments are configured in `_config.yml`.
- Prefer absolute asset paths like `/assets/img/...`.
- Update any image references in page front‑matter to match actual filenames in `assets/img/`.

### Students collection

- Add a new student by creating a Markdown file in `_students/`, e.g. `_students/jane-doe.md`:

  ```yaml
  ---
  title: Jane Doe
  role: PhD Student
  email: jane.doe@berkeley.edu
  website: https://janedoe.example.com
  # Optional image stored at /assets/img/students/jane-doe.jpg
  # photo: /assets/img/students/jane-doe.jpg
  ---
  Short bio or description.
  ```

- Each student page is generated at `/people/<filename>/` and the homepage and People page automatically list all current students and alumni with links to their pages.
- Student cards fall back to `/assets/img/avatar-icon.png` if no `photo` is provided.

#### Marking alumni

- To show someone under Alumni, add `alumni: true` in their front matter:

  ```yaml
  ---
  title: John Smith
  role: PhD, 2024
  alumni: true
  ---
  ```

- Current students should either omit `alumni` or set it to `false`.

## Continuous Integration

- GitHub Actions builds the site via `.github/workflows/ci.yml`.
- CI installs dependencies, sets a preview `baseurl`, and builds with Appraisal against Jekyll 3 and 4.

## Troubleshooting

- If `jekyll serve` fails on Ruby 3+, ensure `webrick` is installed (included in the Gemfile).
- Port already in use? Run with `--port 4001` or stop the existing server.
