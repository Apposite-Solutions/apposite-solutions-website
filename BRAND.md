# Apposite Solutions — Brand Reference

Theme: **Harbor Navy + Signal Teal**. All tokens are defined as CSS variables
in `css/brand.css` — use them, don't hard-code hex values.

## Colors

| Token         | Hex       | Use                                   |
|---------------|-----------|---------------------------------------|
| `--ink`       | `#13314c` | Harbor Navy — primary brand, headings |
| `--ink-900`   | `#0d2438` | Deeper navy — full-bleed dark blocks  |
| `--ink-700`   | `#1d4566` | Hairlines on dark                     |
| `--teal`      | `#2f8581` | Signal Teal — the accent              |
| `--teal-600`  | `#287571` | Teal hover / eyebrows                 |
| `--teal-300`  | `#8fc0bd` | Teal on dark backgrounds              |
| `--paper`     | `#f4f6f7` | Cool off-white page                   |
| `--surface`   | `#ffffff` | Cards / surfaces                      |
| `--mist`      | `#e3e9ec` | Light hairlines                       |
| `--mist-700`  | `#cdd6db` | Borders                               |
| `--slate`     | `#5a6b78` | Secondary text                        |
| `--text`      | `#15222c` | Body near-black                       |

## Type

- **Spectral** (serif) — headings, the wordmark, pull quotes. Weights 400–700.
- **Hanken Grotesk** (sans) — body, UI, buttons. Weights 400–700.
- **IBM Plex Mono** — eyebrows, micro-labels, code-feel tags. Letter-spaced,
  uppercase. Weights 400–500.

## The logo — "The Point"

A ring with a precise center dot: *a system, brought to focus.* It doubles as
the **O** in App·**O**·site. Crosshair ticks (teal) are an optional richer
variant used at large sizes (see `logo-mark.svg`, the OG image).

- Clear space: keep at least the dot's diameter of padding on all sides.
- Minimum size: 16px for the mark; below that use the solid `favicon-16.png`.
- On dark backgrounds use the `-white` variants (white ring, teal dot).
- Don't recolor the ring anything but navy or white. Don't add gradients.

## Tagline

**precise solutions** — set in IBM Plex Mono, uppercase, letter-spaced, with
"solutions" in Signal Teal (`--teal`). Sits beneath the wordmark.

## Voice

Plain, senior, unfussy. We're engineers, not a help desk. Short declaratives.
No jargon for its own sake. "Work a traditional MSP calls 'not our job' — we
call it Tuesday."
