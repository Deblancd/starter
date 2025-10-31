# Repository Guidelines

## Project Structure & Module Organization
Documentation lives alongside the Mintlify configuration. `docs.json` at the repo root defines navigation, theming, and the locales exposed to readers. Root-level MDX (`index.mdx`, `quickstart.mdx`, `development.mdx`) cover global intros while shared assets sit beside them (`favicon.svg`, `/images`, `/logo`). Language-specific guides now live in `en/` and `ar/`, each mirroring filenames (`overview.mdx`, `quickstart.mdx`, `development.mdx`) so slugs map cleanly across locales. API reference material remains under `api-reference/` with endpoint-specific folders (for example `api-reference/endpoint/get.mdx`).

## Build, Test, and Development Commands
First-time setup: `npm install -g mint` installs the Mintlify CLI globally. Use `mint dev` from the repository root to launch the local preview at `http://localhost:3000`. Run `mint update` if the CLI warns about incompatibilities, and restart `mint dev`. Before pushing, stop the dev server to ensure file watchers flush all generated artifacts.

## Coding Style & Naming Conventions
Write pages in MDX using 2-space indentation. Favor descriptive dashed filenames (`patient-overview.mdx`) that match the slugs declared in `docs.json` for every locale entry. Keep React components scoped within the page and ensure embedded JSX blocks export default content. Use sentence case headings unless you are quoting UI labels. When linking media, use relative paths such as `../images/patient-flow.png` and store locale-specific screenshots in language folders when necessary.

## Testing Guidelines
There are no automated tests; rely on preview validation. While `mint dev` runs, open each modified page, confirm navigation highlights match expectations, and check the browser console for MDX errors. Validate links and callouts in both `en` and `ar` locales. When editing `docs.json`, run it through a JSON linter or use `jq . docs.json` to ensure syntax correctness.

## Commit & Pull Request Guidelines
Recent history uses short imperative messages (e.g., `update logos`); follow that tone or adopt Conventional Commits (`docs:` / `chore:`) for clarity. Break work into focused commits that map to single topics. Pull requests should include: 1) a concise summary of the reader impact, 2) screenshots or GIFs for visual tweaks, 3) references to related issues or support tickets, and 4) a checklist noting that `mint dev` was run locally.
