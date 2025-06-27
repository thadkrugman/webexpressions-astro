# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Feedback Philosophy

**Be honest and direct with feedback.** When asked for opinions on design choices, code quality, or implementation decisions:
- Don't just agree or tell me what you think I want to hear
- It's okay to say something looks bad or suggest I'm making the wrong choice
- Provide genuine, constructive feedback even if it challenges my ideas
- I value honest assessment over polite agreement

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
- **Font hierarchy**: Black (900) for branding/logos, Bold (700) for headings, regular weights for content
- **Animation system**: Scroll-triggered animations using `.scroll-trigger` class and global Intersection Observer
- **Premium visual effects**: Custom shadows, white borders, and glass morphism effects for portfolio showcase
- **Responsive design**: Mobile-first with thoughtful scaling (logo sizes, text scaling, layout changes)

### Import Patterns
- Use TypeScript path aliases: `@/components/*`, `@/layouts/*`, etc.
- Page-specific components are organized in `pages/[page-name]/` directories
- Shared components go in `shared/` directory

## Current Design Patterns

### Portfolio Showcase Effects
- **White borders**: `border-6 border-white` for premium gallery look
- **Custom shadows**: Multi-layered shadows for depth (`box-shadow` with top and bottom shadows)
- **Hover interactions**: Scale and rotation resets on hover for engagement
- **Responsive scaling**: Different shadow intensities and border treatments per screen size

### Brand Logo Usage
- **Desktop CTA**: Large Layers2 icon with "webexpressions" text in font-black
- **Mobile CTA**: Small Layers2 icon only (`size-12 sm:size-14`) above content
- **Navbar**: Layers2 icon as primary brand mark
- **Consistent styling**: Always white/primary-foreground color

### Responsive Layout Patterns
- **Flexbox with shrink control**: Content divs use `flex-shrink-0`, logo areas use `flex-1`
- **Breakpoint strategy**: Mobile-first with `lg:` breakpoints for desktop layouts
- **Typography scaling**: Different font sizes per breakpoint with careful hierarchy

## Key Architectural Decisions

1. **No testing framework** - Add Vitest if implementing tests
2. **No linting/formatting** - Code style is manual but consistent
3. **Bun-based workflow** - All commands use `bun` instead of `npm`/`yarn`
4. **SEO-first approach** - Every page includes comprehensive meta tags and structured data
5. **Component composition** - Pages are built by composing purpose-built components
6. **Accessibility built-in** - Skip links, semantic HTML, and screen reader support
7. **Performance-focused** - Intersection Observer for animations, optimized builds via Astro
8. **Premium visual design** - Gallery-style portfolio with thick white borders, custom shadows, and glass effects
9. **Responsive CTA design** - Mobile uses stacked logo, desktop uses side-by-side with flex layouts
10. **Brand consistency** - Layers2 icon as primary logo, consistent Plus Jakarta Sans across all contexts

## Business Context

Professional web development services website showcasing:
- Three service tiers (Landing pages, Business websites, Custom applications)
- Portfolio and testimonials
- Direct client collaboration emphasis
- 100% satisfaction rate messaging