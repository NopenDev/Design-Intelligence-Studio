---
name: product-ux-and-flows
description: "Use when defining user journeys, information architecture, navigation, onboarding, forms, workflows, or product behavior before visual implementation."
---

# Product UX and Flows

Design the user's path before designing isolated screens.

## Workflow
1. State the user's goal, trigger, context, and success condition.
2. Identify actors, permissions, prerequisites, data needed, and irreversible actions.
3. Map the happy path and alternate paths: cancellation, backtracking, validation, empty data, denied access, network failure, retry, and recovery.
4. Define the information architecture: objects, relationships, navigation levels, labels, and search/filter needs.
5. For each step, specify user intent, visible information, action, system response, and next state.
6. Reduce cognitive load: progressive disclosure, sensible defaults, preserve work, and avoid asking for data already known.
7. Validate the flow against realistic scenarios and edge cases before visual polish.

## Screen-state contract
For each important screen, define:
- entry conditions and user permissions;
- loading / initial state;
- populated state;
- empty state with next action;
- validation and error states;
- success / confirmation;
- disabled and unavailable states;
- unsaved changes and exit behavior.

## Flow quality checks
- Is the next action obvious?
- Does the interface explain why an action is unavailable?
- Can the user recover without losing entered data?
- Are destructive consequences clear?
- Does navigation preserve context where expected?
- Are labels understandable to the user rather than implementation-oriented?
- Are exceptional paths designed, not left to browser defaults?

Do not invent user research. Distinguish observed evidence, assumptions, and hypotheses. Recommend validation when an important decision rests on an assumption.
