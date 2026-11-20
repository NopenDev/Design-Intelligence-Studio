---
name: ui-ux-pro-max-intelligence
description: "Use when starting a new product UI, analyzing design requirements, orchestrating UI/UX decisions, or establishing a product-wide design direction."
---

# UI/UX Intelligence

This is the orchestration and product-analysis skill for the suite. It coordinates design decisions and delegates specialized work; it does not claim access to the upstream UI UX Pro Max searchable database or Python CLI.

## Mission

Translate product context into a coherent, usable, and implementable interface. Keep product intent, user needs, accessibility, interaction, responsive behavior, and technical constraints in the same decision loop.

## Intake contract

Extract from the brief or actual project:
- product type, domain, audience, and usage context;
- primary user task and measurable success condition;
- platform, verified implementation stack, and operational constraints;
- brand requirements and supplied references;
- data/content density, localization, and accessibility needs;
- existing design system, user flows, components, and implementation conventions.

Do not invent research, brand facts, user needs, technologies, or performance constraints. Inspect supplied files and screens first. Ask only for missing information that materially changes the decision; otherwise label assumptions.

## Orchestration workflow

1. Frame the product problem and determine whether the request is discovery, UX, visual direction, design-system work, implementation, audit, spatial mapping, or analytics.
2. Select the smallest set of specialist skills using `references/skill-routing.md`.
3. Establish authority: explicit user specification/Figma first; existing product system and architecture second; verified platform conventions third; skill recommendations last.
4. Define the primary journey, hierarchy, key states, and success criteria before visual decoration.
5. Evaluate candidate directions on user fit, distinctiveness, accessibility, responsive behavior, technical feasibility, and maintenance cost.
6. Resolve cross-skill conflicts using ownership boundaries; do not let a visual preference override an explicit behavior or data contract.
7. Produce a concise recommendation with evidence, trade-offs, next steps, and checks required for confidence.

## Decision quality

- Separate facts, assumptions, hypotheses, and preferences.
- Prefer product-specific reasoning over trend copying.
- Do not assume every product needs a dashboard, sidebar, cards, dark theme, or a map.
- Treat accessibility and security constraints as quality requirements, not optional polish.
- Prefer reversible decisions when evidence is weak.
- Do not create duplicate components, tokens, APIs, metrics, or data models without inspecting existing ones.

## Deliverables

For substantial work, provide a compact product/design brief, user and task model, selected specialists, visual or interaction thesis where relevant, key flow and state inventory, implementation implications, risks, and acceptance criteria.

For a narrow task, answer directly and avoid generating a full design system or product plan.
