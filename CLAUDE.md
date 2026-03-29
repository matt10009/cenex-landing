# Cenex Landing Site — cenex.ai

## Project
Static HTML site for Cenex AI Research, hosted on Vercel at cenex.ai. No framework — plain HTML/CSS/JS with inline styles.

## Structure
- `index.html` — Landing page (hero, terms, featured paper, pipeline, Snapback, about)
- `the-gradient-fallacy.html` — Full formatted paper
- `agreeable-dependency-loop.html` — ADL term definition page
- `half-life-thesis.html` — Half-Life thesis research preview
- `og-image.png` — Share image for social cards
- `og-generator.html` — Tool for generating OG images (not part of the site)

## Design System
- **Fonts**: IBM Plex Mono (UI/labels), Newsreader (body/headings)
- **Colors**: Dark (#0a0a0a bg), warm cream text (#e8e4df), red accent (#c4463a), soft red (#d4756c)
- **Pattern**: Noise overlay, scroll-reveal animations, mono labels with serif content
- **Clickable items**: Wrapped in `<a>` tags with `→` arrow affordance on hover and accent border highlight

## Deployment
- GitHub: github.com/matt10009/cenex-landing
- Vercel auto-deploys on push to main
- Domain: cenex.ai

## Adding New Pages
1. Copy the structure from `agreeable-dependency-loop.html` or `half-life-thesis.html`
2. Use the same CSS variables, topbar, and reveal animation pattern
3. Wrap corresponding cards/pipeline items on index.html in `<a>` tags — clickable styles apply automatically
4. Push to main — Vercel deploys automatically
