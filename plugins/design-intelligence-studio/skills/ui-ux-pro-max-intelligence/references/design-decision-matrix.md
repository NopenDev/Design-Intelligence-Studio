# Design decision matrix

Score candidate directions against the actual product, not popularity. Use qualitative Low/Medium/High and cite evidence.

| Dimension | Questions |
|---|---|
| Product fit | Does the style support the domain, user expectation, and task? |
| Distinctiveness | Is there a deliberate product-specific signature, not template chrome? |
| Readability | Can users scan real content at realistic lengths and densities? |
| Accessibility | Can contrast, focus, keyboard, zoom, and reduced motion be supported? |
| Responsive resilience | Does the information architecture survive narrow and short viewports? |
| Implementation fit | Can the existing stack and component system support it without needless dependencies? |
| Maintainability | Can the direction be expressed as reusable tokens and component rules? |

Reject any direction that fails task clarity or accessibility, even if visually distinctive. A high-fashion concept that harms the primary workflow is not a good product design.

## Baseline token roles
- Color: `background`, `surface`, `surface-raised`, `text-primary`, `text-secondary`, `border`, `primary`, `on-primary`, `success`, `warning`, `danger`, `focus`.
- Type: `display`, `heading-1..n`, `body`, `body-small`, `label`, `caption`, `numeric`.
- Space: named scale, not isolated magic numbers.
- Shape: separate roles for controls, cards/panels, overlays, and pills/badges.
- Motion: quick feedback, standard transition, deliberate transition; reduced-motion alternative.
- Elevation: semantic levels only; avoid shadow on every container.
