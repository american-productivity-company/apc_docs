# Righthand Docs

Public product documentation for [Righthand](https://www.righthand.ai), published at [docs.righthand.ai](https://docs.righthand.ai).

## Local development

Use Node.js 20 LTS, then install the pinned Mintlify CLI version used by CI:

```bash
npm install --global mintlify@4.2.531
```

From this repository's root, start a local preview:

```bash
mintlify dev
```

Before opening a pull request, run the same checks as CI:

```bash
mintlify validate
mintlify broken-links --check-anchors --check-redirects
mintlify a11y
```

## Source of truth

These docs describe the customer-visible behavior of the Righthand platform. Verify changing product details—especially pricing, navigation, permissions, billing, and integrations—against the current application before editing. Do not add speculative workflows, placeholder API references, or screenshots from retired interfaces.

## Publishing

Mintlify publishes the production docs from the repository's default branch. Changes should land through a reviewed pull request after local validation and preview QA.

## Troubleshooting

- If `mintlify dev` fails to start, run `mintlify install` and try again.
- If a page returns 404 locally, confirm it exists in `docs.json` and that the preview command is running from the directory containing `docs.json`.
