# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands

This project uses **Bun** as the package manager and runtime.

```bash
bun install        # Install dependencies
bun dev           # Start development server at localhost:4321
bun build         # Build production site to ./dist/
bun preview       # Preview production build locally
bun astro ...     # Run Astro CLI commands (e.g., bun astro check)
```

## Technology Stack

- **Astro 5.9.4** - Main framework for static site generation
- **TypeScript** - Strict configuration with path aliases (`@/*` → `./src/*`)
- **TailwindCSS 4.1.10** - Utility-first CSS framework with Vite plugin
- **Bun** - Package manager and runtime

## Code Architecture

### Component Organization Pattern
```
src/components/
├── pages/home/          # Page-specific components (Hero, CTA, Features, etc.)
├── shared/              # Reusable components (Navbar, Footer, Container)
└── ui/                  # Base UI components (Button)
```

### Page Composition Pattern
Pages are composed by importing and arranging page-specific components in order:
```astro
<Layout {...seo}>
  <Hero />
  <Stats />
  <Features />
  <Portfolio />
  <Pricing />
  <Testimonials />
  <CTA />
</Layout>
```

### SEO Configuration Pattern
Each page defines a `seo` object with title, description, Open Graph, and keywords that gets spread into the Layout component.

### Layout System
- Main layout (`src/layouts/Layout.astro`) handles all SEO meta tags, structured data, and global features
- Includes comprehensive Open Graph, Twitter Cards, and Schema.org business markup
- Built-in accessibility features (skip links, semantic HTML)
- Global scroll animations via Intersection Observer

### Styling Architecture
- **Primary utility**: `cn()` function in `src/lib/utils.ts` for conditional class merging using `clsx` and `tailwind-merge`
- **Global styles**: `src/styles/global.css` with TailwindCSS configuration
- **Font**: Plus Jakarta Sans Variable loaded via Fontsource
- **Animation system**: Scroll-triggered animations using `.scroll-trigger` class and global Intersection Observer

### Import Patterns
- Use TypeScript path aliases: `@/components/*`, `@/layouts/*`, etc.
- Page-specific components are organized in `pages/[page-name]/` directories
- Shared components go in `shared/` directory

## Key Architectural Decisions

1. **No testing framework** - Add Vitest if implementing tests
2. **No linting/formatting** - Code style is manual but consistent
3. **Bun-based workflow** - All commands use `bun` instead of `npm`/`yarn`
4. **SEO-first approach** - Every page includes comprehensive meta tags and structured data
5. **Component composition** - Pages are built by composing purpose-built components
6. **Accessibility built-in** - Skip links, semantic HTML, and screen reader support
7. **Performance-focused** - Intersection Observer for animations, optimized builds via Astro

## Business Context

Professional web development services website showcasing:
- Three service tiers (Landing pages, Business websites, Custom applications)
- Portfolio and testimonials
- Direct client collaboration emphasis
- 100% satisfaction rate messaging