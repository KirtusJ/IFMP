--- START OF FILE VALIDATION_FRAMEWORK.md ---

# VALIDATION FRAMEWORK
## IFMP-ABM Model Calibration and Validation

**Version:** 1.0 (Draft)  
**Status:** Validation Specification  
**Scope:** This document defines the calibration and validation protocol for the IFMP-ABM. It specifies how to verify that the model accurately reproduces historical patterns and produces credible emergent behavior.

---

## I. VALIDATION PHILOSOPHY

### Core Principle: Calibrate to History, Validate on Emergence

The model is calibrated to reproduce historical patterns (2000-2025). It is validated on its ability to produce credible emergent behavior (2025-2050).

| We Validate | We Do Not Validate |
| :--- | :--- |
| That the model reproduces known historical trajectories | That the model predicts specific future outcomes |
| That emergent patterns are plausible | That emergent patterns are predetermined |
| That institutional rules produce expected aggregate behavior | That agent behavior matches empirical psychological data |
| That the model is robust to parameter variation | That the model produces a single "correct" result |

---

## II. CALIBRATION DATA

### 2.1 Data Source

The model uses synthetic data calibrated to the Alpha economy (2000-2025). The dataset is available in `data/alpha_dataset.json`.

### 2.2 Calibration Targets

| Variable | 2000 | 2010 | 2020 | 2025 | Source |
| :--- | :--- | :--- | :--- | :--- | :--- |
| UBS Coverage | 0.652 | 0.664 | 0.674 | 0.681 | Synthetic data |
| DSM Activity | 0.596 | 0.538 | 0.468 | 0.415 | Synthetic data |
| TFP Level | 0.905 | 0.992 | 1.080 | 1.198 | Synthetic data |

### 2.3 Calibration Sub-Indicators

The model is calibrated to match sub-indicators as well as aggregate values:

| UBS Sub-Indicators | DSM Sub-Indicators | TFP Sub-Indicators |
| :--- | :--- | :--- |
| Medical access | Trust | Labor productivity |
| Housing affordability | Community participation | Innovation (R&D) |
| Education access | Cultural production | Infrastructure quality |
| Food security | Entrepreneurship | Skills (education) |
| Social security | Volunteerism | Technology adoption |

---

## III. CALIBRATION PROCEDURE

### 3.1 Initial Parameter Setting

Starting parameters are derived from the theoretical framework and historical precedent.

| Parameter | Symbol | Starting Value | Rationale |
| :--- | :--- | :--- | :--- |
| UBS response to TFP | α_U | 0.12 | Theoretical derivation |
| DSM response to UBS | α_D | 0.15 | Theoretical derivation |
| TFP response to (UBS+DSM) | γ_T | 0.08 | Theoretical derivation |
| UBS network diffusion | β_U | 0.04 | Calibration target |
| DSM network diffusion | β_D | 0.04 | Calibration target |
| TFP network diffusion | δ_T | 0.03 | Calibration target |
| Global Open IP effect | ε_T | 0.02 | Calibration target |

### 3.2 Calibration Method

**Step 1: Run Baseline Simulation**
- Run the model from 2000 to 2025 using starting parameters
- Record UBS, DSM, and TFP at each time step

**Step 2: Calculate Prediction Error**
- For each year, calculate: `error = predicted - actual`
- For each dimension, calculate: `RMSE = sqrt(mean(error^2))`

**Step 3: Adjust Parameters**
- Identify parameters with highest sensitivity
- Adjust parameters to minimize RMSE
- Re-run simulation

**Step 4: Iterate**
- Repeat Steps 1-3 until RMSE < 10% for all dimensions

### 3.3 Acceptable Error Thresholds

| Dimension | Acceptable RMSE | Ideal RMSE |
| :--- | :--- | :--- |
| UBS | < 10% | < 5% |
| DSM | < 10% | < 5% |
| TFP | < 10% | < 5% |

---

## IV. VALIDATION PROCEDURE

### 4.1 Qualitative Validation

**Emergent Pattern Validation:**
- Does the model exhibit virtuous cycles when conditions are favorable?
- Does the model exhibit vicious cycles when conditions are unfavorable?
- Are emergent patterns consistent with theoretical expectations?

**Plausibility Validation:**
- Are agent behaviors plausible given their incentives?
- Do aggregate patterns resemble known economic dynamics?
- Are there any obviously implausible outcomes?

### 4.2 Quantitative Validation

**Historical Trajectory Validation:**
- After calibration, the model should reproduce historical UBS, DSM, and TFP trajectories within acceptable error bounds.

**Scenario Validation:**
- Run baseline scenario (Arm A) with calibrated parameters
- Verify that results are plausible and consistent with theoretical expectations
- Run shock scenarios (Arms B-E) and verify that responses are plausible

### 4.3 Sensitivity Validation

**Parameter Sensitivity:**
- Vary each parameter by ±20% while holding others constant
- Observe whether qualitative conclusions remain stable
- If qualitative conclusions change dramatically, identify the parameter as high-sensitivity

