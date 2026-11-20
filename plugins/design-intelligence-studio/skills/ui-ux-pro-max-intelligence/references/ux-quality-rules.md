# UX quality rules

## Accessibility
- Normal text contrast target at least 4.5:1; large text at least 3:1 (verify actual pairs).
- Visible keyboard focus; never remove outline without a better replacement.
- Semantic headings, labels, buttons, links, landmarks, and form associations.
- Meaningful images have alternatives; decorative imagery is ignored by assistive tech.
- State is not conveyed by color alone.
- Respect reduced motion, zoom, text scaling, and keyboard-only operation.
- Drag and gesture actions need alternatives.

## Touch and interaction
- Use comfortable target sizes; platform guidance differs (e.g. Apple points vs Android dp vs WCAG CSS px). Do not conflate units.
- Never make essential actions hover-only.
- Provide immediate acknowledgement, pending feedback, success/failure, and recovery.
- Preserve keyboard focus through dialogs, validation, and async state changes.

## Responsive
- Design behavior per breakpoint: reorder, collapse, overflow, sticky, or move controls intentionally.
- Test long labels, localization, empty states, error text, dense tables, and short viewport height.
- Avoid horizontal scrolling unless it is intrinsic to the task and has clear affordance.

## Forms and navigation
- Visible labels; errors next to fields and linked programmatically.
- Preserve entered data after recoverable errors.
- Destructive actions need clear consequence and confirmation when irreversible.
- Back behavior, active navigation, and current location must be predictable.
