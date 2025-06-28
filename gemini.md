# Project Documentation: webexpressions-astro

## Overview

This project is a web application built with the [Astro](https://astro.build/) framework. It uses [Tailwind CSS](https://tailwindcss.com/) for styling and is configured to be a static site. The project structure is typical for an Astro project, with a `src` directory containing all the source code, a `public` directory for static assets, and configuration files at the root.

## Project Structure

The project follows a standard Astro project structure:

```
/
├── public/
│   └── ... (static assets like images, fonts, etc.)
├── src/
│   ├── assets/
│   │   └── ... (images, svgs, etc.)
│   ├── components/
│   │   └── ... (reusable Astro components)
│   ├── constants/
│   │   └── ... (constant values used throughout the app)
│   ├── layouts/
│   │   └── Layout.astro (main layout component)
│   ├── lib/
│   │   └── ... (utility functions)
│   ├── pages/
│   │   └── ... (Astro pages, which correspond to routes)
│   └── styles/
│       └── global.css (global stylesheets)
├── .gitignore
├── astro.config.mjs
├── package.json
├── README.md
└── tsconfig.json
```

### Key Directories

*   `src/pages`: Contains the pages of the website. Each `.astro` file in this directory becomes a page on the site.
*   `src/components`: Contains reusable UI components that can be imported into pages and other components.
*   `src/layouts`: Defines the overall structure of pages.
*   `src/styles`: Contains global CSS styles.
*   `src/assets`: For storing assets like images and fonts that are processed by Astro.
*   `public`: For static assets that are not processed by Astro and are copied directly to the build output.

## Key Files

*   `astro.config.mjs`: The main configuration file for the Astro project. It's where you configure integrations, build options, and other settings. This project is configured to use Tailwind CSS.
*   `package.json`: Defines the project's metadata, dependencies, and scripts.
*   `tsconfig.json`: The TypeScript configuration file.

## Dependencies

The project uses the following key dependencies:

*   `astro`: The core Astro framework.
*   `tailwindcss`: A utility-first CSS framework for rapid UI development.
*   `@tailwindcss/vite`: A Vite plugin for Tailwind CSS.
*   `@lucide/astro`: A library of icons for Astro.
*   `clsx` & `tailwind-merge`: Utilities for combining and merging Tailwind CSS classes.

## Available Scripts

The following scripts are available in `package.json`:

*   `bun dev`: Starts the development server.
*   `bun build`: Builds the project for production.
*   `bun preview`: Previews the production build locally.
*   `bun astro`: Provides access to the Astro CLI.

## Getting Started

1.  **Install dependencies:**
    ```bash
    bun install
    ```
2.  **Start the development server:**
    ```bash
    bun dev
    ```
    This will start the development server at `http://localhost:4321`.

3.  **Build for production:**
    ```bash
    bun build
    ```
    This will create a `dist/` directory with the production-ready files.

## Component Architecture

This project follows a clear component-based architecture to promote reusability and maintainability.

-   **Page-Specific Components (`src/components/pages`)**: For each page in the `src/pages` directory (e.g., `index.astro`), there is a corresponding folder inside `src/components/pages` (e.g., `src/components/pages/home`). This folder holds the large, structural components that are only used on that specific page. This keeps the `pages/*.astro` files clean and focused on composing the overall page layout from these high-level components.

-   **Shared Components (`src/components/shared`)**: Components that are used across multiple pages, such as the `Navbar` and `Footer`, are placed in the `src/components/shared` directory. This avoids code duplication and ensures a consistent look and feel across the site.

-   **UI Components (`src/components/ui`)**: This directory contains small, general-purpose UI elements like `Button.astro`. These are the basic building blocks of the user interface and are designed to be highly reusable and configurable.

This structure makes it easy to find and modify components, and it provides a clear pattern for adding new pages and features. When building a new page, you should first create its larger, page-specific components in the `src/components/pages` directory and then compose them within the new route file in `src/pages`.

## File-by-File Breakdown

### Pages

The following pages are defined in `src/pages`:

*   `index.astro`: The home page.
*   `about.astro`: The about page.
*   `contact.astro`: The contact page.
*   `portfolio.astro`: The portfolio page.
*   `blog/index.astro`: The blog index page.
*   `blog/[slug].astro`: The dynamic blog post page.

### Components

The project is organized into the following component structure in `src/components`:

*   **`pages`**: Components that are specific to a particular page.
    *   **`home`**: Components used on the home page.
        *   `CTA.astro`: Call to action section.
        *   `Features.astro`: Features section.
        *   `Portfolio.astro`: Portfolio section.
        *   `Pricing.astro`: Pricing section.
        *   `Stats.astro`: Stats section.
        *   `hero/Hero.astro`: The main hero section.
        *   `hero/ProjectShowcase.astro`: A showcase of projects in the hero section.
        *   `testimonials/Card.astro`: A card for a testimonial.
        *   `testimonials/Testimonials.astro`: The testimonials section.
    *   **`portfolio`**: Components used on the portfolio page.
*   **`shared`**: Components that are used across multiple pages.
    *   `Container.astro`: A container component for layout.
    *   `Footer.astro`: The site footer.
    *   `Navbar.astro`: The site navigation bar.
*   **`ui`**: General-purpose UI components.
    *   `Button.astro`: A button component.
