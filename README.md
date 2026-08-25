# VariantLens marketing website

Static Astro website for `https://variantlens.app`. This project is completely separate from the VariantLens Shopify application.

## Local development

```bash
npm install
npm run dev
```

Astro will print the local URL, normally `http://localhost:4321`.

## Production build

```bash
npm run check
npm run build
```

Static output is written to `dist/`.

## Structure

- `src/pages/` — indexable routes
- `src/layouts/` — shared metadata and SEO-page layouts
- `src/components/` — reusable header, footer, CTA, and FAQ components
- `src/styles/` — global design system
- `public/assets/brand/` — supplied VariantLens brand assets
- `public/robots.txt` — crawler rules and sitemap location

## Adding an SEO page

Create a new `.astro` file in `src/pages/`, use `SEOPage.astro`, and supply a unique title, description, eyebrow, H1, and introduction. Add genuinely useful semantic content and relevant internal links. Astro generates the route and sitemap entry automatically.

## Metadata

`BaseLayout.astro` generates canonical, Open Graph, Twitter, favicon, and structured-data markup. The canonical site origin is configured in `astro.config.mjs`.

## Analytics and Search Console

Copy `.env.example` to `.env` locally or add the same variables in Cloudflare Pages:

- `PUBLIC_GA_MEASUREMENT_ID` — optional GA4 measurement ID
- `PUBLIC_GOOGLE_SITE_VERIFICATION` — optional Search Console meta verification value

Variables prefixed with `PUBLIC_` are included in public browser output. Never put API keys or secrets in them.

## Cloudflare Pages

- Framework preset: Astro
- Build command: `npm run build`
- Build output directory: `dist`
- Root directory: `/`
- Production branch: `main`
- Node version: use a currently supported Node 20 or 22 release

Connect the GitHub repository first. Add `variantlens.app` as the custom domain only after the first Pages deployment succeeds.

## Before launch

- Replace placeholder Shopify App Store CTA links with the live listing URL.
- Confirm `support@variantlens.app` is monitored.
- Supply final favicon/social sharing assets if different from the current brand files.
- Add GA4 and Search Console values only when those services are configured.

