# Changelog

All notable changes to this project are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Changed
- Switched the site from a light to a dark color theme (charcoal background,
  off-white text) with a bolder, more saturated accent (vivid azure→cyan→violet
  range) for stronger visual impact and reduced eye strain. Per-load accent
  randomization ranges were retuned to stay vivid and legible against the dark
  background.

### Added
- Single-page animated landing site (`index.html`) with embedded brand SVG logo,
  full brand content (mission, vision, differentiators, services, values, fit
  criteria, how-it-works, contact CTA), reveal-on-scroll animations, hover states,
  and ambient parallax.
- Per-page-load tasteful randomization: accent hue/saturation drift within a
  bounded graphite-blue range, two ambient motion styles (drifting orbs / shifting
  gridlines), randomized reveal stagger and entrance order — bounded so the brand
  remains recognizable across loads.
- Standalone brand mark (`logo.svg`) for reuse outside the page.
- `style.css` for the initial page scaffold.
- GitHub Actions workflow (`.github/workflows/deploy.yml`) deploying to Cloudflare
  Pages: PR previews and production deploys on merge to `main`.
- `CONTRIBUTING.md` documenting branching strategy and commit message conventions.
- `README.md` describing the project, local development, and deployment process.
- `.claude/launch.json` static-server config for local preview.

[Unreleased]: https://github.com/Apposite-Solutions/apposite-solutions-website/commits/main
