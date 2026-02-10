# Notes and Interpretation Guidance

This document collects contextual notes, judgment calls, and interpretation guidance that support the analysis but are not part of the formal research questions.

The goal is to improve transparency, prevent over-interpretation, and document decisions made during data curation and visualization.

---

## 1) Interpreting Time in the Timeline

The timeline uses a single representative year for each process milestone (typically first volume production or the first clearly observable public milestone).

In practice, process adoption occurs over a multi-year window:
- risk production
- limited volume
- broad customer availability

The timeline should therefore be read as indicating **relative sequencing and structural timing**, not precise start or end dates.

---

## 2) On Node Labels and Comparability

Nominal node labels (e.g., 7nm, 5nm, 3nm) are used only as generational identifiers.

They should not be interpreted as:
- equivalent physical dimensions across foundries
- direct performance or density comparisons

Cross-foundry comparison in this project relies on **architecture class and transition timing**, not on nominal node parity.

---

## 3) Visualization Simplifications

Several visualization-driven simplifications are applied:

- Node-family variants are collapsed into a single representative node
- Only major architectural inflection points are emphasized
- Minor derivatives and application-specific variants are omitted

These choices are intentional and serve readability and interpretability, not completeness.

---

## 4) Reading the Timeline Correctly

The timeline is well-suited for observing:
- periods of architectural stability
- clustering of major transitions
- relative timing differences between foundries

It is **not** intended to support:
- yield comparisons
- cost competitiveness claims
- customer-specific enablement analysis

---

## 5) Source Usage and Confidence

This project relies on a mix of:
- official foundry disclosures
- conference presentations
- industry analysis articles

Where multiple sources disagree, conservative interpretations are preferred, and ambiguity is preserved rather than resolved by assumption.

---

## 6) What This Project Intentionally Does Not Model

The following factors are treated as background conditions and are not modeled explicitly:
- EUV tool supply constraints
- EDA ecosystem readiness
- geopolitical or subsidy-driven effects

This scope choice is intentional and consistent with the focus on process- and architecture-level differentiation.

---

## 7) Notes for Future Extension

If the dataset or analysis is extended in the future, likely impact areas include:
- explicit modeling of backside power delivery
- separation of risk production vs volume production milestones
- inclusion of High-NA EUV as a distinct structural transition
