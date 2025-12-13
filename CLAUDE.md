- SEMPRE use TODAS as regras que estão em @.cursor/rules:

- @.cursor/rules/general.mdc
- @.cursor/rules/typescript.mdc
# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Next.js 16 application called "aparatus" built with React 19, TypeScript, and Tailwind CSS 4. The project uses the App Router architecture and includes shadcn/ui components for the UI layer.

## Development Commands

- **Start dev server**: `npm run dev` (runs on http://localhost:3000)
- **Build**: `npm run build`
- **Start production**: `npm start`
- **Lint**: `npm run lint` (ESLint with Next.js config)
- **Format**: Prettier is configured with Tailwind plugin (`.prettierrc`)

## Architecture & Structure

### Project Layout
- `app/` - Next.js App Router pages and layouts (root layout uses Geist fonts)
- `components/ui/` - shadcn/ui components
- `lib/` - Utility functions (currently contains `cn()` helper for Tailwind class merging)
- `public/` - Static assets

### Path Aliases
The project uses `@/` alias mapping to the project root:
```typescript
"@/components" → components/
"@/lib/utils" → lib/utils
"@/hooks" → hooks/
```

### UI Component System
- **shadcn/ui**: Configured with "new-york" style, using Lucide icons
- **Components**: Located in `components/ui/`, use class-variance-authority (CVA) for variant management
- **Styling**: Components use `cn()` utility from `@/lib/utils` to merge Tailwind classes
- **Button component pattern**: Supports `asChild` prop via Radix Slot for composition
- **Variants**: Buttons include default, destructive, outline, secondary, ghost, link variants
- **Sizes**: Components support default, sm, lg, and icon-based sizes

### Styling Configuration
- **Tailwind CSS 4**: Uses new `@theme inline` syntax in `globals.css`
- **tw-animate-css**: Animation utilities included
- **Dark mode**: Custom variant with `@custom-variant dark (&:is(.dark *))`
- **Design tokens**: CSS variables for colors, fonts, and component theming
- **Prettier**: Auto-formats with tailwindcss plugin for class sorting

### TypeScript Configuration
- **Strict mode**: Enabled
- **Target**: ES2017
- **JSX**: react-jsx transform (React 19)
- **Module resolution**: bundler mode

### Code Quality
- **ESLint**: Next.js config + TypeScript rules + simple-import-sort plugin
- **Import sorting**: Enforced via `eslint-plugin-simple-import-sort` (error level)
  - Imports must be sorted alphabetically
  - Exports must be sorted alphabetically
- **Formatting**: Prettier with Tailwind class sorting

## Adding New UI Components

When adding shadcn/ui components, they will be installed to `components/ui/` and automatically configured to use the project's styling system and path aliases defined in `components.json`.
