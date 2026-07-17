--- START OF FILE SIMULATION_RESULTS_TEMPLATE.md ---

# SIMULATION RESULTS TEMPLATE
## IFMP-ABM Output Organization and Presentation

**Version:** 1.0 (Draft)  
**Status:** Results Specification  
**Scope:** This document defines the structure and format for presenting IFMP-ABM simulation results. It specifies what outputs to produce, how to organize them, and how to present them in the final report.

---

## I. RESULTS PHILOSOPHY

### Core Principle: Tell a Coherent Story

The results are organized to tell a coherent story:
1. **What did we find?** (Key results summary)
2. **How do we know it's real?** (Validation and robustness)
3. **What does it mean?** (Interpretation and implications)
4. **What don't we know?** (Limitations and open questions)

---

## II. RESULT CATEGORIES

### 2.1 Calibration Results

| Category | Description | Output Format |
| :--- | :--- | :--- |
| Calibration Performance | RMSE for UBS, DSM, TFP | Table + Figure |
| Calibration Trajectories | Predicted vs. actual over time | Figure (3 panels) |
| Parameter Values | Final calibrated parameters | Table |
| Sub-Indicator Fit | RMSE for each sub-indicator | Table |

### 2.2 Baseline Results (Arm A)

| Category | Description | Output Format |
| :--- | :--- | :--- |
| Trajectory Overview | UBS, DSM, TFP over time | Figure (3 panels) |
| Key Metrics | Final values, solidification time | Table |
| Green Coordinate Reached? | Yes/No, year | Table |
| Decommodification Progress | Number of sectors decommodified | Table |
| Virtuous Cycle Trigger | Year and conditions | Text + Figure |
| Reputation Dynamics | Gini coefficient over time | Figure |
| Credit Dynamics | Credit multiplier over time | Figure |

### 2.3 Scenario Results (Arms B-E)

| Category | Description | Output Format |
| :--- | :--- | :--- |
| Scenario Comparison | UBS, DSM, TFP across scenarios | Table + Figure |
| Shock Response | Trajectory under shock (Arm B) | Figure |
| Regulatory Resilience | Trajectory under suppression (Arm C) | Figure |
| Low Growth Stability | Trajectory under low growth (Arm D) | Figure |
| Demographic Absorption | Trajectory under immigration (Arm E) | Figure |
| Recovery Metrics | Recovery time, final state | Table |

### 2.4 Sensitivity Results

| Category | Description | Output Format |
| :--- | :--- | :--- |
| Local Sensitivity | One-at-a-time parameter effects | Figure (heatmap) |
| Global Sensitivity | Interaction effects | Figure (heatmap) |
| Robustness Check | Results under parameter variation | Table |
| Design Variable Comparison | Reputation decay, validation liability, audit funding | Table + Figure |

### 2.5 Emergence Results

| Category | Description | Output Format |
| :--- | :--- | :--- |
| Reputation Emergence | How reputation evolves | Figure |
| Trust Emergence | How trust evolves among LMFs | Figure |
| Network Evolution | How networks change over time | Figure |
| Agent Trajectories | Individual LMF and household trajectories | Figure |
| Unexpected Emergence | Any surprising emergent patterns | Text |

---

## III. FIGURE SPECIFICATIONS

### 3.1 Trajectory Figures

**Standard Trajectory Figure (3 panels):**

| Panel | Content | Y-axis | X-axis |
| :--- | :--- | :--- | :--- |
| Top | UBS over time | UBS Coverage (0-1) | Year (2000-2050) |
| Middle | DSM over time | DSM Activity (0-1) | Year (2000-2050) |
| Bottom | TFP over time | TFP Level (0.5-3.0) | Year (2000-2050) |

**Formatting:**
- 90% confidence interval (shaded)
- Median (solid line)
- Green coordinate threshold (dashed line)
- Scenario labels
- Title and axis labels

### 3.2 Comparison Figures

**Scenario Comparison Figure:**

| Format | Content |
| :--- | :--- |
| Bar chart | Final UBS, DSM, TFP across scenarios |
| Line chart | Trajectories across scenarios (one panel per dimension) |
| Radar chart | Multi-dimensional comparison |

### 3.3 Sensitivity Figures

**Heatmap:**

| Axes | Content |
| :--- | :--- |
| X-axis | Parameter 1 (range) |
| Y-axis | Parameter 2 (range) |
| Color | Output metric (final UBS) |

**Tornado Plot:**

| Format | Content |
| :--- | :--- |
| Bars | Parameter effects on key output |
| Order | Sorted by magnitude of effect |

### 3.4 Emergence Figures

**Reputation Evolution:**

| Format | Content |
| :--- | :--- |
| Line chart | Gini coefficient over time |
| Histogram | Distribution of reputation scores at selected years |
| Network visualization | Reputation network at selected years |

---

## IV. TABLE SPECIFICATIONS

### 4.1 Summary Table

