# Project Structure

## Root Level
- `app/` - Main application code (Nuxt 3 app directory)
- `content/` - Content files for docs, blog, pricing (Nuxt Content)
- `public/` - Static assets served directly
- `node_modules/` - Dependencies
- Configuration files at root level

## App Directory (`app/`)
```
app/
├── app.config.ts      # App-level configuration (UI colors, etc.)
├── app.vue           # Root Vue component
├── assets/css/       # Stylesheets and CSS assets
├── components/       # Vue components
├── layouts/          # Page layouts
├── pages/            # File-based routing
├── types/            # TypeScript type definitions
└── error.vue         # Error page component
```

## Components Organization (`app/components/`)
- **App-level**: `AppHeader.vue`, `AppFooter.vue` - Global layout components
- **UI Components**: `LogoPro.vue`, `StarsBg.vue`, `ImagePlaceholder.vue`
- **Feature Components**: `PromotionalVideo.vue`, `TemplateMenu.vue`
- **Nested Folders**: 
  - `OgImage/` - OG image related components
  - `content/` - Content-specific components like `PictureAndText.vue`

## Pages Structure (`app/pages/`)
- File-based routing following Nuxt conventions
- Nested folders create nested routes
- `[slug].vue` for dynamic routes
- `[...slug].vue` for catch-all routes

## Content Structure (`content/`)
```
content/
├── 0.index.yml           # Homepage content
├── 1.docs/              # Documentation
│   ├── .navigation.yml   # Docs navigation
│   └── 1.getting-started/
├── 2.pricing.yml        # Pricing page content
├── 3.blog/              # Blog posts (markdown)
├── 3.blog.yml           # Blog page config
├── 4.changelog/         # Changelog entries
└── 4.changelog.yml      # Changelog page config
```

## Configuration Files
- `nuxt.config.ts` - Main Nuxt configuration
- `content.config.ts` - Content collections and schemas
- `app.config.ts` - App-level config (UI theme, colors)
- `package.json` - Dependencies and scripts
- `tsconfig.json` - TypeScript configuration
- `eslint.config.mjs` - ESLint rules

## Naming Conventions
- **Components**: PascalCase (e.g., `AppHeader.vue`, `LogoPro.vue`)
- **Pages**: kebab-case for files, follow Nuxt routing conventions
- **Content**: Numbered prefixes for ordering (e.g., `1.docs/`, `2.pricing.yml`)
- **Assets**: Organized by type in subfolders

## Content Management
- YAML files for structured content (pricing, homepage)
- Markdown files for long-form content (blog, docs, changelog)
- Zod schemas in `content.config.ts` define content structure
- Navigation files (`.navigation.yml`) control sidebar/menu structure