**Structural Sensitivity:**
- Test alternative model structures (different network topologies, different agent rules)
- Observe whether qualitative conclusions remain stable

---

## V. VALIDATION METRICS

### 5.1 Calibration Metrics

| Metric | Description | Target |
| :--- | :--- | :--- |
| UBS RMSE | Root mean square error for UBS | < 10% |
| DSM RMSE | Root mean square error for DSM | < 10% |
| TFP RMSE | Root mean square error for TFP | < 10% |
| Sub-Indicator RMSE | RMSE for each sub-indicator | < 15% |

### 5.2 Emergence Metrics

| Metric | Description | Target |
| :--- | :--- | :--- |
| Virtuous Cycle Onset | Cycle when virtuous cycle triggers | Plausible range (2040-2050) |
| Solidification Time | Time to reach green coordinate | Plausible range (40-50 years) |
| Reputation Convergence | Gini coefficient of reputation scores | Plausible range (0.3-0.6) |
| Validation Accuracy | % of accurate validations | Plausible range (80-95%) |

### 5.3 Robustness Metrics

| Metric | Description | Target |
| :--- | :--- | :--- |
| Parameter Sensitivity Score | % change in output per % change in parameter | < 2.0 (low sensitivity) |
| Scenario Consistency | Consistency of results across scenarios | Qualitative conclusions stable |
| Structural Stability | Results stable across alternative structures | Qualitative conclusions stable |

---

## VI. VALIDATION CHECKLIST

### Phase 1: Calibration

- [ ] Model runs from 2000-2025 with no errors
- [ ] UBS RMSE < 10%
- [ ] DSM RMSE < 10%
- [ ] TFP RMSE < 10%
- [ ] Sub-indicator RMSE < 15%
- [ ] Calibration parameters documented
- [ ] Calibration iterations recorded

### Phase 2: Qualitative Validation

- [ ] Virtuous cycles observed under favorable conditions
- [ ] Vicious cycles observed under unfavorable conditions
- [ ] Agent behaviors are plausible
- [ ] Aggregate patterns are consistent with theory
- [ ] No obviously implausible outcomes

### Phase 3: Quantitative Validation

- [ ] Historical trajectories reproduced
- [ ] Baseline scenario results are plausible
- [ ] Shock scenario responses are plausible
- [ ] Results are consistent with theoretical expectations

### Phase 4: Sensitivity Validation

- [ ] Parameter sensitivity assessed
- [ ] High-sensitivity parameters identified
- [ ] Qualitative conclusions stable under parameter variation
- [ ] Structural sensitivity assessed
- [ ] Qualitative conclusions stable under structural variation

---

## VII. CALIBRATION AND VALIDATION OUTPUTS

### 7.1 Calibration Outputs

| Output | Format | Description |
| :--- | :--- | :--- |
| Calibration Parameters | CSV | Final parameter values after calibration |
| Calibration History | CSV | Parameter values and RMSE at each iteration |
| Calibration Plots | PNG | Predicted vs. actual trajectories for UBS, DSM, TFP |

### 7.2 Validation Outputs

| Output | Format | Description |
| :--- | :--- | :--- |
| Validation Metrics | CSV | All validation metrics with targets and actual values |
| Sensitivity Analysis | CSV | Parameter sensitivity scores |
| Validation Plots | PNG | Sensitivity plots, robustness plots, scenario comparison plots |

### 7.3 Validation Report

A written report documenting:
1. Calibration procedure and results
2. Validation procedure and results
3. Sensitivity analysis results
4. Any identified limitations or caveats
5. Final parameter set recommendation

---

## VIII. IF CALIBRATION FAILS

### 8.1 Possible Causes

| Cause | Solution |
| :--- | :--- |
| Parameter bounds too restrictive | Expand parameter ranges |
| Model structure too simple | Add complexity to relevant mechanisms |
| Synthetic data unrealistic | Review data generation assumptions |
| Agent behavior assumptions too rigid | Allow more agent discretion |
| Network structure inappropriate | Test alternative network topologies |

### 8.2 Documentation Required

If calibration fails:
- Document the failure mode
- Document attempted solutions
- Document why solutions did not work
- Propose alternative approaches

---

## IX. RELATION TO OTHER DOCUMENTS

This validation framework is part of the broader IFMP documentation suite. It works with:

| Document | Relationship |
| :--- | :--- |
| `ODD_MODEL_DESCRIPTION.md` | Provides the model description being validated |
| `SIMULATION_FRAMEWORK_SPECIFICATION.md` | Defines the scenarios and parameters being tested |
| `REPUTATION_VALIDATION_LOSS_IMPLEMENTATION_FRAMEWORK.md` | Defines the implementation being validated |
| `data/alpha_dataset.json` | Provides the calibration data |

---

**Document Classification:** Validation Specification  
**Complementary Documents:** All IFMP simulation documents

--- END OF FILE VALIDATION_FRAMEWORK.md ---