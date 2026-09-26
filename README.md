# Sajeevan Lab — GitHub Pages Website

This repository contains the GitHub Pages website for **Sajeevan Lab** at the
Srinivasa Ramanujan Institute for Basic Sciences (SRIBS), Kerala.

## Repository

`https://github.com/SajeevanLab/SajeevanLab.github.io`

## Live website

`https://sajeevanlab.github.io/`

## Structure

```text
.
├── _config.yml
├── _data/
│   └── publications.yml
├── _layouts/
│   └── default.html
├── _posts/
├── about.md
├── contact.md
├── index.md
├── news.md
├── opportunities.md
├── people.md
├── projects.md
├── publications.md
├── repositories.md
├── research.md
├── 404.html
├── robots.txt
├── sitemap.xml
└── assets/
    ├── css/
    │   └── style.scss
    └── images/
        └── sajeevan-lab-mark.svg
```

## Updating the site

1. Edit the relevant `.md`, `.yml`, `.html`, or `.scss` file.
2. Commit the changes to the `main` branch.
3. GitHub Pages will rebuild the site automatically.

## Adding publications

Edit `_data/publications.yml`. Each publication can contain:

- `year`
- `title`
- `authors`
- `journal`
- `doi`
- `url`
- `categories`

The publication page automatically creates year sections and category filters.

## Adding news

For a quick update, edit `news.md`.

For a separate news article, add a Markdown file to `_posts/` using:

```text
YYYY-MM-DD-short-title.md
```

with Jekyll front matter:

```yaml
---
layout: default
title: "News title"
---
```

## Local preview

If Ruby and Bundler are installed:

```bash
bundle install
bundle exec jekyll serve
```

Then open:

`http://localhost:4000/`

## Content note

The initial publication list is a curated set of publicly verifiable works and is
intended to be expanded/updated from the lab's definitive publication record.
