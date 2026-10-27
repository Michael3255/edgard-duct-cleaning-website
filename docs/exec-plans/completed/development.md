# Plan: Development guide

- **Status:** completed
- **Doc:** [development.md](../../development.md)
- **Audience:** developers setting up the project locally
- **Completed:** 2026-10-27

## Goal
A developer can clone the repo, run the site locally and produce a production build without asking anyone.

## Outline
1. Requirements
2. Setup
3. Scripts
4. Project conventions (TypeScript, Tailwind)
5. Workflow (branches, commit messages, pre-merge checklist)
6. Troubleshooting

## Verify against
- `package.json` (scripts)
- `node_modules/astro/package.json` (supported Node and npm versions)
- `tsconfig.json`
- `.gitignore` (list of uncommitted paths)

## Steps
1. Correct the Node and npm requirements to Astro's published ranges.
2. Point the clone URL at the real repository.
3. Document the branch format, commit types and pre-merge checklist.
4. Add troubleshooting for the most likely setup problems.
5. Run each documented command.

## Done when
- [x] Node and npm versions match Astro's `engines` field
- [x] Every command in the doc has been run successfully
- [x] Ignored paths listed in the doc match `.gitignore`
- [x] Clone URL points at the real repository
