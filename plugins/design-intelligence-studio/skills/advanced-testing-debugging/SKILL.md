---
name: advanced-testing-debugging
description: "Use when designing test strategy, reproducing defects, debugging flaky or failing systems, preventing regressions, or validating browser and end-to-end behavior."
---

# Advanced Testing & Debugging

Own test design and defect diagnosis. The objective is trustworthy evidence about observable behavior, not maximizing test count or producing green checks that miss real failures.

## 1. Establish the failure or risk

- Clarify expected versus actual behavior, affected users, environment, frequency, and severity.
- Inspect the repository's test runner, scripts, fixtures, CI configuration, logs, and runtime setup before choosing tools.
- Reproduce the issue with the smallest deterministic input or sequence. Record exact steps, environment, timestamps, and relevant logs.
- Separate symptoms, hypotheses, confirmed causes, and unknowns. Do not patch until the first incorrect boundary is identified when feasible.

## 2. Choose the right test portfolio

- Unit tests: deterministic domain rules, parsers, transformations, and edge cases.
- Integration tests: database, filesystem, queues, external adapters, transactions, and service boundaries.
- Contract tests: API schemas and compatibility between independently evolving consumers.
- End-to-end tests: a small set of critical user journeys through the real application path.
- Property-based tests: invariants across generated inputs where useful.
- Performance/load tests: measured bottlenecks and stated workload assumptions.
- Security tests: trust boundaries, authorization, validation, and abuse cases.

Use the test pyramid as a heuristic, not a rigid ratio. Keep most behavior checks fast and focused; reserve browser E2E for behavior that genuinely requires the full stack.

## 3. Make tests robust

- Assert externally observable behavior rather than private implementation details.
- Isolate state, users, sessions, data, and test ordering; tests should be independently repeatable.
- Prefer semantic locators and accessible roles over brittle CSS/XPath selectors in browser tests.
- Use framework-native waiting and retryable assertions; avoid arbitrary sleeps.
- Control clocks, randomness, network dependencies, and fixtures where deterministic behavior matters.
- Test success, validation failure, permission denial, empty state, timeout, retry, duplicate submission, and partial failure where relevant.
- Keep test data representative but non-sensitive; never copy production secrets or personal data into fixtures.

## 4. Debug systematically

1. Capture the exact failure and preserve the failing test/log/trace.
2. Identify the smallest layer where expected and actual behavior diverge.
3. Form competing hypotheses and rank them by evidence and test cost.
4. Run a discriminating experiment that can falsify a hypothesis.
5. Inspect boundary data: request/response, state transition, SQL query/plan, network timing, browser console, or dependency output as appropriate.
6. Fix the root cause with the smallest coherent change.
7. Add a regression test that fails before the fix and passes after it.
8. Run targeted tests, related suites, and build/type/lint checks; inspect the actual result.

For browser defects, inspect console errors, failed requests, status codes, CORS/cookie behavior, DOM state, viewport, and timing. For intermittent failures, look for shared mutable state, race conditions, non-idempotent setup, time dependence, resource contention, and network instability.

## 5. Flaky tests and CI

- Do not hide flakiness by blindly increasing timeouts or adding retries.
- Use retries as a diagnostic signal; track first-run failures separately from recovered retries.
- Capture traces, screenshots, network logs, and environment metadata on failure.
- Keep CI jobs reproducible and avoid test-order dependence.
- Parallelize only when tests are isolated and shared resources are controlled.

## 6. Output contract

Report reproduction steps, confirmed root cause (or remaining hypotheses), changed files, regression coverage, exact commands and results, and residual risk. Distinguish tests authored from tests executed. Never claim runtime, browser, load, or security validation that was not performed.

## Boundaries

- Feature implementation → `frontend-backend-engineering`.
- System structure and refactor strategy → `software-architecture-code-engineering`.
- Browser standards and platform behavior → `modern-web-platform-engineering`.
- Database concurrency and query semantics → `database-distributed-systems-engineering`.
- AI-specific stochastic quality evaluation → `ai-engineering-evaluation`.
