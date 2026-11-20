# Design Intelligence Studio

**Version:** 1.0.1 · **Maintainer:** NopenDev · **License:** MIT

A reusable 14-skill toolkit for product design and software delivery: UI/UX intelligence, art direction, product flows, design systems, visual foundations, motion, accessibility, Figma implementation, visual QA, anti-slop audits, software architecture, frontend/backend engineering, GIS, and data visualization.

## Repository layout

- `.agents/plugins/marketplace.json` — local marketplace registration
- `plugins/design-intelligence-studio/` — complete plugin source
- `plugins/design-intelligence-studio/skills/` — 14 skill definitions and references

## How to use it

### Option A — ChatGPT Desktop / local marketplace

1. Install or open the ChatGPT Desktop app.
2. Clone this repository to a permanent folder, or download the ZIP and extract it.
3. In ChatGPT Desktop, open **Settings → Plugins** and find the local marketplace management option (labels can differ by app version).
4. Add the extracted repository folder as a local marketplace. The marketplace manifest is at `.agents/plugins/marketplace.json`.
5. Install **Design Intelligence Studio** from the marketplace.
6. Start a new chat and select/use the plugin where available.

Local marketplace support is app-version dependent. A GitHub repository being public does not automatically publish it to ChatGPT's global plugin directory.

### Option B — Codex CLI

For a Codex CLI installation that supports plugin marketplaces, run:

```bash
codex plugin marketplace add NopenDev/Design-Intelligence-Studio
```

Then open the plugin browser/management command supported by your installed Codex version, install **design-intelligence-studio**, and restart or start a new session if requested. If the command is not recognized, update Codex CLI and consult its current plugin documentation.

## How friends can get it

Send them this repository:

https://github.com/NopenDev/Design-Intelligence-Studio

Or send the ZIP download page:

https://github.com/NopenDev/Design-Intelligence-Studio/archive/refs/heads/main.zip

They can download/extract it and follow Option A or Option B above. Each person installs it in their own environment; installing the ChatGPT browser extension alone does not install this plugin.

## Privacy

The public plugin manifests identify the maintainer by display name only. No personal contact email is required for installation.

## Versioning

Current source: `1.0.1`. Keep the plugin manifest version and changelog aligned when releasing updates.

## Scope

This is a collection of reusable skills and Markdown references. It does not install a runtime, CLI, API, or MCP server by itself. Some workflows may require the user's own connected tools.
