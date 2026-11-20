---
name: figma-to-interface
description: "Use when implementing a UI from Figma, screenshots, a design spec, or a supplied visual reference while preserving design fidelity."
---

# Figma to Interface

Treat the supplied design as the source of truth unless the user explicitly requests critique or redesign.

## Workflow
1. Identify exact file/page/frame and target viewport. Confirm what is in scope.
2. Inspect component library, variables/tokens, typography, spacing, assets, variants, and auto-layout constraints.
3. Map design components to existing code components. Record gaps instead of silently substituting.
4. Implement in layers: structure → layout → tokens/styles → interactions → responsive behavior → accessibility.
5. Preserve content, hierarchy, spacing, geometry, and component states. Avoid approximating details that can be read from the design.
6. Compare rendered output against the source at matching dimensions. Fix high-impact drift and reinspect.
7. Report what matched, what required interpretation, and what could not be verified.

## Fidelity rules
- Do not invent a design system when the file already defines one.
- Do not use a screenshot as permission to change product behavior.
- Do not claim pixel-perfect fidelity without a same-size visual comparison.
- If an asset is missing, name the gap and ask or use an explicitly approved substitute.
- Respect existing repository conventions and avoid unrelated refactors.
