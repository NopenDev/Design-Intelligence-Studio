---
name: algorithmic-problem-solving
description: "Use when designing, selecting, explaining, implementing, or optimizing algorithms and data structures, analyzing complexity, debugging logic, or solving computational problems."
---

# Algorithmic Problem Solving

Solve the underlying problem before writing code. Prefer a correct, explainable algorithm with justified complexity over clever code or premature optimization.

## 1. Formalize the problem

- Restate the objective and expected output.
- Identify inputs, constraints, data sizes, ordering assumptions, mutability, and edge cases.
- Separate explicit facts from assumptions; ask only when a missing constraint changes the solution materially.
- Define invariants and what constitutes a valid result.
- Construct small examples, including boundary and adversarial cases.

## 2. Design before implementation

Consider the simplest viable paradigm: direct simulation, sorting, hashing, two pointers, sliding window, binary search, divide-and-conquer, greedy, dynamic programming, graph traversal/shortest path, union-find, backtracking, or appropriate data structures. Do not force a named technique when a simpler method suffices.

For each serious candidate, compare:
- correctness argument and required invariant;
- time complexity and the dominant operation;
- auxiliary space complexity;
- preprocessing and memory costs;
- behavior on worst-case and representative inputs;
- implementation complexity and maintainability.

Use asymptotic notation accurately. State assumptions behind average-case claims. Distinguish input storage from auxiliary space. Do not claim an optimization without a baseline or a defensible complexity argument.

## 3. Correctness discipline

- State the key invariant or induction hypothesis.
- Explain initialization, preservation, and termination where applicable.
- For greedy algorithms, justify why the local choice can be part of an optimal solution.
- For dynamic programming, define state, transition, base cases, evaluation order, and answer extraction.
- For graph algorithms, state graph assumptions (directed/undirected, weighted/unweighted, negative edges, connectivity).
- Check overflow, empty inputs, duplicates, invalid values, off-by-one errors, and recursion depth.

## 4. Implementation discipline

Write readable pseudocode first when the problem is nontrivial. Then implement using the project's language and conventions. Keep algorithmic logic separate from input/output, persistence, and UI. Avoid premature micro-optimization; profile before optimizing runtime-sensitive code.

## 5. Verification

Create tests for normal, minimum, maximum, duplicate, sorted/reverse-sorted, malformed, and adversarial inputs as relevant. Use brute force as an oracle for small randomized inputs when feasible. Test invariants and compare optimized results against a simple reference implementation. Benchmark only with reproducible input sizes and environment notes.

## Output contract

For a nontrivial problem, explain: formalized problem, chosen approach and why, pseudocode or implementation, worked example, correctness argument, time/space complexity, edge cases, and tests. Keep the explanation proportional to task complexity.

## Learning reference

MIT OpenCourseWare 6.006, Introduction to Algorithms: https://ocw.mit.edu/courses/6-006-introduction-to-algorithms-fall-2011/ . Use its lecture notes, problem sets, and solutions as learning references; do not copy solutions blindly or assume the course prerequisites are met.
