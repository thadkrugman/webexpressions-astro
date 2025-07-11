# webexpressions

A high-performance web development services website built with Astro, showcasing custom web development, mobile app development, and headless architecture services.

## About

webexpressions is the professional website for Thad Krugman, a web developer specializing in modern, high-performance digital solutions. The site features:

- **Portfolio showcase** - Featured projects including Rockwood Flooring, Spectre Corp, and more
- **Service offerings** - Custom web development, mobile apps, and headless architecture
- **Technical blog** - In-depth articles on web performance, Astro, responsive design, and TypeScript
- **Direct client collaboration** - Emphasizing 1-on-1 partnerships and 100% satisfaction rate

## Tech Stack

- **[Astro 5.11.0](https://astro.build/)** - Static site generator with islands architecture
- **[TypeScript](https://www.typescriptlang.org/)** - Type-safe development with path aliases
- **[Tailwind CSS 4.1.11](https://tailwindcss.com/)** - Utility-first CSS framework
- **[Bun](https://bun.sh/)** - Package manager and runtime
- **[MDX](https://mdxjs.com/)** - Markdown with JSX for blog content
- **[Lucide Astro](https://lucide.dev/)** - Beautiful icon library

## Project Structure

```
webexpressions-astro/
├── public/                    # Static assets (favicons, images, etc.)
├── src/
│   ├── assets/               # Processed assets (images)
│   ├── components/           # Reusable UI components
│   │   ├── pages/           # Page-specific components
│   │   │   ├── home/        # Homepage sections
│   │   │   ├── about/       # About page sections
│   │   │   ├── portfolio/   # Portfolio components
│   │   │   └── blog/        # Blog components
│   │   ├── shared/          # Cross-page components
│   │   └── ui/              # Base UI components
│   ├── constants/           # Static data and configuration
│   ├── content/             # MDX blog posts and config
│   ├── layouts/             # Page layouts
│   ├── lib/                 # Utility functions
│   ├── pages/               # File-based routing
│   └── styles/              # Global CSS
├── astro.config.mjs         # Astro configuration
├── package.json             # Dependencies and scripts
└── tsconfig.json            # TypeScript configuration
```

## Getting Started

### Prerequisites

- [Bun](https://bun.sh/) (recommended) or Node.js 18+

### Installation

1. **Clone the repository:**

   ```bash
   git clone <repository-url>
   cd webexpressions-astro
   ```

2. **Install dependencies:**

   ```bash
   bun install
   ```

3. **Start the development server:**

   ```bash
   bun dev
   ```

   The site will be available at `http://localhost:4321`

## Available Scripts

| Command         | Action                                              |
| :-------------- | :-------------------------------------------------- |
| `bun install`   | Install dependencies                                |
| `bun dev`       | Start development server at `localhost:4321`        |
| `bun build`     | Build production site to `./dist/`                  |
| `bun preview`   | Preview production build locally                    |
| `bun astro ...` | Run Astro CLI commands (`astro add`, `astro check`) |

## Component Architecture

The project follows a structured component organization:

- **Page Components** (`src/components/pages/`): Large, page-specific sections like Hero, Features, Portfolio
- **Shared Components** (`src/components/shared/`): Reusable across pages (Navbar, Footer, Container)
- **UI Components** (`src/components/ui/`): Base building blocks (Button, Badge, Input)

Pages are composed by importing and arranging these components in the `src/pages/` directory.

## Content Management

Blog posts are managed using Astro's Content Collections with MDX:

- **Location**: `src/content/blog/`
- **Format**: MDX (Markdown + JSX)
- **Schema**: Type-safe frontmatter with Zod validation
- **Features**: Syntax highlighting, component embedding, SEO metadata

## Key Features

- **Islands Architecture**: Zero JavaScript by default, selective hydration
- **Performance Optimized**: Lighthouse scores of 95+ across all metrics
- **SEO Ready**: Comprehensive meta tags, Open Graph, and structured data
- **Responsive Design**: Mobile-first approach with modern CSS techniques
- **Type Safety**: Full TypeScript support with path aliases (`@/*`)
- **Modern Styling**: Tailwind CSS with custom design system

## Deployment

The site is optimized for deployment on modern hosting platforms:

- **Vercel** (recommended): Zero-config deployment
- **Netlify**: Static site hosting
- **Cloudflare Pages**: Edge deployment

Build the site for production:

```bash
bun build
```

The built site will be in the `./dist/` directory.

## Development Guidelines

- Use TypeScript for all new code
- Follow the established component organization patterns
- Optimize images and assets for web performance
- Write semantic HTML with accessibility in mind
- Test across different devices and browsers

## Contact

For questions about this project or web development services:

- **Website**: [webexpressions.com](https://webexpressions.com)
- **Email**: Contact through the website
- **Location**: Cleveland, Ohio
