# Design Intelligence Studio

**Version:** 1.1.0 · **Maintainer:** NopenDev · **License:** MIT

A reusable 21-skill toolkit for product design and software delivery. It covers UI/UX intelligence, art direction, product flows, design systems, visual foundations, motion, responsive accessibility, Figma implementation, visual QA, anti-slop audits, software architecture, frontend/backend engineering, modern web platform engineering, database and distributed systems, algorithmic problem solving, advanced testing and debugging, AI engineering and evaluation, critical reasoning, GIS, and data visualization.

## Repository layout

- `.agents/plugins/marketplace.json` — local marketplace registration
- `plugins/design-intelligence-studio/plugin.json` — plugin metadata and version
- `plugins/design-intelligence-studio/skills/` — 21 skill definitions

## Included skills

1. UI/UX Pro Max Intelligence
2. Frontend Art Direction
3. Product UX and Flows
4. Design System Engineering
5. Visual Design Foundations
6. Motion and Interaction Design
7. Responsive Accessibility
8. Figma to Interface
9. UI Visual QA
10. Anti-Slop UI Audit
11. Software Architecture and Code Engineering
12. Frontend and Backend Engineering
13. Modern Web Platform Engineering
14. Database and Distributed Systems Engineering
15. Algorithmic Problem Solving
16. Advanced Testing and Debugging
17. AI Engineering and Evaluation
18. Honest Critical Reasoning
19. Critical Reasoning and Research
20. GIS and Mapping Engineering
21. Data Visualization and Analytics

## How to use it

### Option A — ChatGPT Desktop / local marketplace

1. Install or open ChatGPT Desktop.
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

Each person installs it in their own environment. Installing a browser extension alone does not install this plugin.

## Privacy

The public plugin manifests identify the maintainer by display name only. No personal contact email is required for installation.

## Versioning

Current source: `1.1.0`. Keep the plugin manifest version and changelog aligned when releasing updates.

## Scope

This is a collection of reusable skills and Markdown references. It does not install a runtime, CLI, API, or MCP server by itself. Some workflows may require the user's own connected tools.
