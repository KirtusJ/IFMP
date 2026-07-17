--- START OF FILE SIMULATION_RUN_PROTOCOL.md ---

# SIMULATION RUN PROTOCOL
## IFMP-ABM Execution Plan

**Version:** 1.0 (Draft)  
**Status:** Execution Protocol  
**Scope:** This document defines the execution plan for the IFMP-ABM simulation runs. It specifies what runs to perform, in what order, with what resources, and how to handle failures.

---

## I. EXECUTION PHILOSOPHY

### Core Principle: Systematic, Transparent, Reproducible

The simulation runs are designed to be:
- **Systematic:** All combinations are run according to a defined plan
- **Transparent:** All parameters, assumptions, and results are documented
- **Reproducible:** Anyone with the code and data can reproduce the results

---

## II. RUN ARCHITECTURE

### 2.1 Parallelization Strategy

| Level | Description | Parallelization |
| :--- | :--- | :--- |
| **Parameter Combinations** | Different parameter sets | Parallelize across available cores |
| **Replications** | Multiple runs with same parameters | Parallelize within parameter set |
| **Scenarios** | Different scenario conditions | Parallelize across available cores |

**Recommended Setup:**
- Use 32 cores minimum
- Run parameter combinations in parallel
- Each core handles one parameter combination
- Within each core, run replications sequentially (or in parallel if resources allow)

### 2.2 Run Prioritization

| Priority | Runs | Rationale |
| :--- | :--- | :--- |
| **1** | Baseline scenario (Arm A) with baseline parameters | Establishes reference trajectory |
| **2** | Baseline scenario with alternative reputation decay policies | Tests key design variable |
| **3** | Baseline scenario with alternative validator liability structures | Tests key design variable |
| **4** | Baseline scenario with alternative audit funding structures | Tests key design variable |
| **5** | All scenarios (Arms A-E) with baseline parameters | Tests system robustness |
| **6** | Full factorial of most influential parameters | Tests interaction effects |
| **7** | Remaining parameter combinations | Completes the parameter scan |

---

## III. RUN SCHEDULE

### 3.1 Phase 1: Baseline Establishment (Priority 1-4)

| Task | Runs | Time Estimate |
| :--- | :--- | :--- |
| Arm A with baseline parameters | 30 replications | 1-2 hours |
| Arm A with 5 reputation decay policies | 5 × 30 = 150 runs | 4-6 hours |
| Arm A with 3 validator liability structures | 3 × 30 = 90 runs | 2-4 hours |
| Arm A with 3 audit funding structures | 3 × 30 = 90 runs | 2-4 hours |
| **Phase 1 Total** | **360 runs** | **9-16 hours** |

### 3.2 Phase 2: Scenario Testing (Priority 5)

| Task | Runs | Time Estimate |
| :--- | :--- | :--- |
| Arm A (Baseline) with baseline parameters | 30 runs | 1-2 hours |
| Arm B (Financial Shock) with baseline parameters | 30 runs | 1-2 hours |
| Arm C (Regulatory Suppression) with baseline parameters | 30 runs | 1-2 hours |
| Arm D (Low Growth) with baseline parameters | 30 runs | 1-2 hours |
| Arm E (Immigration Surge) with baseline parameters | 30 runs | 1-2 hours |
| **Phase 2 Total** | **150 runs** | **5-10 hours** |

### 3.3 Phase 3: Sensitivity Analysis (Priority 6-7)

| Task | Runs | Time Estimate |
| :--- | :--- | :--- |
| Full factorial of most influential parameters | 27 combinations × 30 = 810 runs | 24-48 hours |
| Remaining parameter combinations | 1,650 - 810 = 840 runs | 24-48 hours |
| **Phase 3 Total** | **1,650 runs** | **48-96 hours** |

### 3.4 Total Runtime Estimate

| Phase | Runs | Time Estimate |
| :--- | :--- | :--- |
| Phase 1 | 360 | 9-16 hours |
| Phase 2 | 150 | 5-10 hours |
| Phase 3 | 1,650 | 48-96 hours |
| **Total** | **2,160 runs** | **62-122 hours** |

**With 32-core parallelization:**
- Runtime = Total time / 32
- Estimated: **2-4 hours for Phase 1-2, 1.5-3 days for Phase 3**

---

## IV. RESOURCE REQUIREMENTS

### 4.1 Computational Resources

| Resource | Minimum | Recommended |
| :--- | :--- | :--- |
| CPU Cores | 8 | 32+ |
| RAM | 16 GB | 64 GB |
| Storage | 50 GB | 200 GB |
| GPU | Not required | Not required |

### 4.2 Data Storage Estimates

| Data Type | Size Estimate | Frequency |
| :--- | :--- | :--- |
| Run outputs (per run) | 10 MB | Per run |
| Aggregated results | 1 GB | Per phase |
| Visualizations | 500 MB | Per phase |
| **Total Storage** | **~30 GB** | **All runs** |

