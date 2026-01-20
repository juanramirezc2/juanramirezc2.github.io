# juangramirez.me

Personal website built with Vite + Svelte + TypeScript.

## Development

```bash
# Install dependencies
yarn install

# Start dev server
yarn dev

# Type check
yarn run check

# Build for production
yarn build

# Preview production build
yarn preview
```

## Project Structure

```
src/
├── lib/
│   └── components/
│       ├── Header.svelte
│       ├── Hero.svelte
│       ├── About.svelte
│       ├── Skills.svelte
│       └── Contact.svelte
├── App.svelte
├── app.css
└── main.ts
```

## Deployment

Pushes to `main` automatically deploy to GitHub Pages via GitHub Actions.

## Theme

Automatically respects system dark/light mode preference via CSS `prefers-color-scheme`.
