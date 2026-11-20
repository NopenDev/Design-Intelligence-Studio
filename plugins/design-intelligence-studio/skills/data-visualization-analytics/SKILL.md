---
name: data-visualization-analytics
description: "Use when exploring datasets, defining metrics or KPIs, performing quantitative analysis, designing analytical dashboards, or selecting and building charts and data stories."
---

# Data Visualization & Analytics

Turn data into a defensible decision aid. The analytical question, data quality, metric definition, and uncertainty must be correct before visual polish begins.

## 1. Clarify the decision

Identify the audience, decision, unit of analysis, time horizon, comparison, and action that the analysis should support. Translate broad requests into answerable questions. If the data cannot support the requested conclusion, explain the gap rather than manufacturing certainty.

## 2. Inspect and qualify the data

Before analysis, document:
- source, owner, extraction date, grain, time zone, and refresh cadence;
- row/column counts, identifiers, units, data types, and category cardinality;
- missingness, duplicates, outliers, invalid values, inconsistent labels, and join coverage;
- sampling method, selection bias, survivorship, measurement changes, and known limitations.

Keep raw inputs separate from cleaned/derived data. Make transformations reproducible. Never silently delete outliers, impute missing values, change denominators, or mix time periods. State the rule and its effect.

## 3. Define metrics before charts

For every KPI specify its formula, numerator, denominator, unit, population, inclusion/exclusion rules, time window, aggregation, owner, and target/threshold source. Distinguish counts, rates, ratios, averages, medians, percentiles, cohorts, and cumulative measures. Ensure comparisons use compatible definitions and denominators.

For statistical claims, inspect distributions and assumptions. Use confidence intervals or uncertainty bands where meaningful. Distinguish descriptive association, prediction, and causal inference; do not claim causality without a valid design and supporting assumptions.

## 4. Choose an analytical method

Match the method to the question:
- trend over time → line/area with clear temporal granularity;
- category comparison → sorted bar/dot plot;
- distribution → histogram, box/violin, or empirical distribution;
- relationship → scatter plot with appropriate scale and fitted model only when justified;
- composition → stacked or part-to-whole chart only when components sum meaningfully;
- flow → Sankey/alluvial only when transitions and volume are central;
- geographic pattern → route to `gis-mapping-engineering` when spatial relationships matter.

Use a table when exact lookup matters more than a visual pattern. Avoid pie/donut charts for many categories, 3D effects, decorative gauges, and chart types that obscure the comparison.

## 5. Design the visual encoding

- Put the main conclusion and its context in the title/subtitle; label axes, units, periods, and sources.
- Choose scales honestly. Bar charts generally start at zero; if a truncated axis is necessary, disclose it and preserve interpretability.
- Use color to encode a meaningful variable, not decoration. Keep sequential, diverging, and categorical palettes semantically distinct and accessible to color-vision deficiencies.
- Use direct labels where they reduce comparison effort; keep legends close to the data and avoid clutter.
- Show uncertainty, missingness, and no-data explicitly. Distinguish zero from unavailable values.
- Design mobile and small-screen behavior deliberately; prioritize key comparisons and provide accessible tabular summaries.

## 6. Dashboard and analytics architecture

Group views by decisions and workflow, not by whatever fields happen to exist. Keep overview metrics limited to actionable signals; provide drill-downs for diagnosis. Include filters with clear scope, default period, applied state, and reset behavior. Make metric definitions, data freshness, and provenance inspectable. Avoid misleading aggregation, double-counting, and filters that silently change denominators.

Separate ingestion, transformation, metric definitions, and presentation where the project scale warrants it. Cache expensive calculations with explicit freshness semantics. Validate access controls at the data/API layer; dashboard filtering is not authorization. Minimize personally identifiable or sensitive data in charts and exports.

## 7. Verification and communication

Reconcile displayed totals against the source query or a trusted control total. Test boundary dates, empty results, filters, timezone transitions, missing categories, and large values. Verify labels, units, scales, rounding, and source timestamps. For each finding or insight, provide the method, evidence, caveat, and decision implication.

## Output contract

For a substantial analysis or dashboard, deliver:
- question and audience;
- source/provenance and data-quality notes;
- metric definitions and method assumptions;
- chart/dashboard structure and rationale;
- key findings with uncertainty and limitations;
- validation checks and recommended next action.

Do not fabricate data, KPI targets, statistical significance, or business impact.

## Boundaries and routing

- Spatial joins, CRS, basemaps, spatial statistics, interactive maps → `gis-mapping-engineering`.
- Color, typography, visual hierarchy, reusable chart styling → `visual-design-foundations` and `design-system-engineering`.
- Application/API implementation → `frontend-backend-engineering`.
- Product flow and information architecture → `product-ux-and-flows`.
