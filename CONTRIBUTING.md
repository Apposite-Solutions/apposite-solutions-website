# Contributing Guide — Apposite Solutions

This document defines how we branch, commit, and ship code across Apposite Solutions
projects. It applies to this repo and is intended as the standard for all of our
repositories.

## Branching strategy

- **`main`** is the production branch. It is protected — no direct pushes. All changes
  land via pull request.
- Create short-lived branches off `main` named for the type of work:
  - `feature/<short-description>` — new functionality (e.g. `feature/contact-form`)
  - `fix/<short-description>` — bug fixes (e.g. `fix/mobile-nav-overlap`)
  - `chore/<short-description>` — maintenance, tooling, config (e.g. `chore/update-ci-workflow`)
- Open a pull request into `main` when the branch is ready for review. Every PR
  triggers an automatic preview deployment so changes can be reviewed live before
  merging.
- Delete branches after they're merged.

## Commit messages — Conventional Commits

Write commit messages as `<type>: <short summary>`, using these types:

| Type | Use for |
|------|---------|
| `feat` | a new feature, page, or capability |
| `fix` | a bug fix |
| `chore` | maintenance — dependencies, configuration, CI/CD |
| `docs` | documentation-only changes |
| `style` | formatting or visual-only changes (no logic change) |
| `refactor` | restructuring code with no change in behavior |
| `test` | adding or updating tests |

Guidelines:
- Use the imperative mood: "add", "fix", "update" — not "added", "fixes", "updated".
- Keep the summary line under ~72 characters.
- Add a body (separated by a blank line) when the change needs more explanation —
  focus on *why*, not *what* (the diff already shows what changed).

Examples:
```
feat: add contact form to homepage
fix: correct mobile nav overlap on small screens
chore: add Cloudflare Pages deploy workflow
docs: update README with local setup steps
```

Note: merge commits (`Merge pull request #N from ...`) are generated automatically by
GitHub when a PR is merged — you don't need to write these by hand.

## Pull requests

- Keep PRs focused on a single change or feature; smaller PRs are easier to review
  and produce cleaner preview deployments.
- Make sure the automated checks (build/preview deployment) pass before merging.
- Resolve all review conversations before merging.
- **Always squash-merge into `main`.** Each PR becomes a single commit on `main`,
  titled with a Conventional Commits–style summary (e.g. `feat: add contact form to
  homepage`). This keeps `main` history linear and readable regardless of how messy
  the in-progress commits on the branch were. Do not use "Merge commit" or "Rebase
  and merge" when merging into `main`.

## Documentation currency

Docs are part of the change, not an afterthought — update them in the same PR as the
code:

- **CHANGELOG.md** — every change that affects external/observable behavior gets an
  entry under `[Unreleased]`, categorized strictly as `Added`, `Changed`,
  `Deprecated`, `Removed`, `Fixed`, or `Security`, following
  [Keep a Changelog](https://keepachangelog.com). Skip purely internal refactors with
  no surface-level impact. Entries move out of `[Unreleased]` only when a release is
  explicitly tagged (semantic versioning).
- **README.md** — update the relevant section whenever you change anything structural:
  new env vars, config options, CLI flags, the API/page surface, or dependencies. If a
  section is known to be stale and you're not the one fixing it, call it out explicitly
  (e.g. a `<!-- TODO: stale -->` note or a mention in the PR) rather than leaving it to
  silently mislead the next reader.
- This applies to this project and other standalone Apposite Solutions projects with
  their own README/CHANGELOG. It does not apply to one-off scripts or quick fixes that
  don't already have these files.

## Deployment

This site deploys automatically via GitHub Actions to Cloudflare Pages:

- Pull requests get a unique **preview URL** for review.
- Merges to `main` deploy directly to **production**.

No manual deployment steps are required — review the preview, merge the PR, and the
production site updates automatically.
