# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands

- `npm run dev` - Start development server on localhost:3000
- `npm run build` - Build production version
- `npm run start` - Start production server
- `npm run lint` - Run ESLint

## Architecture Overview

This is an Awwwards-inspired portfolio website built with Next.js 15, React 19, TypeScript, and Three.js. The site emphasizes smooth animations and 3D visual effects.

### Key Technologies & Frameworks

- **Next.js 15** with App Router (`app/` directory structure)
- **React 19** with TypeScript
- **GSAP** for animations with ScrollTrigger and ScrollToPlugin
- **Three.js** with React Three Fiber for 3D graphics
- **Tailwind CSS** with shadcn/ui components
- **Framer Motion** for additional animations

### Core Architecture Patterns

**Animation System:**
- `GsapProvider` (`components/gsap-provider.tsx`) - Registers GSAP plugins globally
- `TransitionProvider` (`components/transition-provider.tsx`) - Handles page transitions with GSAP
- `TransitionContext` (`context/transition-context.tsx`) - Context for triggering transitions
- Custom transition components use `useTransitionContext()` hook

**3D Graphics:**
- Three.js scenes in `components/project/` for individual project showcases
- Scene components: `cyberscape-scene.tsx`, `ethereal-scene.tsx`, `quantum-scene.tsx`
- Main `Scene` component (`components/scene.tsx`) for homepage 3D elements

**Styling System:**
- CSS variables for theming in `globals.css`
- Tailwind with custom color scheme (dark theme by default)
- shadcn/ui components in `components/ui/` 

### File Structure Conventions

- `app/` - Next.js App Router pages
- `components/` - Reusable React components
- `components/ui/` - shadcn/ui components
- `components/project/` - Project-specific 3D scenes and components
- `context/` - React contexts
- `hooks/` - Custom React hooks
- `lib/` - Utility functions and data

### Development Notes

- Uses `@/` path alias for imports (configured in `tsconfig.json`)
- Images are unoptimized in Next.js config for compatibility
- TypeScript and ESLint errors are ignored during builds for rapid development
- Uses `pnpm` as package manager (evidenced by `pnpm-lock.yaml`)