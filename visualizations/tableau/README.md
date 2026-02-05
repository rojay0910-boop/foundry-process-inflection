# Tableau Visualization Guide  
## Foundry-Level Process Technology Timeline

This folder contains the Tableau workbook(s) used to visualize the foundry-level process technology timeline.
The visualizations are designed to support **structural analysis of semiconductor process evolution**, rather than node-size ranking or performance comparison.

---

## Purpose of the Visualization

The Tableau dashboard uses a **foundry-level timeline** to examine how advanced semiconductor manufacturing has evolved over time across:

- Intel  
- Samsung
- TSMC  
  
Instead of ranking process nodes by nominal size (e.g., 7nm, 5nm, 3nm), the visualization highlights:

- Transistor architecture transitions  
- System-level manufacturing changes (e.g., power delivery)  
- Periods of architectural stability versus forced structural inflection  

The goal is to make **non-obvious patterns** visible—particularly long plateaus followed by abrupt structural shifts.

---

## How to Read the Chart

### Axes and Layout

- **X-axis (Year):**  
  Represents the calendar year in which a process milestone became publicly observable.

- **Y-axis (Company Lane):**  
 Each foundry is assigned to a primary horizontal lane to preserve structural clarity across companies.
 When a single foundry introduces multiple distinct process nodes within the same calendar year,
 a slight vertical displacement (Y-axis jitter) is applied within the company lane to prevent complete overlap of marks.
 This jitter is used solely for visual separation and does not encode differences in timing, hierarchy, or relative importance.

---

### Marks and Encodings

- **Mark Type:**  
  Each mark represents a foundry-specific process milestone observable at a given point in time.

- **Color:**  
  Distinguishes between foundries (TSMC, Samsung, Intel).
  
- **Shape:**  
  Encodes the **transistor architecture** (Planar, FinFET, GAA).

- **Mark Size:**
  Encodes whether EUV lithography was used at the time of process introduction.
  Larger markers indicate EUV-enabled processes, while smaller markers represent non-EUV processes.
  Marker size reflects a binary usage status, not relative importance, performance, or production scale.

- **Labels:**  
  Display foundry-specific process names (e.g., N7, N3, 20A) for identification and traceability only,
  not for ranking, ordering, or comparative evaluation.

---

## Analytical Intent

This visualization is intentionally **not** designed to answer:

- Which node is the “best”
- Which foundry is “ahead” at a given moment
- How performance or yield compares numerically

Instead, it supports questions such as:

- When does incremental scaling stop working?  
- How long can a given transistor architecture be extended?  
- What conditions force architectural change?  

The timeline makes visible how advanced-node progress often occurs through **extended architectural stability**, followed by **structural inflection points**.

---

## Methodology Alignment

The Tableau design aligns with the project’s broader methodology:

- Process-node names are treated as labels, not physical measurements  
- Architectural change is treated as the primary generational boundary  
- Publicly observable decisions are prioritized over inferred metrics  

For detailed field definitions and assumptions, refer to:

- `methodology/field_definitions.md`  
- `data_model/README.md`

---

## Known Limitations

- The visualization does not encode yield, cost, or defect density, as these are not publicly comparable.
- Timing reflects public disclosure rather than internal manufacturing milestones.
- Some architectural features may appear earlier in research disclosures than in high-volume production.

These limitations are intentional and consistent with the project’s focus on **structural interpretation**, not benchmarking.

---

## Files in This Folder

- `foundry_process_timeline.twbx`  
  Main Tableau workbook containing the timeline visualization.

(Additional dashboards or exploratory views may be added as the project evolves.)

---

## Intended Audience

This visualization is intended for:

- Researchers analyzing semiconductor process evolution  
- Data visualization practitioners exploring timeline-based analysis  
- Readers interested in structural, rather than nominal, technology comparisons  

