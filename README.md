# keepyouroptions.com

Jekyll source for the Keep Your Options blog.

## Local preview

```
bundle install
bundle exec jekyll serve
```

Site will be available at http://localhost:4000

## Cloudflare Pages deployment settings

- **Framework preset:** Jekyll
- **Build command:** `bundle exec jekyll build`
- **Build output directory:** `_site`
- **Environment variable:** `RUBY_VERSION` = `3.2.2` (or your local Ruby version)

## Adding a new post

Add a file to `_posts/` named `YYYY-MM-DD-title.md` with front matter:

```
---
title: "Post Title"
date: YYYY-MM-DD
permalink: /YYYY/MM/title.html
categories: [finance, investing]
tags: [tag1, tag2]
---

Post body in Markdown.
```
