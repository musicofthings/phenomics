# phenomics

Vite + React + TypeScript application for the Phenomics landing page and UI.

## Local development

```bash
pnpm install
pnpm dev
```

## Code quality checks

```bash
pnpm lint
pnpm build
```

## Cloudflare deployment

This repository is configured for **Cloudflare Pages** deployment.

### One-time setup

1. Create a Cloudflare Pages project (or connect this repo in the Pages dashboard).
2. Ensure your Cloudflare API credentials are available in your shell:
   - `CLOUDFLARE_API_TOKEN`
   - `CLOUDFLARE_ACCOUNT_ID`

### Deploy from CLI

```bash
pnpm deploy:cloudflare
```

The deploy script builds the app and uploads the `dist` directory using Wrangler.

### Notes

- `wrangler.toml` contains the Cloudflare build output configuration.
- `public/_redirects` enables SPA fallback routing (`/*` -> `/index.html`).
