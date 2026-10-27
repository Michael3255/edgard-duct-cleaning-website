# Plan: Content editing guide

- **Status:** completed
- **Doc:** [content-editing.md](../../content-editing.md)
- **Audience:** anyone updating the site's text, contact details or colors
- **Completed:** 2026-10-27

## Goal
A person with basic HTML knowledge can change copy, services, phone numbers and colors without breaking the page.

## Outline
1. Where each kind of content lives
2. Editing text
3. Adding or changing a service
4. Changing phone numbers
5. Changing the brand colors
6. Page title and description
7. Checking the change locally

## Verify against
- `src/pages/index.astro`, `src/components/CallBar.astro`, `src/layouts/BaseLayout.astro`
- `tailwind.config.mjs`

## Steps
1. List every place each phone number is defined or repeated.
2. Describe the `services` array and its fields.
3. Walk through one example edit end to end.

## Done when
- [x] Phone number locations match the source
- [x] The services example works when tried
- [x] The doc contains no client-private information
