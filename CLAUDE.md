# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a personal portfolio website built with React, TypeScript, and Vite. It showcases projects, skills, and contact information with smooth animations and a dark theme.

## Development Commands

```bash
# Install dependencies
npm install

# Start development server (usually runs on http://localhost:5173)
npm run dev

# Build for production
npm run build

# Preview production build locally
npm run preview
```

## Architecture

### Tech Stack
- **Framework**: React 18 with TypeScript
- **Build Tool**: Vite
- **Styling**: Tailwind CSS v4 (new PostCSS-based architecture)
- **UI Components**: Shadcn/ui (built on Radix UI primitives)
- **Animations**: Framer Motion
- **Form Handling**: React Hook Form with Zod validation
- **Icons**: Lucide React

### Project Structure

**Root-level files:**
- `index.html` - Entry HTML file that loads `main.tsx`
- `main.tsx` - Application entry point, renders `<App />`
- `App.tsx` - Main component that composes all sections

**Components organization:**
- `components/` - Main section components (HeroSection, AboutSection, SkillsSection, ProjectsSection, ContactSection, Navigation)
- `components/ui/` - Reusable shadcn/ui components (button, card, dialog, etc.)
- `components/figma/` - Custom components (ImageWithFallback)
- `components/styles/globals.css` - Global styles and Tailwind configuration

**Key architectural patterns:**
- Single-page application with section-based layout
- Component composition with shadcn/ui primitives
- Dark theme with CSS custom properties
- Framer Motion for scroll-based animations using `whileInView`

### Styling System

**Tailwind CSS v4:**
- Uses new `@import "tailwindcss"` syntax in globals.css
- Custom CSS variables for theming (--background, --foreground, --primary, etc.)
- Dark mode implemented via `.dark` class with CSS custom properties
- Custom variant: `@custom-variant dark (&:is(.dark *))`

**Color system:**
- Uses OKLCH color format for better color consistency
- Theme tokens defined in `:root` and `.dark` selectors
- Design tokens include chart colors, sidebar colors, and semantic colors

### Path Aliases

The project uses `@/*` as a path alias pointing to the root directory:
```typescript
import { Button } from '@/components/ui/button'
import { Card } from '@/components/ui/card'
```

## Deployment

**GitHub Actions:**
- Automatic deployment to SiteGround via FTP on push to `main` branch
- Workflow file: `.github/workflows/deploy.yml`
- Requires secrets: `FTP_SERVER`, `FTP_USERNAME`, `FTP_PASSWORD`

**Vercel:**
- Also configured for Vercel deployment (vercel.json)
- Build command: `npm run build`
- Output directory: `dist`

## Adding New UI Components

The project uses shadcn/ui components. All UI components are in `components/ui/` and follow shadcn conventions:
- Built on Radix UI primitives
- Styled with Tailwind CSS
- Use class-variance-authority (cva) for variant management
- Utilize cn() utility (clsx + tailwind-merge) for className merging

When adding new section components, follow the existing pattern:
1. Create component in `components/` directory
2. Use Framer Motion for animations with `whileInView` for scroll triggers
3. Import and add to `App.tsx`
4. Use semantic HTML with proper sections and headings

## TypeScript Configuration

- Strict mode enabled
- ES2020 target
- Bundler module resolution (Vite)
- Unused locals and parameters are flagged
- Path aliases configured for @ imports