---

## V. RUN MONITORING

### 5.1 Real-Time Monitoring

| Metric | Frequency | Action if Threshold Exceeded |
| :--- | :--- | :--- |
| Run completion rate | Every 10 minutes | Investigate stalled runs |
| Error rate | Every run | Log and investigate errors |
| Resource utilization | Continuous | Scale up/down as needed |

### 5.2 Run Logging

Each run produces:
1. **Run metadata**: timestamp, parameters, scenario, replication number
2. **Time series data**: UBS, DSM, TFP, reputation scores, credit multiplier by year
3. **Summary metrics**: final values, solidification time, reputation Gini
4. **Error logs**: any errors encountered during the run

---

## VI. QUALITY CONTROL

### 6.1 Data Integrity Checks

| Check | Frequency | Action if Failed |
| :--- | :--- | :--- |
| All runs completed | Per phase | Identify and re-run failed runs |
| Data ranges plausible | Per run | Flag and investigate implausible values |
| No missing data | Per run | Identify and re-run with missing data |
| Results consistent across replications | Per parameter set | Investigate outliers |

### 6.2 Failure Handling

| Failure Type | Action |
| :--- | :--- |
| Run fails to complete | Re-run up to 3 times; log failure if persists |
| Run produces implausible values | Flag for review; re-run with adjusted parameters |
| System crash | Resume from last completed checkpoint |
| Data corruption | Restore from backup; re-run corrupted runs |

---

## VII. OUTPUT ORGANIZATION

### 7.1 Directory Structure

```
simulation_outputs/
├── phase_1/
│   ├── baseline/
│   │   ├── reputation_decay/
│   │   │   ├── no_decay/
│   │   │   │   ├── run_001/
│   │   │   │   ├── run_002/
│   │   │   │   └── ...
│   │   │   ├── 24_month/
│   │   │   ├── 36_month/
│   │   │   ├── 48_month/
│   │   │   └── 60_month/
│   │   ├── validator_liability/
│   │   └── audit_funding/
│   └── scenario/
│       ├── arm_a/
│       ├── arm_b/
│       ├── arm_c/
│       ├── arm_d/
│       └── arm_e/
├── phase_2/
│   ├── sensitivity_analysis/
│   └── full_factorial/
└── phase_3/
    ├── aggregated_results/
    ├── visualizations/
    └── reports/
```

### 7.2 Output Formats

| Output Type | Format | Description |
| :--- | :--- | :--- |
| Run data | CSV | Raw run outputs |
| Metadata | JSON | Run parameters and conditions |
| Aggregated results | CSV | Summary metrics across replications |
| Visualizations | PNG/PDF | Figures and charts |
| Reports | Markdown/PDF | Written documentation |

---

## VIII. RUN COMPLETION CRITERIA

### 8.1 Phase Completion

| Phase | Completion Criteria |
| :--- | :--- |
| Phase 1 | All 360 runs completed; data integrity checks passed |
| Phase 2 | All 150 runs completed; data integrity checks passed |
| Phase 3 | All 1,650 runs completed; data integrity checks passed |

### 8.2 Project Completion

| Criterion | Description |
| :--- | :--- |
| All runs completed | All 2,160 runs completed successfully |
| Data integrity passed | All quality control checks passed |
| Aggregated results generated | Summary metrics for all parameter combinations |
| Visualizations generated | All charts and figures produced |
| Report generated | Final simulation report written |

---

## IX. CONTINGENCY PLANS

### 9.1 Resource Limitations

| Limitation | Solution |
| :--- | :--- |
| Insufficient compute resources | Reduce number of replications (30 → 15) |
| Insufficient storage | Compress outputs; increase storage allocation |
| Time constraints | Prioritize Phase 1 and 2; defer Phase 3 |

### 9.2 Model Issues

| Issue | Solution |
| :--- | :--- |
| Model errors | Fix errors; re-run affected runs |
| Unexpected behavior | Investigate; adjust model if necessary |
| Calibration failure | Adjust parameters; re-calibrate |

---

## X. RELATION TO OTHER DOCUMENTS

This run protocol is part of the broader IFMP simulation framework. It works with:

| Document | Relationship |
| :--- | :--- |
| `SIMULATION_FRAMEWORK_SPECIFICATION.md` | Defines the scenarios and parameters being tested |
| `REPUTATION_VALIDATION_LOSS_IMPLEMENTATION_FRAMEWORK.md` | Defines the implementation being run |
| `VALIDATION_FRAMEWORK.md` | Defines the validation criteria |
| `ODD_MODEL_DESCRIPTION.md` | Provides the model being run |

---

**Document Classification:** Execution Protocol  
**Complementary Documents:** All IFMP simulation documents

--- END OF FILE SIMULATION_RUN_PROTOCOL.md ---