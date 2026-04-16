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

The deploy script runs `wrangler deploy`, which executes the custom Wrangler build command.

### Notes

- the build script force-cleans `dist` and deletes any stray `dist/_redirects` / `dist/_headers` files before upload to prevent Cloudflare redirect validation failures.
- `wrangler.toml` runs the build and uploads the `dist` folder as Worker assets with `html_handling = "auto-trailing-slash"` so `/` correctly resolves to `index.html`.
