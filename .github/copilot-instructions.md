## Repo overview (big picture)

- This repository is a static HTML/CSS course starter for WDD 130. There are no build tools, package manifests, or server-side components — just HTML files at the repo root and under `weekNN/`, plus `styles/` and `images/` folders.
- Primary entry points: `index.html` (root) and the per-week pages in each `week##/` folder (e.g., `week02/basic-layout.html`). Styles are organized both at `styles/` and under `week##/styles/`.

## What an AI coding agent should know (contract)

- Inputs: small edits to HTML/CSS files, new example pages or images, or fixes to student pages under `week##/`.
- Outputs: concise, minimal diffs that preserve the site structure and file naming conventions (lowercase, hyphen-separated filenames). Prefer relative links.
- Error modes: watch for malformed HTML (students often omit closing `>` or attributes), broken relative paths to `images/` and `styles/`, and missing assets.

## Repository patterns & conventions (concrete)

- Folder layout is predictable: `week##/` contains pages for that week. Each `week##/` may have its own `styles/` and `images/` subfolders. Example: `week02/basic-layout.html` and `week02/styles/`.
- Shared assets live at repo root: `styles/` (global CSS) and `images/` (global images). Example: `index.html` references `images/salt-lake-temple.jpg`.
- Filenames use lowercase with hyphens (e.g., `basic-layout.html`, `box-model.css`). Keep this convention when adding files.

## Common, discoverable issues to check and fix

- Broken/malformed HTML tags: e.g., `week02/basic-layout.html` contains an `<img>` element that's missing its closing bracket — fix by ensuring valid tag syntax and attributes.
- Incorrect relative paths: when editing a page in `week##/`, use relative references (e.g., `images/basic-logo.png` or `styles/box-model.css`) rather than absolute paths.
- Styles split: if a page in `week##/` includes a stylesheet, check `week##/styles/` first, then fall back to repo-level `styles/`.

## No build/test tooling — how to run and verify edits locally

- This is a static site. There is no build step. To preview changes in a browser, serve the folder locally (examples below):

```powershell
# Quick one-off server (PowerShell)
python -m http.server 8000

# Or use VS Code Live Server extension to preview `index.html` and pages.
```

## Helpful examples to reference in edits

- Edit content: `index.html` — root homepage. Example: image uses `images/salt-lake-temple.jpg`.
- Fix a student page: `week02/basic-layout.html` — check for malformed tags and correct `img` markup and `meta` attributes.
- Add styles: prefer placing per-week CSS in `week##/styles/`, and global CSS in `styles/`.

## Integration points / external dependencies

- None declared in the repo. Do not introduce dependencies (npm, bundlers) without explicit instruction from maintainers. Keep changes minimal and compatible with static hosting.

## When merging or updating an existing `.github/copilot-instructions.md`

- Preserve any existing actionable content. Merge by adding missing concrete examples and keeping the original author's intent. Avoid removing historical notes unless clearly obsolete.

## Suggested next steps for the maintainer (optional)

- Add a short CONTRIBUTING or DEVELOPMENT note listing preferred local preview commands and any linting rules (if desired). That makes future agent guidance easier.

---
If any areas here are unclear or you'd like more explicit automation (lint rules, HTML validator, or CI preview), tell me which and I will update this file.
