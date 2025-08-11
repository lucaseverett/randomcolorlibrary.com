# Repository Guidelines

## Project Structure & Module Organization

- `src/pages/`: Route files (e.g., `index.astro`). URL = file path.
- `src/components/`: Reusable UI (use `PascalCase.astro`).
- `src/layouts/`: Page layouts and shared wrappers.
- `src/styles/`: Global styles (e.g., `global.css`). Tailwind is enabled via Vite.
- `src/assets/`: Source-managed assets imported by components.
- `public/`: Static files served at root (e.g., `/favicon.svg`).
- `dist/`: Build output (do not edit).
- Config: `astro.config.mjs`, `eslint.config.js`, `.prettierrc`, `tsconfig.json`.

## Build, Test, and Development Commands

- `npm run dev`: Start Astro dev server with hot reload.
- `npm run build`: Production build to `dist/`.
- `npm run preview`: Serve the built site locally from `dist/`.
- `npm run lint`: Lint Astro/JS/TS using ESLint.
- `npm run format`: Format code using Prettier (with Astro + import sorting).

## Coding Style & Naming Conventions

- **Formatting**: Prettier is the source of truth; run `npm run format` before PRs.
- **Linting**: Follow ESLint rules (Astro + a11y). Fix warnings or justify in PR.
- **Components**: `PascalCase.astro` for components; colocate helper files as needed.
- **Pages/Routes**: Kebab-case filenames in `src/pages/` (maps to URLs).
- **Imports**: Sorted by Prettier import plugin; avoid manual grouping.
- **CSS/Tailwind**: Prefer Tailwind utilities; keep global styles in `src/styles/global.css`.

## Testing Guidelines

- No test framework is configured yet. If adding tests, prefer Vitest for unit tests and place files as `*.test.ts` next to the source (or under `tests/`). Keep tests fast and deterministic.

## Commit & Pull Request Guidelines

- **Commits**: Use clear, purpose-driven messages. Conventional Commits are recommended, e.g., `feat: add color picker`, `fix: correct contrast on buttons`.
- **Branches**: `feat/…`, `fix/…`, `chore/…`, `docs/…`.
- **PRs**: Include a concise description, linked issues, and screenshots for UI changes. Ensure `npm run lint`, `npm run format`, and `npm run build` pass.

## Security & Configuration Tips

- Do not commit secrets; anything in `public/` is world-visible.
- This project uses ESM (`"type": "module"`). Prefer modern imports and avoid Node-only APIs in client code.
