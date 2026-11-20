---
name: responsive-accessibility
description: "Use when designing or auditing mobile, tablet, desktop, adaptive layouts, accessibility, keyboard interaction, touch targets, or inclusive content."
---

# Responsive and Accessible UI

## Responsive behavior
Do not simply shrink desktop. Decide what reorders, collapses, becomes sticky, moves to a sheet/menu, or is deprioritized. Preserve the primary task and context at every breakpoint. Check narrow widths, short viewport heights, long labels, dense data, localization, and text zoom.

## Accessibility gate
- Use semantic HTML/native controls where appropriate.
- Ensure keyboard access and visible focus.
- Keep focus visible and not obscured by sticky UI or overlays.
- Provide accessible names and programmatic labels.
- Associate errors and helper text with their fields.
- Do not use color as the only state signal.
- Provide text alternatives for meaningful images and hide decorative images from assistive tech.
- Respect reduced motion, zoom, and text scaling.
- Provide non-drag and non-gesture alternatives for important actions.
- Ensure touch targets and spacing meet the relevant platform/standard; distinguish CSS px, pt, and dp.

## Test scenarios
1. Keyboard-only navigation and dialog open/close focus return.
2. Screen-reader names, roles, values, and status announcements.
3. 200% zoom / enlarged text and long localized strings.
4. Mobile touch and orientation changes.
5. Reduced-motion preference.
6. Empty, invalid, disabled, loading, and error states.
7. High-contrast or forced-colors behavior where relevant.

Never claim WCAG compliance from visual inspection alone. Report which checks were performed and which remain unverified.
