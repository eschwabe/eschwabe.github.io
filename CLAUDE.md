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

- **Theme**: hand-written, no gem theme. `_layouts/default.html` is the page shell (`{% seo %}`, header/footer includes, an inline pre-paint script that applies the saved light/dark choice). `assets/css/style.scss` imports partials from `_sass/` (`_tokens` holds all colors/type/spacing as CSS custom properties, redefined for dark mode). Sass is the old Ruby Sass converter from Jekyll 3.10: use `@import`, no `@use`, no native CSS nesting, and avoid bare `min()`/`max()` (Sass functions).
- **Layouts**: `default` ← `home` / `post` / `page`. Posts get `layout: post` and `comments: true` from `defaults` in `_config.yml`.
- **Home page**: `index.html` (`layout: home`) — its body is the hero bio; projects come from `_data/projects.yml`; shows the 3 most recent posts.
- **Blog index**: `blog/index.html` lists all posts grouped by year. No pagination.
- **Includes**: `header`, `footer`, `social-links` (inline SVG icons), `post-list`, `theme-toggle`, `giscus`.
- **Comments**: giscus (GitHub Discussions). Renders only when `giscus.repo_id` and `giscus.category_id` are set in `_config.yml`.
- **Feed**: `feed.xml` is a hand-written Liquid RSS template (not the jekyll-feed plugin). `jekyll-sitemap` generates `sitemap.xml` and `robots.txt`.
- **Posts**: `_posts/YYYY-MM-DD-slug.markdown` with front matter `title`, `date` (with `-0800` offset), `categories`, `tags`. Images live in `images/` named with the post's date prefix.

## Dependencies

The `github-pages` umbrella gem was intentionally removed (it pinned a vulnerable rubyzip via jekyll-remote-theme). The Gemfile lists only what the site uses: Jekyll 3.10, jekyll-seo-tag, jekyll-sitemap, kramdown-parser-gfm, plus `base64`/`bigdecimal`/`webrick` for Ruby 3.4+. Don't re-add `github-pages`. Most commits are Dependabot bumps to `Gemfile.lock`.
