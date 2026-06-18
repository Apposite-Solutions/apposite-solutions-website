# Changelog

All notable changes to this project will be documented in this file.


## [2026-06-18] SEO Copy Rewrite

### Added
- JSON-LD structured data (`ProfessionalService`) in `index.html` for rich-snippet eligibility
- `sitemap.xml` — was referenced in `robots.txt` but missing
- SEO rewrite report at `work-sessions/seo-report/report.html`

### Changed
- All homepage copy rewritten: zero jargon, no double-negatives, affirmative framing throughout
- Meta title, description, OG, and Twitter tags updated with target SEO keywords
- Nav labels shortened: "Why Us," "Services," "Our Process," "Right Fit"
- Service card titles now double as keyword phrases (Embedded Systems Engineer, Cloud Infrastructure Management, Cybersecurity Strategy & Hardening)
- Footer tagline rewritten for long-tail SEO
- `site.webmanifest` description updated to match new positioning

---

### Added
- Google Analytics 4 loaded dynamically from `config.gaId`; production builds
  inject the ID from the `GA_MEASUREMENT_ID` GitHub secret, PR previews receive
  an empty value and send no data to GA.
- `gaId` field added to `config.js` for local control of analytics.

### Changed
- v2 site (`index.html`, `config.js`, `css/brand.css`, full asset set) replaced
  the original animated single-page build. Brand tokens: Harbor Navy + Signal Teal.
- `config.js` centralises all contact details (email, phone, domain, social, gaId);
  phone and social fields are commented out until ready for go-live.
- GitHub Actions workflow builds `config.js` from GitHub secrets at deploy time
  so sensitive values are never committed to the repository.

> Pre-go-live checklist:
> - Set all required GitHub secrets (see README → Deployment).
> - Uncomment phone/social fields in `config.js` if needed.
> - Update `apposite.io` references in `<head>` of `index.html` (canonical, OG,
>   Twitter tags) once the domain is live.
