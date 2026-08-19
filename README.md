# keepyouroptions.com

Jekyll source for the Keep Your Options blog.

## Local preview

```
bundle install
bundle exec jekyll serve
```

Site will be available at http://localhost:4000

## Cloudflare Workers Builds deployment settings

This site deploys via **Cloudflare Workers Builds** (not the classic Pages dashboard —
there's no "Framework preset" dropdown here). Configuration lives in `wrangler.jsonc`
and `package.json` rather than dashboard env vars.

- **Build command** (dashboard → Settings → Build): `bundle exec jekyll build`
- **Deploy command**: `npx wrangler deploy`
- **Output directory**: `_site` (must match `assets.directory` in `wrangler.jsonc`)
- Ruby/Node versions are auto-detected from the build environment; no `RUBY_VERSION`
  env var needed
- Both `keepyouroptions.com` and `www.keepyouroptions.com` are declared under
  `routes` in `wrangler.jsonc` with `"custom_domain": true` — adding them through
  the dashboard's domain UI directly has been unreliable for the `www` host

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
