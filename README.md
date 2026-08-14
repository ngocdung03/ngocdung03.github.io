# ngocdung03.github.io

Personal portfolio site — Jekyll, deployed by GitHub Pages.

Live at <https://ngocdung03.github.io>.

## Structure

```
_config.yml            site config, nav, collections
index.html             home page
about.md               about page
cv.html                CV
projects.html          project index (renders _projects/)
publications.html      publication list (renders _data/publications.yml)
_projects/             one Markdown file per project
_data/publications.yml publication list, edit here
_layouts/              default, page, project
_includes/             nav, footer
assets/css/style.scss  all styling
files/                 CV PDF and other downloads
```

## Adding content

**A project** — drop a new file in `_projects/`:

```yaml
---
title: "Project name"
subtitle: "One-line description."
period: "2025"
org: "Where"
summary: "Shown on the index pages."
tech: ["PyTorch", "Survival analysis"]
repo: "https://github.com/..."
---

Body in Markdown.
```

**A publication** — add an entry to the top of `_data/publications.yml`.

**A nav item** — add to the `nav:` list in `_config.yml`.

## Local preview

With Ruby installed:

```bash
bundle install
bundle exec jekyll serve --livereload
```

Or with Docker, no Ruby setup needed:

```bash
docker run --rm -it -v "$PWD:/srv/jekyll" -p 4000:4000 \
  jekyll/jekyll:4 jekyll serve --host 0.0.0.0
```

Then open <http://localhost:4000>.

## Deploy

Push to `main`. GitHub Pages builds and publishes automatically — no CI
workflow needed. Enable it once under **Settings → Pages → Source: Deploy from
a branch → main / (root)**.
