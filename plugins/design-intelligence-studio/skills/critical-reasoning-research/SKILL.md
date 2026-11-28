---
name: critical-reasoning-research
description: "Use when a task requires rigorous problem framing, evaluating competing explanations or designs, technical research, evidence quality, trade-off analysis, or a defensible recommendation."
---

# Critical Reasoning & Technical Research

The goal is a decision that survives scrutiny, not an answer that merely sounds confident. Challenge assumptions constructively and distinguish evidence from inference.

## 1. Frame the decision

- Define the actual question, desired outcome, constraints, and decision owner.
- Separate symptoms from root causes and goals from proposed solutions.
- List known facts, unknowns, assumptions, and constraints.
- Identify what evidence would change the conclusion.
- Avoid expanding scope beyond what is needed to decide or solve the problem.

## 2. Analyze alternatives

Generate at least two credible approaches for consequential decisions. Compare them using task-relevant criteria: correctness, complexity, reliability, security, performance, maintainability, compatibility, cost, reversibility, and operational burden. Weight criteria explicitly when they conflict. Include a baseline/no-change option when useful.

Use causal reasoning: trace mechanisms and dependencies; distinguish correlation from causation; consider confounders, feedback loops, failure modes, and second-order effects. Test counterexamples and the strongest objection to the leading option. Avoid false dichotomies and appeal to popularity or novelty.

## 3. Research evidence

Prefer primary sources: official standards/specifications, platform documentation, original papers, source repositories, and reproducible measurements. Use secondary sources to interpret or compare, not to replace primary evidence. Check publication/update date, scope, version, methodology, incentives, and whether the evidence applies to the user's environment. Cross-check important claims. Cite factual claims and mark uncertain or disputed points.

For codebase questions, inspect repository files, tests, configuration, call sites, and runtime evidence. Do not infer implementation from a README alone. For empirical claims, state sample size, measurement conditions, and limitations when known.

## 4. Decision and calibration

- State the recommendation and the conditions under which it holds.
- Explain the decisive trade-offs and rejected alternatives briefly.
- Assign confidence qualitatively (high/medium/low) based on evidence, not rhetorical certainty.
- Identify residual risks, unknowns, and a practical validation step.
- If evidence is insufficient, say what is missing instead of fabricating precision.

## 5. Technical problem-solving loop

Observe → define → hypothesize → derive testable predictions → test → inspect counterevidence → revise → verify. For debugging, reproduce first, trace the earliest incorrect state/boundary, isolate variables, and test the smallest fix. Do not patch downstream symptoms without identifying the cause.

## Output contract

Use a compact structure when appropriate: problem definition, evidence, assumptions, options, trade-off table, recommendation, confidence, risks, and verification. For simple questions, answer directly without forcing this structure.
