# Plan: Deployment guide

- **Status:** blocked (hosting provider not yet chosen)
- **Doc:** `deployment.md` (not yet written)
- **Audience:** whoever publishes the site
- **Completed:**

## Goal
Someone can publish the built site and roll back a bad release.

## Blocker
The hosting provider has not been decided. The site must end up owned by the business owner, so the choice needs to be one the owner can manage comfortably.

## Outline (once unblocked)
1. Build command and output directory (`npm run build`, `dist/`)
2. Account and domain ownership
3. Connecting the repository
4. Custom domain and HTTPS
5. Rolling back a release

## Verify against
- `package.json`, `astro.config.mjs` (`site` value)

## Steps
1. Choose the hosting provider.
2. Write the doc for that provider.
3. Test a deploy from a branch before documenting it.

## Done when
- [ ] Provider chosen
- [ ] A test deploy has succeeded
- [ ] Rollback steps have been tried
