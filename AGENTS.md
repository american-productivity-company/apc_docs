# Repository Guidelines

## Project Structure & Module Organization

Customer-facing content lives in `introduction.mdx` and three sectional folders:

- `guides/` for setup, operation, connections, plans, billing, and team administration.
- `security/` for connection, communications, and voice-authentication controls.
- `legal/` for terms and privacy policy pages.

Mintlify navigation, branding, and site behavior are configured in `docs.json`. Shared brand assets live under `logo/`, `images/`, and the root favicon files. The published Righthand support skill lives at `.mintlify/skills/righthand-docs/SKILL.md` and must change when product guidance or routes change.

This repository does not publish a public API reference. Do not add example APIs or placeholder OpenAPI specifications.

## Source of Truth

Public docs must describe current customer-visible product behavior. Before changing navigation, pricing, permissions, billing, integrations, or security guidance, verify the corresponding control in the current Righthand application and product source. Do not infer a promise from an old screenshot or retired route.

Prefer screenshot-light procedures. When a screenshot materially helps, capture the current deployed interface, remove account data, and record when it was verified. Delete screenshots when their interface is retired.

## Build, Test, and Development Commands

Use Node.js 20 LTS and the Mintlify CLI version pinned in `.github/workflows/docs-validation.yml`:

```bash
npm install --global mintlify@4.2.531
```

Run a local preview from the repository root:

```bash
mintlify dev
```

Run every validation check before opening a pull request:

```bash
mintlify validate
mintlify broken-links --check-anchors --check-redirects
mintlify a11y
```

## Writing and MDX Conventions

Keep filenames and slugs lowercase with hyphens. Use short prose, ordered steps for procedures, tables for exact comparisons, and callouts for warnings or constraints. Use 2-space indentation inside Mintlify components and preserve component casing such as `<Card>`, `<Steps>`, and `<Warning>`.

Use the exact customer-visible label for controls and routes. Keep stable published slugs when retitling a page unless a redirect is intentionally configured. Never publish raw credentials, internal IDs, unsupported timing guarantees, remembered DNS values, or carrier codes.

## Validation Guidelines

For every substantive docs change:

1. Run all three Mintlify checks.
2. Preview the site and visit every changed page.
3. Test navigation, internal links, theme, and representative desktop and mobile viewports.
4. Check browser console errors and failed network requests.
5. Compare consequential claims against the current product one more time.

## Commit and Pull Request Guidelines

Use an imperative, concise commit title. Include a commit body headed `Why this change` that explains the user or maintenance problem being addressed.

Each pull request should summarize affected sections, list validation performed, include QA screenshots for meaningful visual or navigation changes, and call out any downstream updates that should wait until the pages are live.
