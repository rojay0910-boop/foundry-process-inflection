## Overview

This project analyzes the evolution of advanced semiconductor manufacturing by using a **foundry-level technology timeline** as the primary analytical lens.  
Rather than ranking process nodes by nominal node size or vendor performance claims, the analysis focuses on **structural decision points**—specifically transistor architecture and system-level manufacturing choices—across Intel, TSMC, and Samsung.

By visualizing each foundry’s process milestones on a shared timeline, this project aims to reveal non-obvious patterns in how advanced-node progress is achieved, delayed, or fundamentally redirected under physical, economic, and manufacturability constraints.

---

## Visualization

The core artifact of this project is a timeline visualization in which:

- Each foundry is fixed on a consistent horizontal lane  
- Discrete process milestones are plotted by year  
- Key attributes such as transistor architecture and power-delivery strategy are emphasized  

This layout allows direct visual comparison without relying on marketing-driven node labels alone.  
The visualization highlights periods of architectural stability, moments of forced transition, and divergence in strategic timing between foundries.

---

## Research Questions

This analysis is guided by the following research questions:

### RQ1: Process Node Evolution (Technology Timeline)  
How have advanced semiconductor process nodes evolved over time when viewed through a foundry-level technology timeline rather than nominal node naming?

### RQ2: Technology Leadership and Differentiation  
How do leading foundries differ in their technology trajectories, and what defines process leadership beyond node labels?

### RQ3: Supply Chain Roles and Node Relationships  
How do supply-chain dependencies—such as tooling, materials, IP, and ecosystem readiness—influence the timing and feasibility of advanced-node transitions?

### RQ4: Process Nodes and Industry Concentration  
Does rising process complexity contribute to structural concentration within the foundry industry, and if so, how?

### RQ5: Data Limitations and Analytical Assumptions  
What limitations arise from using publicly available data to analyze semiconductor process-node trends?

---

## Methodology

### Data Sources

This project relies exclusively on **publicly available sources**, including:

- Foundry press releases and technology disclosures  
- Conference presentations (IEDM, VLSI, etc.)  
- Public roadmaps and technical whitepapers  
- Industry analysis articles and archival reporting  

No proprietary yield, cost, or internal design data is used.

### Modeling Assumptions

- Nominal process-node names are treated as **generational labels**, not physical dimensions  
- Architectural changes are considered more significant than incremental node scaling  
- Public announcements are interpreted conservatively, with uncertainty noted when applicable  

The analysis prioritizes **comparability and interpretability** over absolute technical precision.

---

## Key Findings

### 1. The FinFET Architectural Plateau

After the industry-wide transition from planar transistors to FinFET around 2012–2014, transistor architecture remained largely unchanged for nearly a decade—even as nodes scaled from 7nm to 3nm.

This apparent plateau does not indicate stagnation. Instead, progress during this period was driven by:

- Lithography scaling (including multi-patterning and EUV adoption)  
- Materials engineering and device optimization  
- Application-specific process variants  

### 2. Complexity as a Substitute for Architecture Change

Rather than introducing new transistor architectures, foundries extended FinFET through increasingly complex process techniques.  
Innovation shifted from geometry to execution, cost management, and yield optimization.

### 3. True Inflection Points Are Structural, Not Nominal

Major generational transitions occur when existing architectures can no longer be extended:

- Gate-All-Around (GAA) transistors represent a fundamental change in electrostatic control  
- Backside power delivery reconfigures system-level integration and routing constraints  

These transitions mark **structural inflection points**, not merely new node names.

---

## Comparative Analysis: Intel, TSMC, and Samsung

- **TSMC** emphasized risk-managed scaling, extending FinFET longer while prioritizing yield and ecosystem stability  
- **Samsung** pursued earlier architectural experimentation, accepting higher initial manufacturing risk  
- **Intel** combined aggressive architectural shifts with system-level innovations such as backside power delivery  

Differences in timing reflect not just technical capability, but also strategic tolerance for risk and cost.

---

## Supply Chain and Industry Implications

Advanced-node manufacturing increasingly depends on:

- EUV lithography tooling availability  
- Materials and process-integration maturity  
- Co-optimization with EDA tools and customers  

As complexity rises, fewer firms can sustain leading-edge development, reinforcing **structural concentration** within the foundry industry.

---

## Limitations

This analysis is constrained by the nature of public data:

- Disclosures are incomplete and sometimes marketing-driven  
- Yield, defect density, and true cost structures are unavailable  
- Node naming conventions obscure cross-foundry comparability  

As a result, conclusions should be interpreted as **directional and structural**, not definitive measurements.

---

## Conclusion

Viewed through a foundry-level timeline, advanced semiconductor progress is not a steady sequence of shrinking node numbers, but a pattern of **extended architectural stability punctuated by forced structural transitions**.

This framework reframes node evolution as a series of engineering trade-offs under physical, economic, and manufacturability limits—offering a clearer lens for understanding past transitions and anticipating future ones.

---

## Future Work

Potential extensions of this project include:

- Advanced packaging and chiplet integration timelines  
- Post-GAA architectures such as CFET  
- High-NA EUV adoption and ecosystem readiness  
- Closer integration of packaging and front-end process analysis  

---

## References
1. https://www.tsmc.com/english/dedicatedFoundry/technology/logic
2. https://semiconductor.samsung.com/foundry/process-technology/logic-node/
3. https://semiwiki.com/semiconductor-manufacturers/321400-samsung-versus-tsmc-update-2022/
4. https://www.aminext.blog/
