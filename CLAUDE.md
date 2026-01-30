# CLAUDE.md

## Project Overview

This is a personal portfolio website for Juan Ramirez, designed to showcase developer skills to recruiters and potential contacts. The site is deployed as a GitHub Pages site at juanramirezc2.github.io.

## Tech Stack

- **Framework:** Svelte 4
- **Build Tool:** Vite 5
- **Language:** TypeScript
- **Package Manager:** yarn (always use yarn for dependency management)

## Commands

```bash
yarn dev      # Start development server
yarn build    # Build for production
yarn preview  # Preview production build
yarn check    # Run svelte-check for type validation
```

## Project Structure

```
src/
├── App.svelte                 # Main app component with fullpage layout
├── main.ts                    # Entry point
├── lib/
│   └── components/
│       ├── FullpageContainer.svelte  # CSS scroll-snap container
│       ├── FullpageSection.svelte    # Individual section wrapper
│       ├── Header.svelte             # Fixed navigation header
│       ├── Hero.svelte               # Landing/intro section
│       ├── About.svelte              # About me section
│       ├── Skills.svelte             # Technical skills section
│       ├── Contact.svelte            # Contact information section
│       └── ParticlesBackground.svelte # Animated particle background
```

## Architecture

### Fullpage Scroll System

The site uses native CSS scroll-snap for fullpage scrolling (no external library):

- `FullpageContainer.svelte`: Main scrollable container with `scroll-snap-type: y mandatory`. Uses IntersectionObserver to detect the active section and dispatches `change` events.
- `FullpageSection.svelte`: Section wrapper with `scroll-snap-align: start`. Registers with parent container via Svelte context.
- Navigation uses `fullpage:goto` custom window events to scroll to specific sections.

### Section Navigation

Header dispatches `window` events with `fullpage:goto` containing the section index. The FullpageContainer listens for these events and scrolls to the target section using `scrollIntoView()`.

## Styling

- CSS variables for theming (defined in global styles)
- Supports light/dark mode via `prefers-color-scheme`
- Mobile-responsive design
- Background uses tsparticles for animated effect

## Deployment

The site builds to `dist/` and deploys to GitHub Pages. The CNAME file configures the custom domain.
