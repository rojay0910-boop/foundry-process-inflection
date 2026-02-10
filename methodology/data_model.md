Why a Foundry-Level Timeline (Data Model Rationale)

This data model is structured around a foundry-level technology timeline, rather than a ranking or comparison based on nominal process-node size (e.g., 7nm, 5nm, 3nm).
This design choice reflects both the nature of modern semiconductor manufacturing and the constraints of publicly available data.

Node size is not a reliable primary key

Nominal process-node labels no longer correspond to consistent physical dimensions across foundries.
At advanced nodes, identical node names may represent substantially different transistor architectures, lithography usage, and manufacturing maturity.

As a result, node size is treated as a descriptive label, not as a sortable or comparable metric within the data model.

Technology evolution occurs as sequences, not isolated nodes

Foundry technology decisions unfold over time through sequences of choices, including:

How long to extend an existing transistor architecture

When to introduce a new architecture

How to balance risk, yield, cost, and ecosystem readiness

A timeline-based model preserves these sequences, whereas a node-ranking model collapses them into misleading point comparisons.

Architectural change defines generational boundaries

In this data model, transistor architecture and system-level structure are the primary indicators of generational transition.
Major shifts—such as Planar → FinFET, FinFET → GAA—represent structural changes that are not captured by node-size ordering.

Organizing data by foundry and year makes these inflection points explicit.

Public data supports temporal structure better than quantitative ranking

Key metrics required for node ranking (yield, defect density, true cost) are not publicly available in consistent or verifiable form.
In contrast, the timing of architectural adoption and manufacturing strategy shifts is observable through public disclosures.

The data model is therefore optimized for structural sequencing, not performance scoring.

Implications for the dataset

Each row represents a foundry-specific process milestone in time

Node labels are preserved for traceability, not comparison

Analytical focus is placed on architecture, power delivery, and system-level decisions

This structure enables reproducible analysis of technology inflection points using public information, without implying false precision or competitive rankings.