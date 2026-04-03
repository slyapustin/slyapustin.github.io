# Portfolio Site - slyapustin.github.io

## Important
- This is a PUBLIC repository. Never commit secrets, credentials, or sensitive information.
- Deployed via GitHub Pages to slyapustin.com (Jekyll 3.10, auto-built on push)
- Git remote uses SSH: git@github.com:Slyapustin/slyapustin.github.io.git

## Local Development
```
export PATH="/usr/local/opt/ruby@3.3/bin:/usr/local/lib/ruby/gems/3.3.0/bin:$PATH"
bundle exec jekyll serve --port 4001
```
Site runs at http://localhost:4001. Uses Ruby 3.3 + `github-pages` gem (Jekyll 3.10).

## Jekyll Structure
- `_posts/` — blog posts as `.html` files with YAML frontmatter (NOT markdown)
- `_layouts/post.html` — shared post template (nav, CSS, footer, related posts, scripts)
- `_includes/` — CSS partials, nav, theme toggle, article footer, related posts, scripts
- `_includes/css/` — variables, base, nav-post, article, related-posts, diagram, responsive
- `index.html` — homepage with Liquid loop for blog cards
- `feed.xml`, `sitemap.xml`, `llms.txt` — auto-generated from posts via Liquid templates

## Blog Post Checklist

To add a new post, create ONE file: `_posts/YYYY-MM-DD-slug.html`

### Required frontmatter:
```yaml
---
layout: post
title: "Full Title"
title_html: "Title with <em>Accent Part</em>"
date: YYYY-MM-DD
description: "100+ chars for LinkedIn"
og_image: /blog/og-filename.jpg
tags: [Tag1, Tag2, Tag3]
read_time: N
card_title: "Shorter title for homepage cards"
card_excerpt: "1-2 sentence excerpt for homepage cards"
has_diagrams: true/false
related:
  - slug-of-related-post-1
  - slug-of-related-post-2
  - slug-of-related-post-3
---
```
Optional: `preload_image: /blog/image.webp` for LCP optimization.

### What's auto-generated (no manual editing needed):
- Homepage blog card (from frontmatter)
- RSS feed entry
- Sitemap entry
- llms.txt entry
- Prev/next navigation
- Related posts section
- JSON-LD structured data
- All meta tags (OG, Twitter, canonical, robots, author)
- Heading anchor icons (via shared JS)

### Still manual:
- Create OG image (light theme, 1200x630)
- Write the article body HTML (goes after frontmatter)
- Add `id` attributes to h2/h3 headings for anchor links
- Add chain-link SVG anchor icon to each h2/h3: `<a href="#slug" class="anchor-icon" aria-label="Link to section"><svg ...></a>`

### Quality checks:
- Lighthouse audit must score 100 on SEO, Accessibility, Best Practices
- SVG diagrams must work in light mode (shared overrides in `_includes/css/diagram.html`)
- OG image must render in LinkedIn post inspector
- No em dash replacement in CSS or HTML attributes (only in article body text)

## Design
- Apple system fonts (-apple-system, SF Pro) — no Google Fonts
- No blinking/pulsing animations
- Single adaptive favicon.svg with CSS prefers-color-scheme
- Dark/light theme with system detection

## Do not commit
- screenshot-*.png
- *-post.txt (social media drafts)
- .DS_Store
- _site/
- Gemfile.lock
- tmp/
