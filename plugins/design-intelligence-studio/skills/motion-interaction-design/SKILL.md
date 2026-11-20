---
name: motion-interaction-design
description: "Use when designing animation, transitions, micro-interactions, gesture behavior, loading feedback, or perceived-performance behavior."
---

# Motion and Interaction Design

Motion must communicate intent. It should explain a state change, acknowledge input, preserve spatial continuity, or guide attention. If removing it loses no useful signal, remove it.

## Three decisions before implementation
1. What should the user understand or feel?
2. What changed in the interface or system?
3. What is the least motion that communicates that change?

## Interaction contract
For each async interaction, explicitly choose optimistic or pessimistic behavior based on failure cost, reversibility, and latency. Specify pending feedback, success/error, recovery, keyboard path, and focus destination.

## Motion guidance
- Use entrance deceleration and exit acceleration; use linear motion only for constant-rate progress/rotation.
- Keep high-frequency feedback fast and non-blocking.
- Prefer transform/opacity for animation performance; avoid layout reflow.
- Keep sequences short and interruptible.
- Use consistent motion tokens and easing per product.
- Respect `prefers-reduced-motion` and platform settings.
- Do not animate every card, section, or hover by default.

## Review
For every animation, name its communicative purpose. Check that it does not delay input, hide focus, cause layout shift, or compete with content. Test rapid repeated actions and cancellation.

Inspired by LottieFiles Motion Design Skill (MIT); this skill is a compact independent workflow, not a copy of its full reference library.
