# Development guide

## Requirements

- Node.js `^18.17.1`, `^20.3.0` or `>=21.0.0` (Astro 4's supported range)
- npm 9.6.5 or newer

Check your versions:

```bash
node --version
npm --version
```

## Setup

```bash
git clone https://github.com/<your-username>/edgard-duct-cleaning-website.git
cd edgard-duct-cleaning-website
npm install
```

## Scripts

| Command | What it does |
| --- | --- |
| `npm run dev` (or `npm start`) | Starts the dev server at http://localhost:4321 with hot reload |
| `npm run build` | Builds the static site into `dist/` |
| `npm run preview` | Serves the built `dist/` locally so you can check production output |
| `npm run astro -- <command>` | Runs any Astro CLI command, for example `npm run astro -- check` |

Run `npm run build` before merging anything. A build that fails locally will fail anywhere else.

## Conventions

- **TypeScript:** `tsconfig.json` extends `astro/tsconfigs/strict`. Components that take props declare a `Props` interface in their frontmatter.
- **Styling:** Use Tailwind classes. Brand colors are defined once in `tailwind.config.mjs` as `brand-blue`, `brand-blue-dark`, `brand-blue-light`, `brand-orange` and `brand-orange-dark`; use those names rather than hex values.
- **Content:** Page copy lives in `src/pages/index.astro`. See the [content editing guide](content-editing.md).

## Workflow

1. Create a branch from `main`. Do not commit directly to `main`.
2. Make the change and check it locally.
3. Commit with a clear message.
4. Merge into `main` through a pull request.

**Branch names** use `category/kebab-description`:

```
feature/contact-form
fix/mobile-call-bar-overlap
docs/add-deployment-guide
chore/update-dependencies
```

The category is one of `feature`, `fix`, `docs`, `chore` or `refactor`.

**Commit messages** follow [Conventional Commits](https://www.conventionalcommits.org): `type: short summary`, in the present tense and under about 72 characters, for example `fix: stop call bar covering the footer`.

| Type | Use for |
| --- | --- |
| `feat` | A new feature or page section |
| `fix` | A bug fix |
| `docs` | Documentation only |
| `style` | Formatting or styling with no behavior change |
| `refactor` | Code change that is neither a fix nor a feature |
| `chore` | Dependencies, config and other upkeep |

**Before merging:**
- [ ] `npm run build` passes
- [ ] The change looks right at phone width and desktop width in `npm run dev`
- [ ] New phone numbers or business details are updated everywhere they appear (see the [content editing guide](content-editing.md))
- [ ] Docs are updated if the change affects setup, structure or conventions
- [ ] No secrets, `.env` files or client-private information are included

**Not committed:** dependencies (`node_modules/`), build output (`dist/`), generated types (`.astro/`), environment files (`.env`, `.env.*` except `.env.example`) and operating-system files. See `.gitignore`.

## Troubleshooting

**`npm install` fails or warns about the engine.** Your Node version is outside the supported range. Install a supported version and try again.

**Port 4321 is already in use.** Astro will pick the next free port and print it in the terminal. Use that URL.

**Styles are missing or stale.** Stop the dev server and start it again. Tailwind only generates classes it finds in files under `src/`, so a class added somewhere else will not appear.

**`dist/` or `.astro/` look wrong.** Both are generated folders. Delete them and rebuild.
