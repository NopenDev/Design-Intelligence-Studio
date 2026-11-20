---
name: frontend-backend-engineering
description: "Use when implementing or changing application code across frontend interfaces, backend services, APIs, authentication, database integration, or end-to-end feature behavior."
---

# Frontend & Backend Engineering

Implement application behavior against the product's approved UX and architecture. This skill owns code delivery across the UI-to-data path; it does not invent the visual direction or redesign the system architecture by default.

## 1. Read before changing

Inspect the repository and establish:
- framework, language, runtime, package manager, scripts, and directory conventions;
- existing component, routing, state, API-client, service, persistence, and validation patterns;
- authentication and authorization boundaries;
- environment variables and deployment/runtime assumptions;
- available tests, fixtures, migrations, and code-generation workflows.

Use existing patterns unless they are demonstrably defective. Identify the smallest files and boundaries that need to change. Avoid unrelated refactors.

## 2. Frontend implementation

- Translate the approved flow and design into semantic, maintainable components.
- Keep state near its owner; separate ephemeral UI state from server/cache state.
- Define loading, empty, error, success, disabled, permission-denied, and retry states where applicable.
- Use typed or otherwise explicit API boundaries; validate untrusted data at the boundary.
- Handle async work with cancellation/stale-response protection where needed, visible pending feedback, and safe optimistic updates only when failure is recoverable.
- Preserve keyboard operation, visible focus, accessible names, responsive layout, and reduced-motion preferences.
- Avoid hidden business rules in presentation components. Keep formatting and derived display values separate from authoritative domain logic.

## 3. Backend and API implementation

- Model endpoints around resources and use cases; validate request parameters, payloads, and identity at the server boundary.
- Enforce authorization server-side on every protected operation. UI hiding is not access control.
- Keep business rules in services/domain logic, not duplicated across route handlers and clients.
- Use parameterized database operations, explicit transaction boundaries, bounded pagination, and indexes justified by query patterns.
- Design external calls with timeouts, bounded retries, backoff, idempotency where duplicate execution is possible, and clear failure classification.
- Use consistent response/error contracts without exposing secrets, internal stack traces, or sensitive data.
- Treat migrations, background jobs, webhooks, and realtime flows as first-class parts of the feature.

## 4. Security and reliability baseline

Check authentication versus authorization, tenant/user scoping, input validation, output encoding, CSRF/CORS assumptions, rate limits, secret handling, file upload constraints, SSRF-sensitive URL handling, and audit logging when relevant. Use least privilege. Never trust client-supplied role, owner, price, or permission claims without server verification.

Do not add a security mechanism blindly: verify how the current stack handles sessions, cookies, tokens, origin checks, and deployment secrets before changing them.

## 5. Implementation and verification loop

1. State the behavior change and acceptance criteria.
2. Write or update tests for the observable behavior and edge cases.
3. Implement the smallest coherent vertical slice.
4. Run targeted tests, then relevant type/lint/build checks.
5. Exercise the real path across browser/client → API → persistence or external dependency → response.
6. Inspect logs and error paths when available; do not infer success from a successful build alone.
7. Summarize changed files, behavior, checks run, failures, and remaining risks.

For an existing defect, reproduce it and trace the first incorrect boundary before editing. Do not patch symptoms at both client and server unless both contain independent defects.

## Output contract

For feature work, provide a compact implementation plan, affected boundaries, acceptance tests, and any migration or configuration requirements. For completed work, report exact verification evidence. For code review, identify the file/location, exploitability or user impact, severity, and a specific fix.

## Boundaries and routing

- System decomposition, architecture selection, ADRs, large refactors → `software-architecture-code-engineering`.
- Visual concept, design system, information architecture, accessibility policy → the relevant UI/UX skill.
- Map components, spatial services, coordinate systems, geospatial queries → `gis-mapping-engineering`.
- Statistical analysis, chart selection, dashboard metric semantics → `data-visualization-analytics`.
- Do not fabricate API behavior, test output, deployment success, or data state. Never run a production migration, destructive action, or deployment without explicit authorization.
