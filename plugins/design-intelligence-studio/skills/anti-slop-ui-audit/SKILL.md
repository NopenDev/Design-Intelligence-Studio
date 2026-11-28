---
name: anti-slop-ui-audit
description: "Use when reviewing a UI for generic AI-generated patterns, framework-default styling, unnecessary decoration, weak hierarchy, or invented design-system elements."
---

# Anti-Slop UI Audit

Anti-slop is a diagnostic discipline, not a universal style ban. The objective is to catch unconsidered defaults while preserving deliberate visual direction.

## Run the checklist item by item
1. **Framework-default chrome:** unmodified framework look with no product-specific decisions.
2. **Flat hierarchy:** title, body, labels, and actions compete at the same level.
3. **Centered-everything:** no intentional alignment or grid logic.
4. **Fake content:** lorem ipsum, generic names, implausible metrics, or unrealistic data shapes.
5. **Missing states:** no meaningful empty, error, disabled, or recovery states.
6. **Hover-only behavior:** essential actions lack keyboard/touch alternatives.
7. **Spacing drift:** arbitrary spacing values conflict with the real scale.
8. **Invented system elements:** tokens, classes, or components are referenced without verifying they exist.
9. **Generic copy:** vague marketing language or cheerful filler in utility interfaces.
10. **Missing async feedback:** no pending state or acknowledgement for slow actions.
11. **Inconsistent behavior:** same action works differently across surfaces without reason.
12. **Cardification:** nested or identical cards where layout and spacing would suffice.
13. **Decoration by reflex:** gradient, glow, bento, pills, micro-labels, or motion added without a functional or brand reason.
14. **Dashboard-by-default:** metrics, sidebar, or charts added without a decision need.
15. **Scattered actions:** same-scope actions split across unrelated regions.

## Output discipline
For each finding, quote the offending element or describe its exact location, explain why it is a problem in this context, and name the owning correction. Do not report a pattern merely because it is popular. A deliberate gradient or card can pass when justified by product, brand, content, or hierarchy.

## Correction order
Fix the earliest structural issue with the largest impact: task clarity → hierarchy → information grouping → spacing → typography → action placement → states → responsive behavior → accessibility → decorative polish.

## False-positive control
A clean surface may have zero findings. Do not manufacture issues to appear thorough. Separate confirmed defects from subjective opportunities. Preserve user-specified design direction and existing system authority.


---
Available file URIs for this installed plugin skill. Use these exact URIs when reading files:

skills://plugins/design-intelligence-studio/anti-slop-ui-audit/skill.md
skills://plugins/design-intelligence-studio/anti-slop-ui-audit/references/anti-slop-patterns.md