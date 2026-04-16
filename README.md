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

This repository is configured for **Cloudflare Workers static assets** deployment via Wrangler.

### One-time setup

1. Ensure your Cloudflare API credentials are available in your shell:
   - `CLOUDFLARE_API_TOKEN`
   - `CLOUDFLARE_ACCOUNT_ID`

### Deploy from CLI

```bash
pnpm deploy:cloudflare
```

The deploy script builds the app and runs `wrangler deploy`.

### Notes

- `wrangler.toml` runs the Vite build and uploads the `dist` folder as Worker assets.
