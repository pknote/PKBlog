# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Hexo blog site (赛博胖氪 - windowsplus.cn). It uses Hexo 8.x with a customized Chic theme.

## Common Commands

```bash
hexo clean        # Remove generated files and cache
hexo generate     # Generate static files (alias: g)
hexo server       # Start dev server at http://localhost:4000 (alias: s)
hexo deploy       # Deploy website (alias: d)
hexo new <title>  # Create new post
```

## Architecture

- **Hexo framework**: Static site generator with EJS templates, Marked renderer, Stylus CSS
- **Theme**: Chic (customized) at `themes/Chic/`
  - Layouts: `themes/Chic/layout/` (EJS templates)
  - Styles: `themes/Chic/source/css/` (Stylus)
  - Assets: `themes/Chic/source/` (images, js)
- **Content**: Blog posts in `source/_posts/` (166 posts, numbered 1-163+)
- **Images**: Local images in `source/images/` (WebP/GIF format)
- **SEO**: Implemented via `themes/Chic/layout/_partial/head.ejs` - canonical URLs, Open Graph, Twitter Cards, JSON-LD
- **Comments**: Waline (configured in theme `_config.yml`)
- **HTML compression**: `hexo-html-minifier` configured in root `_config.yml`

## Key Files

- `_config.yml` - Site-wide Hexo configuration
- `themes/Chic/_config.yml` - Theme configuration (Waline, MathJax, nav, links)
- `themes/Chic/layout/_partial/head.ejs` - SEO meta tags (edit for Open Graph/Twitter improvements)
- `themes/Chic/layout/_page/post.ejs` - Article page template with Waline comments

## Notes

- `public/` and `db.json` are gitignored
- Posts use front matter: `title`, `date`, `tags`, `categories`, `keywords`
- Image paths in posts: `/images/` for local images
- The site uses Chinese language (zh-CN)