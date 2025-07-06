# Tailwind CSS 3.x Benchmark App

This is a synthetic benchmark application built with Tailwind CSS 3.x to test migration tools for upgrading to Tailwind CSS 4.x.

## Breaking Changes Demonstrated

This app specifically includes the following Tailwind CSS 3.x features that will break in v4:

### 1. Package Dependencies
- `tailwindcss` (v3.x)
- `postcss-import` (removed in v4)
- `autoprefixer` (removed in v4)

### 2. PostCSS Configuration
- Uses `tailwindcss` plugin instead of `@tailwindcss/postcss`
- Includes `postcss-import` and `autoprefixer` plugins

### 3. CSS Import Directives
- `@tailwind base;`
- `@tailwind components;`
- `@tailwind utilities;`
- Custom `@layer` definitions

### 4. Opacity Utilities (Need Migration)
- `bg-opacity-*` → `bg-*/opacity`
- `text-opacity-*` → `text-*/opacity`
- `border-opacity-*` → `border-*/opacity`

### 5. Gradient Utilities
- `bg-gradient-to-*` → `bg-linear-to-*`
- `bg-gradient-to-r`, `bg-gradient-to-br`, etc.

### 6. Deprecated Utility Classes
- `flex-shrink-*` → `shrink-*`
- `flex-grow-*` → `grow-*`
- `overflow-ellipsis` → `text-ellipsis`
- `decoration-*` → `box-decoration-*`

### 7. JavaScript-based Configuration
- `tailwind.config.js` with theme objects
- `darkMode: 'class'` configuration
- Custom `addUtilities` plugin functions

### 8. Transition Properties
- `transition-transform` (needs expansion in v4)

## Setup and Usage

1. Install dependencies:
```bash
npm install
```

2. Build the CSS:
```bash
npm run build
```

3. Start development server:
```bash
npm run dev
```

4. View the app at `http://localhost:8080`

## Migration Testing

Use this app to test your Tailwind CSS 3.x to 4.x migration tool. The app should continue to work and look the same after migration, but with updated syntax and dependencies.

## Files Structure

- `package.json` - Dependencies that need updating
- `postcss.config.js` - PostCSS configuration to migrate
- `tailwind.config.js` - JavaScript config to convert to CSS
- `src/styles.css` - CSS with @tailwind directives and @layer
- `index.html` - HTML with various deprecated utilities
- `dist/` - Compiled CSS output