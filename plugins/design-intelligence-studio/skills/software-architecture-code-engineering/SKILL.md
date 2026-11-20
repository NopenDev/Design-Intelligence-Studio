---
name: software-architecture-code-engineering
description: "Use when designing or reviewing software architecture, inspecting an existing codebase, making structural engineering decisions, improving maintainability, planning refactors, or defining code-quality and testing boundaries."
---

# Software Architecture & Code Engineering

Own system structure and engineering quality. Produce decisions that can be inspected, tested, and evolved. Do not jump from a vague request directly to a framework choice or a large rewrite.

## 1. Establish the evidence base

For an existing repository, inspect its actual files before making claims:
- identify entry points, runtime, framework, package manager, build/test commands, and deployment target;
- map major modules, dependencies, data stores, external services, and request/event flows;
- locate configuration, environment handling, migrations, tests, CI, and observability;
- distinguish active code from generated files, examples, stale modules, and unused dependencies.

Cite paths, symbols, call sites, tests, or observed runtime behavior for important findings. Mark assumptions and unknowns explicitly. Do not infer architecture solely from directory names or README claims.

For greenfield work, first establish product constraints: users, workloads, data sensitivity, consistency needs, expected scale, latency, availability, team size, deployment constraints, budget, and operational capability. Ask only for decisions that materially change the architecture; otherwise state bounded assumptions.

## 2. Design the architecture

1. Translate product goals into quality attributes and measurable scenarios (for example, p95 latency under a stated load, recovery objective, or acceptable data staleness).
2. Define system boundaries, responsibilities, ownership of data, trust boundaries, and external dependencies.
3. Choose the simplest viable shape. Prefer a modular monolith until independent deployment, scaling, team ownership, or fault isolation justifies services.
4. Define dependency direction and stable interfaces. Keep domain rules independent of transport, framework, and persistence details where the cost is justified.
5. Model synchronous and asynchronous flows, state transitions, transaction boundaries, retries, idempotency, ordering, and failure modes.
6. Compare alternatives by trade-offs, migration cost, operational burden, reversibility, and evidence—not fashion.
7. Record consequential decisions as concise ADRs: context, decision, alternatives, consequences, and revisit triggers.

## 3. Engineer code for change

- Optimize for cohesion, explicit contracts, low accidental coupling, and understandable control flow.
- Keep abstractions proportional to demonstrated repetition or change pressure; avoid speculative layers and generic frameworks.
- Separate business rules from I/O and framework orchestration when this improves testability or change isolation.
- Prefer small, reviewable changes with clear ownership over broad rewrites.
- Make invariants explicit and validate them at trust boundaries.
- Handle errors at the layer with enough context to recover or report them; preserve actionable context without leaking secrets.
- Treat configuration, migrations, dependency upgrades, and compatibility as part of the change.

## 4. Quality and verification

Choose tests by risk and boundary:
- unit tests for deterministic domain rules;
- integration tests for persistence, queues, external adapters, and transaction behavior;
- contract tests for interfaces with independent consumers;
- end-to-end tests for critical user journeys;
- performance, resilience, and security tests where their risks justify them.

Before refactoring, capture behavior with tests or another explicit baseline. Preserve behavior unless a behavior change was requested. Verify formatting, lint, type checks, tests, build, migration safety, and the affected runtime flow. Report the exact commands run and their results; do not claim checks that were not executed.

## 5. Output contract

For substantial architecture work, provide:
- repository evidence or stated assumptions;
- current/target boundaries and a concise component/data-flow map;
- decision table with trade-offs and a recommendation;
- risks, failure modes, security and operational implications;
- phased implementation plan with rollback/migration notes;
- acceptance and verification criteria.

For code-quality reviews, rank findings by severity and include file/location, evidence, impact, and a concrete correction. Separate confirmed defects from optional improvements.

## Boundaries and routing

- Product journeys and information architecture → `product-ux-and-flows`.
- Visual direction, tokens, components, and motion → the relevant UI/UX skill.
- Implementing a specific frontend/backend feature or API → `frontend-backend-engineering`.
- GIS-specific data systems and map behavior → `gis-mapping-engineering`.
- Dataset exploration and analytical storytelling → `data-visualization-analytics`.
- Do not rewrite or deploy production systems, alter production data, or perform destructive migrations without explicit authorization.
