# Technology Stack

## Framework & Core
- **Nuxt 4.0** - Vue.js meta-framework with SSR/SSG
- **Vue 3** with Composition API
- **TypeScript** for type safety
- **Nuxt UI Pro** - Premium component library

## Key Dependencies
- **@nuxt/content** - File-based CMS for docs/blog
- **@nuxt/image** - Optimized image handling
- **nuxt-og-image** - Dynamic OG image generation
- **@vueuse/nuxt** - Vue composition utilities
- **Zod** - Schema validation
- **better-sqlite3** - Database (SQLite)

## Package Management
- **pnpm** (v10.13.1) - Fast, disk space efficient package manager
- Uses pnpm workspaces and specific resolutions

## Development Tools
- **ESLint** with Nuxt config
- **TypeScript** strict mode
- **Vue TSC** for type checking

## Common Commands

### Development
```bash
pnpm dev          # Start dev server on localhost:3000
pnpm build        # Build for production
pnpm preview      # Preview production build locally
pnpm generate     # Generate static site
```

### Code Quality
```bash
pnpm lint         # Run ESLint
pnpm typecheck    # Run TypeScript checks
```

### Setup
```bash
pnpm install      # Install dependencies
pnpm postinstall  # Prepare Nuxt (runs automatically)
```

## Code Style
- ESLint with stylistic rules: comma dangle 'never', brace style '1tbs'
- TypeScript strict mode enabled
- Vue 3 Composition API preferred over Options API