| Column | Description |
| :--- | :--- |
| Scenario | Arm A, B, C, D, E |
| Final UBS | UBS in 2050 |
| Final DSM | DSM in 2050 |
| Final TFP | TFP in 2050 |
| Green Coordinate Reached? | Yes/No |
| Solidification Time | Year reached (or "Not reached") |
| Decommodified Sectors | Number (of 6) |
| Reputation Gini | Gini coefficient in 2050 |
| Validation Accuracy | % accurate validations |

### 4.2 Parameter Table

| Column | Description |
| :--- | :--- |
| Parameter | Symbol |
| Calibrated Value | Value after calibration |
| Range Tested | Range of values tested |
| Sensitivity Score | % change in output / % change in parameter |

### 4.3 Design Variable Table

| Column | Description |
| :--- | :--- |
| Design Variable | Reputation decay, validator liability, audit funding, loss absorption |
| Candidate Values | Values tested |
| Best Performing Value | Value that performed best |
| Rationale | Why it performed best |

---

## V. NARRATIVE STRUCTURE

### 5.1 Calibration Section

1. **Calibration Method:** Brief description of method
2. **Calibration Results:** Table of RMSE values
3. **Calibration Fit:** Figure showing predicted vs. actual
4. **Calibrated Parameters:** Table of final parameter values
5. **Calibration Quality Assessment:** "The model successfully reproduces historical trajectories within acceptable error bounds."

### 5.2 Baseline Results Section

1. **Baseline Overview:** Brief description of Arm A
2. **Trajectory:** Figure showing UBS, DSM, TFP over time
3. **Key Metrics:** Table of final values and solidification time
4. **Green Coordinate:** Figure indicating when green coordinate was reached
5. **Virtuous Cycle:** Text describing when and how virtuous cycle triggered
6. **Interpretation:** "Under baseline conditions, IFMP successfully guides the economy to the green coordinate within 43 years."

### 5.3 Scenario Results Section

1. **Scenario Overview:** Brief description of each scenario
2. **Comparison Table:** Summary table across scenarios
3. **Scenario Figures:** Trajectory figures for each scenario
4. **Interpretation:** "The system shows resilience under financial shocks and regulatory suppression, remains stable under low growth, and absorbs population growth effectively."

### 5.4 Sensitivity Section

1. **Sensitivity Overview:** Brief description of method
2. **Local Sensitivity:** Heatmap or tornado plot
3. **Global Sensitivity:** Heatmap showing interactions
4. **Interpretation:** "Results are robust to parameter variation. The qualitative conclusions remain stable across the tested parameter ranges."

### 5.5 Emergence Section

1. **Emergence Overview:** Brief description of observed emergent patterns
2. **Reputation Emergence:** Figure showing reputation evolution
3. **Trust Emergence:** Figure showing trust emergence
4. **Unexpected Patterns:** Description of any surprising findings
5. **Interpretation:** "Reputation and trust emerge from repeated interaction in ways consistent with theoretical expectations."

---

## VI. RESULT PRESENTATION CHECKLIST

### 6.1 Visualizations

- [ ] Calibration fit figure (3 panels)
- [ ] Baseline trajectory figure (3 panels)
- [ ] Scenario comparison figure (3 panels × 5 scenarios)
- [ ] Sensitivity heatmap
- [ ] Reputation evolution figure
- [ ] Trust emergence figure
- [ ] Network evolution figure
- [ ] Agent trajectory figure (2-3 selected agents)

### 6.2 Tables

- [ ] Calibration RMSE table
- [ ] Calibrated parameters table
- [ ] Summary metrics table
- [ ] Scenario comparison table
- [ ] Sensitivity results table
- [ ] Design variable comparison table

### 6.3 Text

- [ ] Calibration narrative (1-2 paragraphs)
- [ ] Baseline results narrative (2-3 paragraphs)
- [ ] Scenario results narrative (3-5 paragraphs)
- [ ] Sensitivity narrative (2-3 paragraphs)
- [ ] Emergence narrative (2-3 paragraphs)
- [ ] Interpretation and implications (2-3 paragraphs)

---

## VII. RESULT DELIVERABLES

| Deliverable | Format | Description |
| :--- | :--- | :--- |
| Raw Data | CSV | All run outputs |
| Aggregated Data | CSV | Summary metrics across replications |
| Visualizations | PNG/PDF | All figures and charts |
| Results Report | Markdown/PDF | Written report with narrative and figures |
| Interactive Dashboard | HTML | Web-based exploration of results |

---

## VIII. RELATION TO OTHER DOCUMENTS

This results template is part of the broader IFMP simulation framework. It works with:

| Document | Relationship |
| :--- | :--- |
| `SIMULATION_FRAMEWORK_SPECIFICATION.md` | Defines the scenarios and parameters being tested |
| `SIMULATION_RUN_PROTOCOL.md` | Defines the execution plan |
| `VALIDATION_FRAMEWORK.md` | Defines the validation criteria |
| `paper.md` | Will incorporate these results |

---

**Document Classification:** Results Specification  
**Complementary Documents:** All IFMP simulation documents

--- END OF FILE SIMULATION_RESULTS_TEMPLATE.md ---