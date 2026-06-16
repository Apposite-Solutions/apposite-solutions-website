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

## Editing contact details

All contact info lives in **`config.js`** — edit it and reload. Nothing else
needs to change:

```js
window.APPOSITE_CONFIG = {
  company:   "Apposite Solutions",
  email:     "hello@apposite.io",   // wires the contact button + mailto:
  phone:     "+1 (555) 014-2230",   // displayed text
  phoneHref: "+15550142230",        // dialable (digits + leading +)
  domain:    "apposite.io",
  url:       "https://apposite.io",
  social: { linkedin: "...", x: "", github: "" }  // blank = hidden
};
```

> The canonical URL, Open Graph and Twitter tags live in the `<head>` of
> `index.html` — update the `apposite.io` references there when the real
> domain is live.

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
