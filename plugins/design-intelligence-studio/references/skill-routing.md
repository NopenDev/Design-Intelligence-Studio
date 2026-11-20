# Skill routing and conflict resolution

This plugin contains exactly 14 independently discoverable skills. Route by the user's actual task, not by keyword coincidence. Load multiple skills only when the task crosses their ownership boundaries.

## Skill catalog

| # | Skill | Primary responsibility |
|---:|---|---|
| 1 | `ui-ux-pro-max-intelligence` | UI/UX Intelligence: product analysis, design intelligence, and skill orchestration |
| 2 | `frontend-art-direction` | Distinct visual direction and visual concept |
| 3 | `product-ux-and-flows` | User journeys, behavior, navigation, and information architecture |
| 4 | `design-system-engineering` | Design tokens, themes, components, and governance |
| 5 | `visual-design-foundations` | Typography, color, layout, hierarchy, icons, and basic chart presentation |
| 6 | `motion-interaction-design` | Motion, transitions, micro-interactions, and interaction feedback |
| 7 | `responsive-accessibility` | Responsive behavior and accessibility |
| 8 | `figma-to-interface` | Design-to-code implementation while preserving design fidelity |
| 9 | `ui-visual-qa` | Evidence-based visual verification and sign-off |
| 10 | `anti-slop-ui-audit` | Audit generic patterns, weak hierarchy, and unjustified decoration |
| 11 | `software-architecture-code-engineering` | System architecture, codebase understanding, maintainability, refactoring, and engineering quality |
| 12 | `frontend-backend-engineering` | Application implementation across frontend, APIs, services, auth, and persistence |
| 13 | `gis-mapping-engineering` | Spatial data, GIS pipelines, map services, web maps, and cartography |
| 14 | `data-visualization-analytics` | Dataset exploration, metric definition, quantitative analysis, and dashboards |

## Routing by task

- New product, ambiguous design brief, or product-wide UI/UX decisions → `ui-ux-pro-max-intelligence`; pair with `frontend-art-direction` when a new visual identity is required.
- Screen flow, onboarding, navigation, forms, or workflow behavior → `product-ux-and-flows`.
- Tokens, component contracts, themes, or reusable UI → `design-system-engineering`.
- Typography, color, spacing, hierarchy, image/icon use, or basic chart styling → `visual-design-foundations`.
- Animation, gestures, transitions, optimistic/pessimistic feedback, reduced motion → `motion-interaction-design`.
- Mobile/tablet/desktop adaptation, keyboard and assistive technology → `responsive-accessibility`.
- Supplied Figma/screenshot/spec to implementation → `figma-to-interface`; add `frontend-backend-engineering` for behavior and API wiring.
- Rendered page review, visual regression, evidence-based sign-off → `ui-visual-qa`.
- Generic AI-looking UI, unjustified bento/card/gradient patterns, invented tokens → `anti-slop-ui-audit`.
- System boundaries, architecture selection, repository archaeology, dependency direction, refactor strategy, code quality → `software-architecture-code-engineering`.
- Implementing application features, UI components, APIs, auth, database integration, or end-to-end behavior → `frontend-backend-engineering`.
- Spatial datasets, CRS, spatial SQL, map providers/layers, routing, web maps, thematic maps → `gis-mapping-engineering`.
- Data cleaning/exploration, statistical analysis, KPI definitions, chart selection, analytical dashboard → `data-visualization-analytics`.

## Orchestration patterns

- Product delivery from brief to release: #1 → #3 → #2/#4/#5/#6/#7 as needed → #11 for architecture decisions → #12 for implementation → #8 when a supplied design is the source → #9 for rendered QA; run #10 when there is a credible risk of generic or ungrounded UI.
- Spatial product: #1/#3 for user need and IA → #11 for system boundaries when needed → #13 for spatial data and map architecture → #12 for non-spatial application/API code → #9 for UI verification.
- Analytics product: #3 for dashboard audience and decision flow → #11 for data/system boundaries when needed → #14 for metric semantics and analysis → #5/#4 for visual presentation and reusable components → #12 for implementation → #9 for rendered QA.

Do not invoke every skill by default. Use the smallest set that covers the task. #11 decides architectural structure; #12 implements code. #13 owns spatial semantics; #14 owns non-spatial analytical semantics. #5 provides visual foundations but does not replace analytical method selection.

## Authority and conflict resolution

1. Explicit user requirements and supplied specifications.
2. Existing verified product architecture, design system, data contracts, and security boundaries.
3. Platform, accessibility, legal, licensing, and operational constraints.
4. Evidence from the repository, data, and runtime.
5. Narrow specialist skill guidance.
6. Generic preferences or trends.

- Do not change behavior when asked only for visual polish or review.
- Do not invent repository structure, tokens, API behavior, datasets, metrics, sources, user research, or compliance claims.
- Separate confirmed defects from subjective improvements and hypotheses.
- Preserve unrelated files and behavior; scope changes explicitly.
- Never claim build, visual QA, accessibility, GIS validation, statistical significance, or production verification that was not actually performed.
- Do not modify production data, run destructive migrations, or deploy without explicit authorization.
