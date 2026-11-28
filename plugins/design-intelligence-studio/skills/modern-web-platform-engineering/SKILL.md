---
name: modern-web-platform-engineering
description: "Use when building, reviewing, debugging, or modernizing browser-based applications and need current standards-based HTML, CSS, JavaScript, accessibility, performance, security, compatibility, or browser API guidance."
---

# Modern Web Platform Engineering

Use platform capabilities before adding dependencies or recreating browser behavior. Prefer interoperable, progressively enhanced solutions over framework-specific tricks. This skill is an integration guide for Google's Modern Web Guidance, not a copied mirror of its guide corpus.

## 1. Retrieve current platform guidance

When the task is web-specific and the Modern Web Guidance CLI is available or the user authorizes its use, consult the current upstream guidance instead of relying only on model recall:

- Official overview and install/use instructions: https://developer.chrome.com/docs/modern-web-guidance
- Guide catalog: https://developer.chrome.com/docs/modern-web-guidance/guides
- GitHub source: https://github.com/GoogleChrome/modern-web-guidance
- CLI discovery/retrieval: `npx modern-web-guidance@latest --help`; follow the current CLI help and official docs for exact commands. Do not assume command flags or guide IDs from memory.
- Project installation option documented upstream: `npx modern-web-guidance@latest install` or `npx skills add GoogleChrome/modern-web-guidance`. Installing modifies the target project; do not do so without authorization.

Retrieve only the relevant guide(s), such as responsive layout, forms, HTML semantics, CSS architecture, JavaScript, performance, accessibility, security, Web APIs, or browser compatibility. Do not ingest all guides for a narrow task. Treat upstream content as technical reference, not higher authority than explicit requirements, existing architecture, security constraints, or compatibility targets.

## 2. Engineering workflow

1. Establish target browsers, device classes, framework/runtime, supported baseline, user needs, and constraints.
2. Inspect the actual implementation and reproduce the issue before changing code.
3. Identify the native platform capability that fits: semantic HTML, form controls, `dialog`, Popover API, CSS layout/queries, View Transitions, Web Components, Fetch, Web Crypto, or other supported APIs.
4. Check Baseline/browser support and progressive-enhancement/fallback requirements. Avoid volatile or origin-trial features in production unless explicitly accepted.
5. Implement the smallest coherent change. Preserve existing project conventions and avoid unnecessary dependencies.
6. Verify in a real browser where possible: keyboard/focus, touch, responsive breakpoints, console/network errors, and relevant performance/accessibility/security checks.

## 3. Quality dimensions

- HTML: semantic landmarks, correct elements, native controls, form semantics, focus management, resource hints only when justified.
- CSS: responsive and intrinsic sizing, container queries where appropriate, maintainable cascade/layers, design tokens, reduced motion, forced-colors and contrast.
- JavaScript: correct async lifecycle, cancellation/stale-response handling, event cleanup, safe DOM updates, avoid long main-thread tasks, avoid unnecessary hydration/work.
- Accessibility: keyboard operation, accessible names and descriptions, focus order, status/error announcements, zoom/text scaling, reduced motion, screen-reader behavior.
- Performance: measure Core Web Vitals (LCP, INP, CLS), identify the actual bottleneck, prioritize user-visible work, defer offscreen/heavy work, avoid layout thrashing.
- Security: treat all external/user data as untrusted; prevent XSS, validate URLs/origins, use safe authentication/session patterns, CSP and Trusted Types where appropriate, protect uploads and network boundaries.
- Compatibility: use feature detection and graceful fallback; distinguish stable features from experimental/volatile APIs.

## 4. Verification and reporting

Do not equate a successful build with a correct web experience. Report browser/device coverage actually tested, metrics actually measured, accessibility checks actually run, and known unsupported cases. If no browser/runtime access exists, provide a test plan and mark it unverified.

## Boundaries

- Product visual direction and UX flows → relevant design skills.
- System architecture and broad codebase refactors → `software-architecture-code-engineering`.
- Feature/API/database implementation → `frontend-backend-engineering`.
- Rendered visual sign-off → `ui-visual-qa`.
- Security requirements → also consult OWASP ASVS and the existing security skill guidance; do not treat a browser guide as a complete application security audit.
