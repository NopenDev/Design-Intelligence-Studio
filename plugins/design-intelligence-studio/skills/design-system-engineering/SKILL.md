---
name: design-system-engineering
description: "Use when creating, documenting, auditing, or extending design tokens, component libraries, themes, typography scales, or reusable UI patterns."
---

# Design System Engineering

A design system is a set of governed decisions, not a pile of variables.

## Establish authority
Inspect existing token files, theme providers, component library, Figma variables, and usage patterns. Record exact paths and names. Do not invent a token or component and imply it exists.

## Foundations
Define semantic roles for:
- color and contrast pairs;
- typography and text roles;
- spacing and layout rhythm;
- grid, container, and breakpoints;
- radii, borders, elevation, and layering;
- icon family and sizing;
- motion durations, easing, and reduced-motion behavior.

## Component contract
For each component document purpose, anatomy, variants, sizes, states, accessibility semantics, responsive behavior, content constraints, and usage/do-not-use guidance. Include real examples and anti-examples.

## Governance
- Prefer semantic tokens over raw values in components.
- Avoid near-duplicate tokens and one-off variants.
- Make exceptions explicit and scoped.
- Keep light and dark themes semantically aligned, not mechanically inverted.
- Ensure component variants represent meaningful behavior or hierarchy.
- Document migration/deprecation when changing shared contracts.

## Audit
Find token drift, inconsistent geometry, duplicate primitives, invalid contrast pairs, undocumented variants, and components that bypass the system. Prioritize fixes by user impact and blast radius.
