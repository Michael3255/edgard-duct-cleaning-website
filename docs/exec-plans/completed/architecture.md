# Plan: Architecture

- **Status:** completed
- **Doc:** [architecture.md](../../architecture.md)
- **Audience:** developers new to the codebase
- **Completed:** 2026-10-27

## Goal
A new developer can find where any part of the site lives and understands how source files become the deployed site.

## Outline
1. Overview and stack
2. Project structure
3. Build flow (source to `dist/`)
4. Page layout, section by section
5. Components and layout props

## Verify against
- `package.json`, `astro.config.mjs`, `tailwind.config.mjs`
- `src/pages/index.astro`, `src/layouts/BaseLayout.astro`, `src/components/CallBar.astro`

## Steps
1. Expand each outline section from the current draft.
2. Add a build-flow diagram.
3. Add a props table for the layout.
4. Check every path and name against the files above.

## Done when
- [x] Every file path and config key named in the doc exists
- [x] Page sections match `index.astro` in order
- [x] Build flow matches what `npm run build` produces
