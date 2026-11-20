---
name: ui-visual-qa
description: "Use when asked to inspect, critique, verify, or sign off a UI, especially after material frontend changes or when screenshots/browser rendering are available."
---

# UI Visual QA

A successful build is not proof of a good interface. Verify the rendered experience and distinguish observed evidence from assumptions.

## Review protocol
1. Confirm the target screen, user task, source design, and project design authority.
2. Inspect desktop and realistic mobile widths; include short viewport height when relevant.
3. Compare against Figma/screenshots when supplied. Identify drift rather than redesigning without permission.
4. Exercise realistic content: long labels, dense lists, empty data, invalid fields, attachments, loading, errors, success, disabled, and permissions.
5. Check hierarchy, spacing rhythm, alignment, component geometry, action grouping, responsive reflow, accessibility, and motion.
6. Record findings by impact: blocker, high, medium, low. Each finding includes location, evidence, user impact, and concrete correction.
7. For build/polish work, fix in-scope failures and reinspect. For review-only tasks, report without editing.
8. State unverified checks explicitly. Never claim screenshot/browser review if it did not happen.

## Acceptance checklist
- Primary task and action are immediately clear.
- Existing design system and vocabulary are preserved.
- No unjustified invented tokens/components.
- Realistic content does not break layout.
- Relevant empty/error/loading/success states exist.
- Keyboard focus, accessible names, and reduced motion are handled.
- Mobile actions remain reachable and usable.
- Visual hierarchy is intentional; decorative noise is removed.
- No unrelated refactor was introduced under the label of polish.
