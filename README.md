# personal-website

Minimalist, editorial personal website and writing notebook for **Giovanni Schiavo** (physics student at University of Padova, developer & tech enthusiast).

Built with **[Astro](https://astro.build/)**, **pnpm**, and pure CSS. Zero bloated dependencies, 100% static HTML generation, responsive typography, and an obsidian dark aesthetic.

---

## Features

- **Who Am I**: Concise hero section highlighting physics studies at UniPD, software development, sourdough fermentation/cooking, photography, and personal finance.
- **Card-Grid Projects**: All software systems, simulations, and tools showcased directly on the landing page as interactive cards with status badges and tech stack tags.
- **Single-Page Complete Articles Feed (`/blog`)**: A continuous long-form stream rendering all articles in full prose in chronological order of posting, complete with a quick-jump table of contents and per-entry permalinks.
- **Headerless, Distraction-Free Layout**: Pure content-first design without top navigation clutter.
- **Aesthetic**: Refined, pure dark design system crafted with deep obsidian surfaces, subtle zinc borders, and warm monospace/serif accents.
- **RSS Feed**: Auto-generated standard RSS 2.0 feed at `/rss.xml`.
- **Content Collections**: Type-safe Markdown content layer configured via `src/content.config.ts`.

---

## Project Structure

```text
personal-website/
├── public/
│   └── favicon.svg           # Monogram SVG icon
├── src/
│   ├── components/
│   │   ├── Footer.astro       # Social links & copyright
│   │   └── ProjectCard.astro  # Interactive project card
│   ├── content/
│   │   └── blog/              # Markdown articles
│   ├── layouts/
│   │   └── BaseLayout.astro   # HTML skeleton, SEO & OpenGraph tags
│   ├── pages/
│   │   ├── index.astro        # Landing page (About + All Projects + Blog portal)
│   │   ├── blog/
│   │   │   ├── index.astro    # Single long-form feed loading all articles in full
│   │   │   └── [...slug].astro# Deep-link article reader
│   │   └── rss.xml.ts         # RSS feed endpoint
│   ├── styles/
│   │   └── global.css         # Dark design system
│   └── content.config.ts      # Astro content collections schema
├── astro.config.mjs
├── pnpm-lock.yaml
├── pnpm-workspace.yaml
└── package.json
```

---

## Development

```bash
# Install dependencies
pnpm install

# Start development server
pnpm dev

# Build production bundle
pnpm build

# Preview build locally
pnpm preview
```

---

## License

MIT © [Giovanni Schiavo](https://github.com/giovesch)
