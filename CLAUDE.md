# Portfolio Site - slyapustin.github.io

## Important
- This is a PUBLIC repository. Never commit secrets, credentials, or sensitive information.
- Deployed via GitHub Pages to slyapustin.com
- Git remote uses SSH: git@github.com:Slyapustin/slyapustin.github.io.git

## Blog Post Checklist

Every new blog post MUST include before deploying:

### HTML meta tags (all required):
- `og:type` (article)
- `og:title`
- `og:description` (100+ characters for LinkedIn)
- `og:image` (create OG screenshot — light theme, 1200x630)
- `og:url`
- `twitter:card` (summary_large_image)
- `twitter:image`
- `article:author` (Sergey Lyapustin)
- `article:published_time`
- `link rel="canonical"`
- `meta name="robots"` (index, follow)
- `meta name="author"`
- `meta name="description"`

### Update these files:
- `index.html` — add blog card to blog section
- `feed.xml` — add RSS item
- `sitemap.xml` — add URL
- Adjacent blog posts — update prev/next navigation links
- `llms.txt` — add post to blog list

### Quality checks:
- Lighthouse audit must score 100 on SEO, Accessibility, Best Practices
- SVG diagrams must work in light mode (add CSS overrides for hardcoded dark colors)
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
