# Plan: Design decisions

- **Status:** completed
- **Doc:** [design-decisions.md](../../design-decisions.md)
- **Audience:** developers and reviewers who want to know why the site is built this way
- **Completed:** 2026-10-27

## Goal
Each significant choice is recorded with its context, the decision and its consequences, so it can be revisited later.

## Outline
One short entry per decision, numbered:
1. Static site with no backend
2. Mobile-first with a sticky call bar
3. System font stack
4. Brand palette in the Tailwind config
5. Structured data for local search

## Verify against
- `astro.config.mjs`, `tailwind.config.mjs`
- `src/components/CallBar.astro`, `src/layouts/BaseLayout.astro`

## Steps
1. Convert the draft notes into context / decision / consequences entries.
2. Remove the "next steps" list (it is not a decision).
3. Check each claim against the files above.

## Done when
- [x] Every entry has context, decision and consequences
- [x] Every claim matches the code
