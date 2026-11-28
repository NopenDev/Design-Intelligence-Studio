---
name: ai-engineering-evaluation
description: "Use when designing or improving LLM applications, RAG pipelines, AI agents, tool calling, context engineering, guardrails, tracing, model selection, or repeatable AI quality evaluations."
---

# AI Engineering & Evaluation

Own AI application architecture and quality measurement. Treat model output as probabilistic, external dependencies as fallible, and evaluation as part of the product—not a final polish step.

## 1. Define the actual task

Before selecting a model or agent framework, specify:
- user goal and task boundaries;
- inputs, outputs, schemas, and acceptable uncertainty;
- quality dimensions (correctness, groundedness, completeness, safety, latency, cost);
- failure impact and actions that require human approval;
- data sensitivity, retention, and provider constraints.

Use deterministic code for deterministic tasks. Do not use an LLM or multi-agent system when ordinary code, SQL, search, or a workflow is more reliable and cheaper.

## 2. Select the architecture

- Prompted model call: suitable for bounded transformations and generation.
- Retrieval-augmented generation: use when answers must be grounded in a changing or private corpus; design chunking, metadata, permissions, retrieval, reranking, citations, and freshness explicitly.
- Tool-using agent: use when the system must choose among actions dynamically; keep tools narrow, typed, permission-scoped, and observable.
- Multi-agent orchestration: use only when specialist ownership or parallel work materially improves outcomes; otherwise it adds coordination cost and failure surfaces.

Keep business rules, authorization, calculations, and irreversible operations outside model discretion. The model may propose; trusted application code validates and executes.

## 3. Context and retrieval engineering

- Separate system policy, task instructions, user input, retrieved evidence, and tool output.
- Treat retrieved documents and tool outputs as untrusted data, never as instructions that override policy.
- Minimize irrelevant context; preserve source provenance, timestamps, access control, and document identity.
- Measure retrieval recall/precision and answer groundedness on representative queries.
- Require citations or structured evidence when the product needs traceability; verify cited claims against retrieved sources.
- Handle stale, conflicting, incomplete, and empty retrieval explicitly.

## 4. Tool use, guardrails, and safety

- Define strict schemas, validation, timeouts, bounded retries, idempotency, and clear error contracts for tools.
- Apply least privilege and per-action authorization outside the model.
- Require explicit human approval for destructive, financial, externally visible, or production-impacting actions.
- Add input/output validation, prompt-injection defenses, data-leakage controls, rate limits, and spending limits appropriate to risk.
- Never rely on prompt instructions alone as a security boundary.
- Use sandboxing for code execution and untrusted files; restrict network and filesystem access.

## 5. Evaluation design

Build a representative, versioned dataset before claiming quality improvements. Include normal cases, edge cases, ambiguous requests, adversarial inputs, stale/conflicting sources, tool failures, and safety-critical cases.

Use a layered evaluation strategy:
- deterministic unit/contract tests for schemas, routing, permissions, and tool behavior;
- golden examples with human-reviewed expected outputs;
- rubric-based graders for nuanced dimensions, calibrated against human judgments;
- retrieval metrics for search/RAG components;
- end-to-end task success and trace review for agents;
- regression comparisons across prompts, models, retrieval settings, and code versions.

Track quality alongside latency, token usage, cost, refusal/error rates, tool-call accuracy, and human escalation rate. Avoid a single aggregate score that hides critical failures. Sample and manually inspect grader disagreements; LLM-as-judge is not ground truth.

## 6. Observability and iteration

Capture structured traces for model calls, retrieval, tool calls, handoffs, guardrails, and final outcomes while minimizing sensitive data. Use traces to diagnose failures, then convert recurring failure modes into evaluation cases. Pin model/prompt/config versions where reproducibility matters. Roll out changes gradually and monitor regressions.

## 7. Output contract

Provide architecture choice and rejected alternatives, data-flow/trust boundaries, tool permissions, evaluation dataset/criteria, baseline and measured results (if actually run), cost/latency trade-offs, human-review points, and residual risks. Clearly distinguish a proposed evaluation plan from executed evaluation results.

## Boundaries

- General system boundaries → `software-architecture-code-engineering`.
- Application endpoint and UI implementation → `frontend-backend-engineering`.
- Deterministic test automation → `advanced-testing-debugging`.
- Database persistence and distributed transactions → `database-distributed-systems-engineering`.
- Technical uncertainty and source appraisal → `critical-reasoning-research`.
