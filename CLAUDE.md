# Cenex Landing Site — cenex.ai

## Project
Static HTML site for Cenex AI Research, hosted on Vercel at cenex.ai. No framework — plain HTML/CSS/JS with inline styles.

## Structure
- `index.html` — Landing page (hero, terms, featured paper, pipeline, email capture, Snapback, about)
- `the-gradient-fallacy.html` — Full formatted paper
- `agreeable-dependency-loop.html` — ADL term definition page
- `friction-starvation.html` — Friction Starvation term definition page
- `capability-correlated-agreeableness.html` — CCA term definition page
- `half-life-thesis.html` — Half-Life thesis research preview
- `child-brain-thesis.html` — Full Child Brain Thesis paper
- `blog/index.html` — Blog listing page
- `blog/trust-surface-vs-trust-infrastructure.html` — First blog post (OpenClaw / trust surface analysis)
- `snapback.html` — Snapback product page (deeper than landing section)
- `snapback/` — Snapback screenshots and app icon
- `404.html` — Branded 404 page
- `favicon.svg` — Site favicon (C with red accent dot)
- `og-image.png` — Share image for social cards
- `robots.txt` — Crawler directives + sitemap pointer
- `sitemap.xml` — All pages with lastmod dates (update when adding pages)
- `og-generator.html` — Tool for generating OG images (not part of the site)

## Design System
- **Fonts**: IBM Plex Mono (UI/labels), Newsreader (body/headings)
- **Colors**: Dark (#0a0a0a bg), warm cream text (#e8e4df), red accent (#c4463a), soft red (#d4756c)
- **Pattern**: Noise overlay, scroll-reveal animations, mono labels with serif content
- **Clickable items**: Wrapped in `<a>` tags with `→` arrow affordance on hover and accent border highlight
- **Topbar**: Consistent across all subpages — `Cenex.` logo left, `← Back to research` right

## SEO
- All pages have: meta description, OG tags, Twitter card tags, canonical URL, favicon
- index.html has JSON-LD structured data (ResearchOrganization)
- Vercel Analytics enabled on all pages (`/_vercel/insights/script.js`)
- Google Search Console verified and sitemap submitted

## Email
- Google Workspace: matt@cenex.ai, hello@cenex.ai
- DNS: MX + SPF + DKIM + DMARC all configured via Vercel DNS
- Buttondown newsletter (username: cenex) — form on landing page, uses hello@cenex.ai

## Deployment
- GitHub: github.com/matt10009/cenex-landing
- Vercel auto-deploys on push to main
- Domain: cenex.ai

## Adding Blog Posts
1. Copy from `blog/trust-surface-vs-trust-infrastructure.html` as template
2. Use `post-label`, `post-date`, `post-section` classes — same design system as papers but with `Blog` label
3. Topbar links back to `../blog/` (not research). Footer has "All Posts" + "Research Home"
4. Internal links to existing pages use `../` relative paths (e.g., `../friction-starvation.html`)
5. Add a new `<a class="post-item">` entry to `blog/index.html` (newest first)
6. Add SEO meta tags, canonical URL, Vercel Analytics script
7. Update `sitemap.xml` with the new post URL

## Adding New Pages
1. For full papers, copy from `the-gradient-fallacy.html` or `child-brain-thesis.html`. For shorter term pages, copy from `friction-starvation.html` or `capability-correlated-agreeableness.html`
2. Use the same CSS variables, topbar (Cenex. logo + back link), and reveal animation pattern
3. Add SEO meta tags: description, OG, Twitter card, canonical URL, favicon link
4. Add `<script defer src="/_vercel/insights/script.js"></script>` before `</body>`
5. Wrap corresponding cards/pipeline items on index.html in `<a>` tags — clickable styles apply automatically
6. Update `sitemap.xml` with the new page URL and lastmod date
7. Push to main — Vercel deploys automatically
