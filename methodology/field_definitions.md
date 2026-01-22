# Field Definitions and Methodology Notes

This document defines the fields used in the core dataset and explains the analytical intent behind each column.
The goal is not to describe manufacturing recipes in detail, but to establish a consistent, comparable framework
for analyzing structural inflection points in advanced semiconductor process evolution using public sources.

---

## Overview

The dataset is designed around a **foundry-level technology timeline**, rather than a node-ranking or performance benchmark.
Each row represents a publicly observable process milestone associated with a specific foundry and year.

Key design principles:

- Focus on **structural decisions**, not nominal node labels
- Use **stable categorical fields** suitable for visualization and comparison
- Avoid fields that require confidential metrics (yield, defect density, cost)

---

## Field Definitions

### `company`

**Description:**  
The semiconductor manufacturer or foundry responsible for the process technology.

**Examples:**  
- TSMC  
- Samsung  
- Intel  

**Rationale:**  
Fixing each company as a persistent entity enables lane-based timeline visualization and highlights differences
in technology adoption timing and strategy.

---

### `company_type`

**Description:**  
Business model classification of the company.

**Typical Values:**  
- Foundry  
- IDM  

**Rationale:**  
This field provides contextual information about organizational structure and strategic constraints
(e.g., pure-play foundry vs. vertically integrated manufacturer).

---

### `year`

**Description:**  
The calendar year in which the process milestone was publicly announced, entered risk production,
or reached volume production.

**Rationale:**  
The year field anchors all analysis temporally.  
Precision beyond the year level is intentionally avoided due to inconsistent public disclosure practices.

---

### `technology_stage`

**Description:**  
High-level categorization of the process generation or era.

**Examples:**  
- FinFET era  
- GAA transition  
- GAA + system-level integration  

**Rationale:**  
This field abstracts away node naming and instead groups technologies by architectural phase,
supporting inflection-point analysis.

---

### `transistor_architecture`

**Description:**  
The dominant transistor structure used at that process stage.

**Examples:**  
- Planar  
- FinFET  
- GAA (Nanosheet, MBCFET, RibbonFET)  

**Rationale:**  
Transistor architecture is treated as a **primary structural variable**.
Changes in this field indicate genuine generational transitions rather than incremental scaling.

---

### `power_delivery`

**Description:**  
The dominant power delivery configuration at the system or device level.

**Examples:**  
- Frontside power delivery  
- Backside power delivery  

**Rationale:**  
Power delivery is included as a separate structural dimension because it reflects
system-level integration changes that are orthogonal to transistor geometry.
Backside power delivery is treated as a distinct inflection point.

---

### `tech_label`

**Description:**  
Foundry-specific process naming used in public communications.

**Examples:**  
- N7, N5, N3, N2 (TSMC)  
- SF7, SF3, SF2 (Samsung)  
- Intel 7, 20A, 18A (Intel)  

**Rationale:**  
This field preserves traceability to public sources while avoiding analytical reliance on nominal node size.

---

### `source_type`

**Description:**  
Type of public source used to identify or validate the process milestone.

**Examples:**  
- Foundry announcement  
- Technical conference (IEDM, VLSI)  
- Industry analysis  
- Public roadmap  

**Rationale:**  
This field supports transparency and allows readers to assess the reliability and intent of the source.

---

### `y_position`

**Description:**  
A visualization helper field used to fix each company on a consistent vertical lane in Tableau.

**Rationale:**  
This field has no analytical meaning on its own.
It exists solely to ensure visual stability and prevent reordering during filtering or interaction.

---

### `notes`

**Description:**  
Free-text annotations providing context, clarification, or known caveats.

**Examples:**  
- Early risk production vs. high-volume manufacturing  
- Limited adoption or yield concerns  
- Architecture present in research but not yet in mass production  

**Rationale:**  
This field captures nuance that cannot be expressed through categorical fields,
without contaminating the core analytical dimensions.

---

## Methodological Notes

- Process node names are treated as **labels**, not physical measurements.
- Absence of architectural change does **not** imply stagnation; it often reflects optimization under constraint.
- All conclusions are **structural and directional**, not quantitative performance rankings.
- The dataset intentionally avoids fields that would require non-public information.

---

## Known Limitations

- Public disclosures may be incomplete or marketing-driven
- Yield, defect density, and true cost structures are unavailable
- Cross-foundry comparability is inherently imperfect due to naming conventions

These limitations are acknowledged explicitly and form part of the analytical framing of the project.

---

## Intended Use

This dataset and its field structure are intended for:

- Timeline-based visualization of technology inflection points
- Comparative analysis across foundries
- Methodology-focused discussion rather than benchmarking claims

