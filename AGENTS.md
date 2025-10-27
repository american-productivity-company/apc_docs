# Repository Guidelines

## Project Structure & Module Organization
Docs content lives in top-level `.mdx` files (`introduction.mdx`, `quickstart.mdx`) and sectional folders. `essentials/`, `faqs/`, and `snippets/` hold reusable guide content, while `legal/` captures policy pages. API reference material sits in `api-reference/` with `openapi.json` and `endpoint/` examples. Shared assets are under `images/`, `logo/`, and `favicon.png`. Tweak global navigation, styling, and brand settings through `docs.json` at the root.

## Build, Test, and Development Commands
Install the Mintlify CLI once per machine with `npm i -g mintlify`. Run `mintlify install` whenever the preview server fails to resolve components or dependencies. Use `mintlify dev` from the repo root (where `docs.json` lives) to launch the local preview; add `--open` if you want the browser to auto-start.

## Coding Style & Naming Conventions
Keep filenames and slugs lowercase with hyphens (e.g., `legal/privacy-policy.mdx`). Author content in MDX with 2-space indentation and fenced code blocks such as ```````bash`````` where syntax highlighting helps. Favor short prose paragraphs, ordered steps for procedures, and callouts for warnings. When embedding components, follow Mintlify casing (`<Card>`, `<Steps>`), and place reusable snippets in `snippets/` for importing elsewhere.

## Testing Guidelines
There is no automated test suite; rely on manual validation in `mintlify dev`. Verify navbar links, anchor buttons, and API schemas after edits, and scan the terminal output for broken imports or frontmatter errors. For larger changes, preview pages on multiple breakpoints and confirm that icons and images load from the correct paths.

## Commit & Pull Request Guidelines
Match the existing imperative, concise commit style (`Updating privacy policy`, `Add ToS and PP Outline`). For each PR, include a summary of affected sections, screenshots or GIFs for visual tweaks, and references to any related support tickets. Confirm the branch rebases cleanly, ensure `mintlify dev` runs without warnings, and flag downstream configuration impacts in `docs.json`.

## Content & Configuration Tips
When adjusting branding, update `colors` and `fonts` in `docs.json` alongside `logo/` variants. Place downloadable assets inside `images/` and link using relative paths. Keep legal copy evergreen by dating material in-page rather than renaming files, preserving stable URLs for the published site.
