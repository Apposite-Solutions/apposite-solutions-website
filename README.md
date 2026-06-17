# Apposite Solutions — Website

The shipping v1 of the Apposite marketing site. Single-page, dependency-free
(only Google Fonts loaded over CDN). Drop it on any static host.

## Quick start

Open `index.html` in a browser, or serve the folder:

```bash
# any static server works, e.g.
npx serve .
# or
python3 -m http.server 8000
```

Then visit the printed URL.

## File structure

```
apposite-site/
├── index.html              The website
├── config.js               ← edit contact details here
├── site.webmanifest        PWA / install metadata
├── robots.txt
├── css/
│   └── brand.css           Design tokens & base styles (the brand template)
└── assets/
    ├── favicon.svg              Primary favicon (scalable)
    ├── favicon-16/32/48.png     Raster favicon fallbacks
    ├── apple-touch-icon.png     180×180 iOS home-screen icon
    ├── icon-192/512.png         PWA icons
    ├── icon-maskable-512.png    PWA maskable icon
    ├── og-image.png             1200×630 social share card
    ├── logo-mark.svg            The "Point" mark (navy/teal)
    ├── logo-mark-white.svg      Mark for dark backgrounds
    ├── logo-lockup.svg          Horizontal "App◉site" lockup
    └── logo-lockup-white.svg    Lockup for dark backgrounds
```

## Brand

See **`css/brand.css`** for the full token set and **`BRAND.md`** for a quick
reference (colors, type, the logo system). The theme is *Harbor Navy +
Signal Teal*.

## Fonts

Loaded from Google Fonts: **Spectral** (serif headings), **Hanken Grotesk**
(body), **IBM Plex Mono** (labels). To self-host, download the families and
swap the `<link>` in `index.html` for local `@font-face` rules.

## Analytics

Google Analytics 4 is loaded dynamically from `config.gaId`. Set it in `config.js` for local use:

```js
gaId: "G-XXXXXXXXXX",  // leave blank ("") to disable
```

In CI, the value comes from the `GA_MEASUREMENT_ID` GitHub secret and is only injected on production (`main`) builds — PR previews receive an empty `gaId` and send no data to GA.

## Editing contact details

All editable values live in `config.js` — change them and reload. The full set:

```js
window.APPOSITE_CONFIG = {
  company:   "Apposite Solutions",
  email:     "hello@apposite.io",
  // phone:     "+1 (555) 014-2230",    // uncomment to enable phone link
  // phoneHref: "+15550142230",
  domain:    "apposite.io",
  url:       "https://apposite.io",
  // social: { linkedin: "https://..." },  // uncomment to show social link
  gaId:      "",                           // set to GA4 measurement ID or leave blank
};
```

## Deployment

Hosted on **Cloudflare Pages**, deployed via GitHub Actions (`.github/workflows/deploy.yml`).

| Branch | Deploys to |
|---|---|
| `main` | Production (custom domain) |
| Any PR against `main` | Unique Cloudflare Pages preview URL (posted as PR comment) |

The workflow builds `config.js` from GitHub secrets at deploy time so sensitive values are never committed.

### GitHub secrets required

| Secret | Purpose |
|---|---|
| `CLOUDFLARE_API_TOKEN` | Scoped to Cloudflare Pages: Edit |
| `CLOUDFLARE_ACCOUNT_ID` | Cloudflare account ID |
| `SITE_COMPANY` | Legal company name |
| `CONTACT_EMAIL` | Contact email wired to the CTA button |
| `SITE_DOMAIN` | Bare domain, e.g. `apposite.io` |
| `SITE_URL` | Full URL, e.g. `https://apposite.io` |
| `GA_MEASUREMENT_ID` | GA4 measurement ID — leave empty to disable analytics |

### DNS / custom domain

1. In Cloudflare DNS, add a `CNAME` for `@` pointing to `apposite-solutions-website.pages.dev` (proxied, orange cloud).
2. In Pages → your project → **Custom domains**, add the domain — SSL is issued automatically.
