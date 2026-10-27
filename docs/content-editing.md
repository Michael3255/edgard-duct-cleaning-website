# Content editing guide

This guide covers the most common edits to the site. After any change, run `npm run dev` and check the result at http://localhost:4321.

## Where things live

| To change | Edit |
| --- | --- |
| Headings, paragraphs, trust strip, contact section | `src/pages/index.astro` |
| Service cards | The `services` array at the top of `src/pages/index.astro` |
| Phone numbers | See [Phone numbers](#phone-numbers) |
| Page title and search description | `src/layouts/BaseLayout.astro` |
| Brand colors | `tailwind.config.mjs` |
| Site URL | `astro.config.mjs` |

## Editing text

Open `src/pages/index.astro`. Everything below the `---` line that closes the frontmatter is HTML. Find the text, change it and save; the dev server reloads on its own.

Text in square brackets, such as `[Pending confirmation]`, marks content that has not been confirmed yet. Replace the whole bracketed phrase when you have the real value.

## Services

Each card on the page comes from one entry in the `services` array:

```js
{ title: 'Dust', body: 'Full-unit cleaning removes built-up dust from supply and return ducts.' },
```

- To **edit** a card, change its `title` or `body`.
- To **add** a card, add a new `{ title, body }` line to the array.
- To **remove** a card, delete its line.

The grid adjusts to the number of cards automatically.

## Phone numbers

Each number is stored in two forms: a display version (with parentheses) and a `tel:` version (digits with a country code).

| Number | Where it is defined |
| --- | --- |
| Primary | Constants at the top of `src/pages/index.astro` and `src/components/CallBar.astro` |
| Primary (search data) | `telephone` in the JSON-LD block, and the default `description`, in `src/layouts/BaseLayout.astro` |
| Secondary | Constants at the top of `src/pages/index.astro` |

Example for `index.astro`:

```js
const primaryPhoneDisplay = '(540) 288-6840';   // shown on the page
const primaryPhoneTel = '+15402886840';         // used in the tel: link
```

To change the primary number, update all three files, then search the project for the old number to make sure none remain.

## Brand colors

In `tailwind.config.mjs`, edit the values under `colors.brand`. Every use of `bg-brand-blue`, `text-brand-orange-dark` and similar classes follows automatically.

## Page title and description

`BaseLayout.astro` sets defaults for the page title and meta description. To override them for a page, pass props:

```astro
<BaseLayout title="New title" description="New description.">
```

## Check your change

```bash
npm run build
```

A successful build means the page compiles. Then run `npm run preview` to see the built site.
