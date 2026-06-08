# Apposite Solutions — Website

The public marketing site for Apposite Solutions, an engineering firm that delivers
managed IT, cloud, and security through forward-deployed engineers.

## Stack

Static site — plain HTML, CSS, and vanilla JavaScript. No build step, no framework,
no dependencies.

## Structure

```
index.html    — self-contained landing page (markup, styles, and script inline)
logo.svg      — standalone copy of the brand mark, for reuse outside the page
style.css     — (legacy) stylesheet from the initial scaffold; index.html now embeds its own styles
```

## Local development

Serve the directory with any static file server, e.g.:

```
python -m http.server 8174
```

then open `http://localhost:8174`.

A `.claude/launch.json` config is included for previewing the site through Claude Code's
built-in preview server.

## Deployment

Hosted on **Cloudflare Pages** (free tier), deployed automatically via GitHub Actions
(`.github/workflows/deploy.yml`):

- **Pull requests** → unique Cloudflare Pages preview URL, posted as a PR comment
- **Merges to `main`** → production deploy

Deployment requires two repository secrets (configured in GitHub → Settings → Secrets
and variables → Actions):

- `CLOUDFLARE_API_TOKEN` — API token scoped to Cloudflare Pages: Edit
- `CLOUDFLARE_ACCOUNT_ID` — Cloudflare account ID

No manual deploy steps are needed once these are set — review the PR preview, merge,
and production updates automatically.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for branching strategy, commit message
conventions, and the PR/merge workflow.

## Changelog

See [CHANGELOG.md](CHANGELOG.md) for a record of notable changes, following
[Keep a Changelog](https://keepachangelog.com) conventions.
