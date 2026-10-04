# personal-website

Minimalist, editorial personal website and writing notebook for **Giovanni Schiavo** (physics student at University of Padova, developer & tech enthusiast).

Built with **[Astro](https://astro.build/)** and pure CSS. Zero bloated dependencies, 100% static HTML generation, responsive typography, and anti-flicker dark/light mode.

---

## Features

- **Who Am I**: Concise hero section highlighting physics studies at UniPD, software development, sourdough fermentation/cooking, photography, and personal finance.
- **Highlighted Projects**: Clean card grid with status badges, tech stack tags, and external/internal routing.
- **Single-Thread Blog**: Continuous chronological stream layout (`/blog`) with dynamic tag filtering and dedicated deep-dive article reading pages (`/blog/[slug]`).
- **Typography & Theme System**: Warm editorial palette for light mode and obsidian slate for dark mode, with zero-layout-shift client switcher.
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
│   │   ├── Header.astro       # Nav links & dark/light switcher
│   │   ├── Footer.astro       # Social links & copyright
│   │   ├── ProjectCard.astro  # Interactive project card
│   │   └── ThemeScript.astro  # Inline anti-FOUC theme script
│   ├── content/
│   │   └── blog/              # Markdown articles
│   ├── layouts/
│   │   └── BaseLayout.astro   # HTML skeleton, SEO & OpenGraph tags
│   ├── pages/
│   │   ├── index.astro        # Landing page (About + Projects + Recent Thread)
│   │   ├── blog/
│   │   │   ├── index.astro    # Single-thread chronological stream
│   │   │   └── [...slug].astro# Article reader
│   │   ├── projects/
│   │   │   └── index.astro    # Dedicated project showcase
│   │   └── rss.xml.ts         # RSS feed endpoint
│   ├── styles/
│   │   └── global.css         # Minimalist responsive design system
│   └── content.config.ts      # Astro content collections schema
├── astro.config.mjs
└── package.json
```

---

## Development

```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Build production bundle
npm run build

# Preview build locally
npm run preview
```

---

## License

MIT © [Giovanni Schiavo](https://github.com/giovesch)
