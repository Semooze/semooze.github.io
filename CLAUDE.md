# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Structure

This is a Hugo static site hosted on Cloudflare Pages. The Hugo site lives inside the `gosem-log/` subdirectory, not the repo root.

- `gosem-log/` — Hugo site root
  - `hugo.toml` — site config (baseURL, theme, locale)
  - `content/posts/` — blog posts in Markdown
  - `static/` — static assets served as-is
  - `themes/PaperMod/` — PaperMod theme (git submodule)
  - `public/` — build output (not committed)
- `.github/workflows/hugo.yml` — GitHub Actions workflow (deploys to `docs/` on master)

## Local Development

All Hugo commands must be run from inside `gosem-log/`:

```bash
cd gosem-log
hugo server          # local dev server at http://localhost:1313
hugo server -D       # include draft posts
hugo --minify        # build to gosem-log/public/
```

## Deployment

**Cloudflare Pages** auto-deploys on push to master.
- Build command: `hugo --minify`
- Root directory: `gosem-log`
- Output directory: `public`
- Live site: `https://gosem-blog.pages.dev`

## Content

Posts use TOML or YAML front matter. Set `draft = false` to publish:

```toml
+++
title = 'Post Title'
date = 2026-01-01T00:00:00+07:00
draft = false
+++
```

## Theme

PaperMod is a git submodule at `gosem-log/themes/PaperMod`. When cloning, use:

```bash
git clone --recurse-submodules
# or after cloning:
git submodule update --init --recursive
```
