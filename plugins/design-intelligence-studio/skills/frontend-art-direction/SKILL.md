---
name: frontend-art-direction
description: "Use when creating a new visual direction, landing page, branded experience, or redesign where the interface needs a distinct visual identity."
---

# Frontend Art Direction

Act as a design lead. The goal is a visual direction that belongs to this product and audience, not a generic generated interface.

## Process
1. Understand the subject, audience, context, and primary task. If the brief is vague, propose a concrete interpretation and label it as a proposal.
2. Inspect existing brand assets, Figma, design tokens, and code conventions. Preserve supplied direction unless redesign is requested.
3. Generate 2–3 materially different concepts grounded in the product's content and purpose. Compare them on task clarity, identity, accessibility, responsive behavior, and implementation cost.
4. Select one visual thesis and define palette roles, type roles, grid/layout, surface behavior, imagery, and motion restraint.
5. Critique the plan before implementation: identify which choices are product-specific and which could be pasted unchanged into an unrelated SaaS page. Replace the generic choices.
6. Implement structure first, then expression. Inspect rendered output when possible and remove one unnecessary decorative element.

## Design principles
- Typography carries identity; choose typefaces for language coverage, readability, licensing, and product temperament.
- Visual structure must encode hierarchy or relationships. Numbering, dividers, borders, labels, and badges are not filler.
- Use real content or realistic-shape sample data. Avoid lorem ipsum and arbitrary metrics.
- Concentrate expressive choices. One memorable signature can be stronger than many competing effects.
- Use motion to explain state or guide attention; routine interactions should remain immediate.
- Design copy as part of the interface: concrete nouns, active verbs, consistent action names, clear recovery.

## Do not turn these into bans
Gradients, glass, cards, pills, bento grids, dark themes, serif typography, or bold radii are not inherently wrong. They become slop when chosen without product, brand, content, or interaction justification. The user's explicit direction overrides generic anti-pattern heuristics.
