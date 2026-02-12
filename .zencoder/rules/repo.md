---
description: Repository Information Overview
alwaysApply: true
---

# Portfolio Website Information

## Summary

A personal portfolio website built with React 19, TypeScript, and Vite. The project uses Motion (Framer Motion) for animations and features a modern dark-themed single-page application with smooth scrolling navigation between sections.

## Structure

- **src/**: Main source code directory containing React components and assets
  - **components/**: UI components organized by section and reusable UI elements
  - **assets/**: Static assets like images and icons
- **public/**: Static files served directly by the web server
- **.vscode/**: VS Code editor configuration

## Language & Runtime

**Language**: TypeScript
**Version**: TypeScript 5.9.3
**Build System**: Vite 7.1.7
**Package Manager**: npm

## Dependencies

**Main Dependencies**:

- React 19.1.1
- React DOM 19.1.1
- Motion 12.23.24 (Framer Motion)
- Lucide React 0.546.0 (Icon library)
- Reacharts 0.4.5 (Charting library)

**Development Dependencies**:

- TypeScript 5.9.3
- Vite 7.1.7
- ESLint 9.36.0
- @vitejs/plugin-react 5.0.4
- typescript-eslint 8.45.0

## Build & Installation

```bash
# Install dependencies
npm install

# Development server
npm run dev

# Production build
npm run build

# Preview production build
npm run preview

# Lint code
npm run lint
```

## UI Component Library

The project includes a comprehensive UI component library in `src/components/ui/` with ~45 reusable components including:

- Basic elements (button, input, checkbox)
- Layout components (card, dialog, drawer)
- Navigation elements (tabs, navigation-menu)
- Data display (table, chart)

The components use a utility-first styling approach with the `cn()` helper function that combines `clsx` and `tailwind-merge` for className composition.

## Styling System

- **CSS Variables**: Theme defined in `src/globals.css` with extensive CSS custom properties
- **Dark Mode**: Uses a `.dark` class variant system with OKLCH color space for perceptual uniformity
- **Component Styles**: Utility-based class naming convention
- **Responsive Design**: Mobile-first approach with responsive breakpoints

## Application Structure

The application follows a section-based architecture where `App.tsx` orchestrates the main layout:

- **Navigation**: Fixed navigation bar with scroll-based styling
- **HeroSection**: Landing/hero content
- **AboutSection**: About/bio information
- **SkillsSection**: Skills and technologies
- **ProjectsSection**: Portfolio projects
- **ContactSection**: Contact information and form
