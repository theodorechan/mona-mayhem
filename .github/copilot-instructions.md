# Copilot Instructions for Mona Mayhem

## Quick Reference

- **Framework**: Astro 6 with Node.js adapter
- **Language**: TypeScript (strict mode)
- **Type**: Workshop template + work-in-progress application

## Build & Run

```bash
npm install          # Install dependencies
npm run dev          # Start dev server (http://localhost:3000)
npm run build        # Build for production (generates dist/)
npm run preview      # Preview production build locally
npm run astro        # Run Astro CLI directly
```

## Project Structure

```
src/pages/
  ├── index.astro                    # Landing page (entry point, minimal)
  └── api/
      └── contributions/[username].ts # API endpoint for GitHub contribution data
public/
  └── favicon.svg
```

## Architecture Overview

**Mona Mayhem** is a GitHub Contribution Battle Arena — a retro arcade-themed web app that compares GitHub contribution graphs of two users.

### Data Flow

1. **Frontend** (`index.astro`): User inputs two GitHub usernames
2. **API** (`api/contributions/[username].ts`): Fetches contribution data from GitHub (endpoint format: `/api/contributions/username`)
3. **Display**: Renders arcade-style comparison

The API route uses `prerender = false` because it's dynamic and depends on request parameters.

## Key Conventions

### Astro File Structure

- `.astro` files use frontmatter (between `---` markers) for component logic
- HTML/JSX rendered below frontmatter
- API routes in `src/pages/api/` return `Response` objects
- Use `APIRoute` type for endpoints that need typed params

### TypeScript Configuration

- Strict mode enabled (`extends: "astro/tsconfigs/strict"`)
- Expect to declare types explicitly
- Type your component props and API responses

### GitHub Contribution API

- Endpoint format: `https://github.com/{username}.contribs` (mentioned in existing TODO)
- API response is typically SVG data for the contribution graph
- The `[username].ts` endpoint is a catch-all route parameterized by username

## Workshop Structure

This repo supports two parallel workshop tracks:

- **VS Code track**: Uses Chat, Plan Mode, Agent Mode
- **CLI track**: Uses `copilot` CLI with `@file`, `/plan`, `/delegate`, `/review`

Workshop guides are in `/workshop/` directory. When building features, refer to the relevant part:
- Part 02: API and page planning
- Part 03: Agentic implementation
- Part 04: Visual design
- Part 05: Polish and parallel work

## Design

- **Font**: Press Start 2P (retro arcade aesthetic)
- **Theme**: 1980s arcade game vibes
- Apply consistent styling across UI (check existing CSS patterns in components)

## Important Notes

- The app is **server-side rendered** (`output: 'server'` with Node.js adapter)
- Dynamic API routes require `prerender = false`
- This is a **workshop template** — the app is intentionally partially built for learning
- Many features will be TODO items; implementing them is part of the workshop flow
