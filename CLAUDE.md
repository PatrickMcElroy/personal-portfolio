# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands

- **Development server**: `npm run dev` or `yarn dev` - Starts Next.js development server
- **Build**: `npm run build` or `yarn build` - Creates production build  
- **Start production**: `npm start` or `yarn start` - Runs production server
- **Lint**: `npm run lint` or `yarn lint` - Runs ESLint for code quality
- **Deploy**: `npm run deploy` - Builds and deploys to GitHub Pages via gh-pages

## Project Architecture

This is a personal portfolio website built with Next.js 12, React 18, and TailwindCSS. The architecture follows a component-based approach with data-driven content.

### Core Structure

- **Data-driven content**: Portfolio content is centralized in `data/portfolio.json`, making it easy to update personal information, projects, services, and resume details without touching code
- **Page-based routing**: Uses Next.js file-based routing with main pages in `pages/` directory
- **Component library**: Reusable UI components in `components/` directory following atomic design principles
- **Blog system**: Full CRUD blog functionality with markdown support using gray-matter and remark

### Key Components

- **Header/Footer**: Navigation and site structure
- **WorkCard**: Project showcase cards with external links
- **ServiceCard**: Skills/services display
- **BlogEditor**: In-browser blog post creation and editing
- **Cursor**: Custom cursor implementation (toggleable via `showCursor` in portfolio.json)
- **Theme system**: Dark/light mode via next-themes

### Data Management

- Portfolio data flows from `data/portfolio.json` through props to components
- Blog posts stored as markdown files in `_posts/` directory
- Static assets (images, PDFs) in `public/` directory
- API routes in `pages/api/` handle blog CRUD operations and portfolio data

### Styling Approach

- TailwindCSS with custom responsive breakpoints (mob, tablet, laptop, desktop, laptopl)
- Dark mode support via CSS classes
- GSAP animations for page transitions and scroll effects
- Custom CSS in `styles/globals.css` and `styles/markdown.css`

### Blog System Architecture

- Markdown files with frontmatter processed by gray-matter
- Dynamic routing via `[slug].js` for individual blog posts
- Admin interface at `/edit` for blog management
- API endpoints for creating, reading, updating, and deleting blog posts

## Configuration Notes

- Next.js 12 with React Strict Mode enabled
- ESLint with Next.js configuration
- TailwindCSS configured for component scanning
- Homepage deployment configured for GitHub Pages