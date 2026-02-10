# Data Preparation

This document describes how the project’s foundry-specific datasets are curated and consolidated into a unified, Tableau-ready dataset for timeline visualization and cross-foundry comparison.

---

## 1) Inputs and Outputs

### Foundry-specific source files (inputs)
The project maintains three source datasets, curated at the foundry level:

- `data/process_nodes_TSMC.csv`
- `data/process_nodes_Samsung.csv`
- `data/process_nodes_Intel.csv`

These files preserve provenance and enable future expansion without breaking the unified schema.

### Unified dataset (output)
For visualization and comparative analysis, the three foundry-level datasets are merged into a single canonical file:

- `data/foundry_technology_timeline(all).csv` *(Tableau-ready)*

This unified dataset is the single source of truth used by Tableau visualizations and any cross-foundry comparisons.

---

## 2) Standardization Goals

To support a shared timeline view across Intel, TSMC, and Samsung, data preparation prioritizes:

- **Schema alignment:** consistent column names, types, and value conventions across foundries  
- **Comparability:** interpret nominal node labels as *generational identifiers*, not literal dimensions  
- **Visualization readiness:** stable categorical encoding in Tableau (foundry lanes, milestone years, attributes)  
- **Traceability:** retain foundry identity and notes/sources when available

---

## 3) Schema Alignment and Normalization

Before merging, each foundry-level dataset is normalized to a consistent schema.

Typical normalization steps include:

- **Column naming consistency**
  - Convert headers to a shared naming convention (e.g., `snake_case`)
  - Ensure the same field names exist across all three files

- **Data type standardization**
  - Year fields stored as integers (e.g., `first_volume_year`)
  - Boolean or categorical fields standardized (e.g., `euv_used` as `Yes/No` or `True/False`, but consistent)

- **Categorical cleanup**
  - Normalize foundry names (e.g., `TSMC`, `Samsung`, `Intel`)
  - Normalize architecture labels (e.g., `Planar`, `FinFET`, `GAA`)
  - Normalize technology variants and node family naming where possible

The unified dataset preserves foundry identity as a categorical field to enable lane-based timeline encoding.

---

## 4) Consolidation Process (Merge)

The unified dataset is constructed by concatenating the three foundry-specific tables after schema alignment.

Conceptually:

1. Load the three foundry-level CSVs  
2. Validate schema compatibility (same columns and types)  
3. Union/concat rows into a single table  
4. Export a Tableau-ready CSV

This merge produces a single table that supports:
- foundry-level filtering
- cross-foundry comparisons
- consistent encoding of architecture and EUV adoption

---

## 5) Visualization-Oriented Node Representation (Node-Level Only)

To maintain clarity and interpretability in the Tableau timeline, the unified dataset adopts a **node-level representation** rather than listing every node-family entry.

In cases where a single process generation includes multiple closely related **node families** or derivative variants, only **one representative node record** is retained for visualization. The representative record serves as the anchor point for that generation on the timeline, while family-level and derivative entries are intentionally omitted.

This design choice is applied consistently across foundries where applicable and is intended to:

- reduce visual clutter and overplotting  
- keep lane-based comparisons readable  
- support stable categorical encoding and controlled jitter behavior in Tableau  

Omitted node-family variants are **not** considered technologically insignificant. They are excluded solely to preserve a clean, comparable timeline view and do not change the analytical framing of the project.

---

## 6) Handling Overlapping Milestones (Tableau Overplotting)

Because multiple milestones can occur in the same year (either within one foundry or across foundries), overlapping marks can occur in a shared timeline.

To address this in Tableau:

- **Foundry lanes** are fixed by foundry (one horizontal lane per foundry)
- **Controlled jitter is applied to the Y-position (lane position)** to separate overlapping points while preserving lane identity
- **Categorical encoding** (e.g., shape/size) is used to emphasize key attributes such as transistor architecture and EUV adoption

This approach preserves the timeline semantics while improving readability when marks share the same or adjacent year values.

---

## 7) Quality Checks

Before exporting the unified dataset, the following checks are recommended:

- **Schema check:** all expected columns exist, no unexpected null columns introduced
- **Value sanity checks:**
  - `first_volume_year` is within a plausible range
  - `foundry` values are limited to the expected set
  - `transistor_architecture` categories are consistent
  - `euv_used` categories are consistent
- **Duplicate inspection:** verify whether duplicates represent legitimate multiple milestones or accidental repeated rows
- **Spot-check against sources:** validate a small subset of milestones for each foundry

---

## 8) Reproducibility Notes

The unified dataset can be regenerated at any time by re-running the merge pipeline that reads the three foundry CSVs and exports a consolidated file.

Recommended practice:
- Treat foundry-level CSVs as the curated source of truth
- Treat the unified CSV as a derived artifact for visualization and comparison
- Document any future schema changes in this file to keep Tableau and analysis aligned

---

## 9) File Locations (Suggested)

Recommended repository layout:

- `data/`  
  - `process_nodes_TSMC.csv`  
  - `process_nodes_Samsung.csv`  
  - `process_nodes_Intel.csv`  
  - `foundry_technology_timeline(all).csv` *(unified, Tableau-ready)*

- `methodology/`  
  - `data_preparation.md` *(this document)*  
  - `modeling_assumptions.md` *(optional)*  
  - `node_representation.md` *(optional; can be merged into this doc if preferred)*

---

## 10) Change Log (Optional)

Maintain a short change log here if your schema or selection rules evolve (e.g., changes to node-level representation rules, new attributes, or revised category mapping).
