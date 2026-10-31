# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

Personal Jekyll blog served by GitHub Pages at https://www.ericschwabe.com (custom domain set in `CNAME`). Pushing to `master` triggers the GitHub Pages build; there is no CI, test suite, or linter.

## Commands

```sh
bundle install                 # install gems from Gemfile.lock
bundle exec jekyll serve       # local preview at http://localhost:4000 (rebuilds on change)
bundle exec jekyll build       # build into _site/ (gitignored)
```

`_config.yml` changes are not picked up by `jekyll serve` auto-regeneration — restart the server.

## Architecture

- **Theme**: `jekyll-theme-slate` (gem-based). Local files override the theme: `_layouts/default.html` replaces the theme's default layout (adds `{% seo %}` from jekyll-seo-tag), and `assets/css/style.scss` imports `{{ site.theme }}` then applies site-specific CSS overrides.
- **Layouts**: `default` (page shell) ← `post` / `page`. Posts use `layout: post`.
- **Home page**: `index.html` lists posts via `paginator` (jekyll-paginate, `paginate: 5` in `_config.yml`). jekyll-paginate only works on `index.html`.
- **Feed**: `feed.xml` is a hand-written Liquid RSS template (not the jekyll-feed plugin).
- **Posts**: `_posts/YYYY-MM-DD-slug.markdown` with front matter `layout`, `title`, `date` (with `-0800` offset), `categories`, `tags`, `comments`. Images live in `images/` named with the post's date prefix.

## Dependencies

The `github-pages` umbrella gem was intentionally removed (it pinned a vulnerable rubyzip via jekyll-remote-theme). The Gemfile lists only what the site uses: Jekyll 3.10, slate theme, jekyll-paginate, kramdown-parser-gfm, plus `base64`/`bigdecimal`/`webrick` for Ruby 3.4+. Don't re-add `github-pages`. Most commits are Dependabot bumps to `Gemfile.lock`.
