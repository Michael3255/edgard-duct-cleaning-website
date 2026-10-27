# Design decisions

Short records of the main choices behind the site. Each one gives the context, the decision and what follows from it.

## 1. Static site with no backend

**Context.** The site exists so customers can find the business and call. It has no accounts, no stored data and no content that changes by the hour.

**Decision.** Build a static site with Astro. Pages render to HTML at build time.

**Consequences.**
- Hosting is simple and cheap, and there is no server to patch.
- There is very little to attack, because nothing runs on request.
- Anything interactive, such as a contact form, needs a third-party service or a serverless function added later.

## 2. Mobile-first layout with a sticky call bar

**Context.** People looking for a local service are mostly on a phone and want to call, not read.

**Decision.** `CallBar.astro` pins a full-width call button to the bottom of the screen below the `md` breakpoint, using a `tel:` link. On larger screens the header carries the call button instead.

**Consequences.**
- One tap starts a call from anywhere on the page.
- The body needs bottom padding on small screens so the bar does not hide content (set in `BaseLayout.astro`).
- The phone number is defined in more than one place; see the [content editing guide](content-editing.md).

## 3. System font stack

**Context.** Web fonts add a download and can cause the text to shift as they load.

**Decision.** Use the system font stack set in `tailwind.config.mjs` (`system-ui`, `-apple-system`, `Segoe UI`, `Roboto`).

**Consequences.**
- Text renders immediately and there is nothing extra to download.
- The typeface differs slightly between operating systems.

## 4. Brand palette in the Tailwind config

**Context.** The same blues and oranges appear throughout the page, and the exact values may change once the owner confirms them.

**Decision.** Define the palette once under `brand` in `tailwind.config.mjs` and use the names in markup.

**Consequences.**
- Changing a color is a one-line edit.
- Orange is used only for calls to action so they stand out against the blue.

## 5. Structured data for local search

**Context.** The business depends on local search results.

**Decision.** `BaseLayout.astro` includes a `LocalBusiness` JSON-LD block, along with a title, description and Open Graph tags that pages can override.

**Consequences.**
- Search engines get the business name, phone number and service area in a machine-readable form.
- The values in the block are written by hand, so they must be updated whenever the business details change.
