--- START OF FILE SIMULATION_FRAMEWORK_SPECIFICATION_v1.1.md ---

# SIMULATION FRAMEWORK SPECIFICATION
## Agent-Based Modeling (ABM) for Mutualist Georgism

**Version:** 1.0 (Draft)  
**Status:** Technical Specification for Simulation  
**Scope:** This document defines the architecture, parameters, and test protocols for simulating the Integrated Federated Mutualist Protocol (IFMP) using Agent-Based Modeling (ABM). The goal is to validate the core hypotheses of Mutualist Georgism and identify potential failure modes before real-world implementation.

---

## I. SIMULATION OBJECTIVES

The simulation is designed to test the following propositions derived from the theoretical framework:

1. **Multiplicative Dividend:** Does TFP growth exhibit super-additive (\(n^2\)) characteristics under open-source IP replication, compared to linear growth under proprietary regimes?

2. **Sectoral Decommodification:** Do Utility Layer goods asymptotically approach near-zero marginal cost within T+10 cycles, triggering programmed decommodification?

3. **Credit Solvency:** Does endogenous MCC credit volume remain within ±15% of physical output growth, preventing speculative bubbles?

4. **Governance Robustness:** Does ATD (Algorithmic Temporal Decay) prevent managerial entrenchment and sustain distributed agency?

5. **Resilience:** Can the protocol survive adversarial interventions (regulatory suppression, supply shocks) without catastrophic failure?

6. **Populism Prevention:** Under demographic change (immigration surge), does populist sentiment remain low due to UBS, infrastructure maintenance, and cultural autonomy?

7. **Post-Labor Stability:** If labor becomes optional, does the system remain stable and meaningful?

---

## II. MODEL ARCHITECTURE

### A. Agent Types

| Agent Type | Description | Behavior |
| :--- | :--- | :--- |
| **LMF (Labor-Managed Firm)** | Worker-owned production unit | Produces goods; participates in MCC; allocates capital based on LSQ; participates in governance (ATD-weighted) |
| **Household** | Individual or family unit | Consumes UBS and DSM goods; may participate in governance; may work in LMF or DSM |
| **Clearinghouse (MCC Node)** | Federated financial intermediary | Issues cost-basis credit; tracks bilateral ledgers; synchronizes credit with output |
| **SDR Reserve** | Federated capital pool | Manages LVC revenue; allocates R&D funding; maintains RARR buffer |
| **State Actor (Optional)** | External sovereign entity | May adopt, resist, or suppress IFMP protocols (for hostile interaction testing) |
| **Peer Validator** | LMF or clearinghouse node | Reviews production claims before MCC credit issuance; liability structure configurable |

### B. Environment

| Element | Description |
| :--- | :--- |
| **Geography** | Grid-based or network-based representation of regions with varying resource availability |
| **Resources** | Land (variable quality), energy, water, raw materials |
| **Goods** | Utility Layer (UBS) and Discretionary Layer (DSM) categories |
| **Technology** | Open-source IP protocols; TFP gains propagate across connected nodes |
| **Time** | Discrete cycles (1 cycle = 1 year; simulation runs for 10-20 cycles) |

### C. Core Processes

| Process | Description |
| :--- | :--- |
| **LVC Collection** | 100% levy on unimproved land value; revenue flows to SDR |
| **MCC Credit Issuance** | Cost-basis credit (0.5-1.0% administrative fee) against future production |
| **LSQ Capital Allocation** | Investment flows to projects with highest Labor-Saving Quotient |
| **ATD Governance Weight Decay** | Strategic weight decays over 36-month half-life |
| **TMC Decommodification Trigger** | Sector transitions to UBS when marginal cost < 0.5% of historical price |
| **Open-Source Replication** | Efficiency gains propagate across federated nodes |

---

## III. PARAMETER BOUNDS

### A. Fixed Parameters (Proposed Starting Points)

| Parameter | Value | Unit | Source |
| :--- | :--- | :--- | :--- |
| LVC Levy | 100% | % of unimproved land value | Technical Spec II.1 |
| LTD Cap | 5% | year-over-year increase | Technical Spec II.2 |
| RARR Buffer | 200% | of output std deviation | Technical Spec II.4 |
| MCC Admin Fee | 0.5 - 1.0 | % per clearing cycle | Technical Spec III.2 |
| ATD Half-Life | 36 | months | Technical Spec IV.2 |
| TMC Threshold | 0.5 | % of historical price | Technical Spec V.1 |

### B. Variable Parameters (To Be Calibrated)

| Parameter | Description | Range |
| :--- | :--- | :--- |
| Population Size | Number of households | 100 - 10,000 |
| LMF Count | Number of production units | 10 - 1,000 |
| Initial Technology Level | Starting TFP baseline | 0.1 - 1.0 |
| Resource Availability | Regional variation | 0.5 - 2.0x baseline |
| Participation Rate | % of households active in governance | 10% - 80% |
| Adoption Rate | % of LMFs using open-source protocols | 0% - 100% |
| Immigration Rate | % population increase per cycle | 0% - 5% |

### C. Design Variables (Open Questions to be Tested)

| Variable | Description | Candidate Values | Purpose |
| :--- | :--- | :--- | :--- |
| **Reputation Decay Policy** | Whether credit reputation decays over time or accumulates indefinitely | Cumulative (no decay), 24-month half-life, 36-month half-life, 48-month half-life, 60-month half-life | Test entrenchment dynamics vs. new entrant access |
| **Validator Liability Structure** | Liability structure for peer validators | No liability, individual liability, joint-and-several liability | Test collusion risk vs. validator accountability |
| **Audit Funding Structure** | Funding mechanism for SDR audit function | LVC-dependent, independent, hybrid | Test auditor independence vs. system integration |
| **Loss-Absorption Thresholds** | Thresholds for clearinghouse vs. SDR absorption | Clearinghouse limit: 10-30% of capital; SDR trigger: 30-50%; Systemic: 50-100% | Test loss mutualization vs. individual accountability |

### D. Shock Parameters (For Resilience Testing)

| Shock Type | Description | Magnitude |
| :--- | :--- | :--- |
| Supply Shock | Resource availability reduction | 3σ event |
| Regulatory Suppression | State actor bans IFMP protocols | Binary (On/Off) |
| Credit Crisis | MCC clearinghouse failure | 1-3 node failures |
| Participation Collapse | Governance participation drops to 5% | 5% active |

---

## IV. SIMULATION ARMS

### Arm A: Baseline Trajectory (Optimal Conditions)

**Purpose:** Establish reference TFP growth curves, price trajectories, and credit stability in a favorable environment.

**Conditions:**
- No external shocks.
- Moderate participation (40-60%).
- Gradual adoption of open-source protocols.
- No regulatory suppression.
- Moderate immigration (1-2% per cycle).

**Key Outputs:**
- TFP growth curve (linear vs. multiplicative).
- Price deflation trajectory for Utility Layer goods.
- MCC credit volume vs. physical output correlation.
- ATD governance turnover rate.
- Populist sentiment index.
- **Reputation score distribution** across LMFs (testing entrenchment).

---

### Arm B: Shock Analysis (Stress Testing)

**Purpose:** Validate RARR adequacy and system robustness under adverse conditions.

**Conditions:**
- 3σ supply shock at T+2.
- Recovery period (5 cycles).
- Moderate participation maintained.

**Key Outputs:**
- SDR drawdown rate during crisis.
- MCC credit contraction (if any).
- LMF bankruptcy rate.
- Recovery time to pre-shock output.
- **Peer validation performance** during crisis (tracking collusion or erosion).

---

### Arm C: Hostile Interaction (Regulatory Suppression)

**Purpose:** Test Module VIII resilience ("Asymmetric Jurisdictional Shadowing").

**Conditions:**
- State actor suppresses IFMP protocols at T+3.
- IFMP nodes attempt to relocate/re-seed.
- Dual-jurisdictional operation.

**Key Outputs:**
- Node survival rate post-suppression.
- SDR accessibility across jurisdictions.
- Network fragmentation (number of isolated nodes).
- Time to network re-stabilization.
- **Audit function independence** under regulatory pressure.

---

### Arm D: Low-Growth Scenario (Flat TFP)

**Purpose:** Validate system stability without TFP growth.

**Conditions:**
- TFP growth near zero (0-0.5% per cycle).
- Moderate participation.
- No external shocks.
- Moderate immigration.

**Key Outputs:**
- UBS sustainability.
- DSM health.
- Populist sentiment index.
- Infrastructure maintenance.
- **Reputation score** dynamics under low-growth conditions.

---

### Arm E: Demographic Change (Immigration Surge)

**Purpose:** Test populism-prevention mechanism.

**Conditions:**
- Immigration surge (3-5% per cycle) starting T+2.
- Moderate participation.
- No external shocks.

**Key Outputs:**
- Populist sentiment index.
- Infrastructure strain and expansion.
- UBS coverage.
- DSM cultural diversity.
- LMF innovation rate.
- **Peer validation network** resilience under rapid expansion.

---

## V. DATA COLLECTION AND METRICS

### A. Primary Metrics

| Metric | Definition | Target |
| :--- | :--- | :--- |
| **TFP Growth** | Annual % increase in total factor productivity | > 5% compounding |
| **Price Deflation** | % decline in Utility Layer prices | > 90% by T+10 |
| **Credit-Output Ratio** | MCC credit volume / physical output | 0.85 - 1.15 |
| **Governance Turnover** | % of strategic decision-weight renewed annually | > 20% |
| **SDR Reserve Ratio** | SDR balance / output std deviation | > 200% |
| **Node Survival** | % of LMFs surviving hostile conditions | > 70% |
| **Populist Sentiment** | % of population expressing anti-system sentiment | < 20% |

### B. Design Variable Metrics (Testing Open Questions)

| Metric | Purpose | Tested In |
| :--- | :--- | :--- |
| **Reputation Gini Coefficient** | Track concentration of credit access across LMFs | All Arms |
| **Validator Collusion Index** | Measure of correlated false validations | Arms B, C |
| **Audit Independence Score** | Measure of auditor dependence on audited nodes | Arms C, E |
| **Loss Absorption Cascade** | Distribution of loss absorption across clearinghouse/SDR levels | Arm B |

### C. Secondary Metrics

| Metric | Purpose |
| :--- | :--- |
| **Gini Coefficient** | Track wealth/income distribution |
| **Labor-Hour Reduction** | Time-dividend realization |
| **DSM Exchange Volume** | Health of discretionary market |
| **Participation Rate** | Governance engagement levels |
| **Innovation Rate** | New LSQ improvements per cycle |
| **Infrastructure Quality** | Maintenance and expansion |

---

## VI. IMPLEMENTATION REQUIREMENTS

### A. Technical Requirements

| Requirement | Description |
| :--- | :--- |
| **Modeling Framework** | ABM platform (NetLogo, Mesa, or custom) |
| **Computational Resources** | Sufficient for 10,000+ agents at 10-year simulations |
| **Data Storage** | Time-series database for metric tracking |
| **Visualization** | Dashboard for real-time metric monitoring |
| **Version Control** | Track parameter changes and simulation runs |

### B. Modeler Requirements

| Skill | Description |
| :--- | :--- |
| **ABM Experience** | Familiar with agent-based modeling frameworks |
| **Economic Literacy** | Understanding of TFP, credit, and market dynamics |
| **Statistical Analysis** | Ability to interpret simulation outputs |
| **Parameter Calibration** | Experience with sensitivity analysis |

---

## VII. PHASED IMPLEMENTATION

### Phase 1: Core Model Development (Months 1-3)

- Implement basic agents (LMF, Household, Clearinghouse).
- Implement core processes (LVC, MCC, LSQ, ATD).
- Implement baseline parameter set.
- Validate against known economic behavior (sanity checks).
- **Implement design variables as configurable parameters** (reputation decay, validator liability, audit funding, loss thresholds).

### Phase 2: Arm A Execution (Months 4-6)

- Run Baseline Trajectory simulations.
- Collect TFP, price, and credit metrics.
- Refine parameters based on initial results.
- Establish reference curves.
- **Test reputation decay candidates** (cumulative vs. multiple half-lives).

### Phase 3: Arm B Execution (Months 7-9)

- Introduce supply shocks.
- Test RARR adequacy.
- Document recovery dynamics.
- Refine reserve ratio if necessary.
- **Test validator liability structures** (no liability, individual, joint-and-several).

### Phase 4: Arm C Execution (Months 10-12)

- Implement regulatory suppression scenarios.
- Test jurisdictional shadowing.
- Document survival and recovery dynamics.
- Refine resilience mechanisms.
- **Test audit funding structures** (LVC-dependent, independent, hybrid).

### Phase 5: Arm D and E Execution (Months 13-16)

- Run Low-Growth scenarios.
- Run Demographic Change scenarios.
- Test populism-prevention mechanisms.
- Document stability under adverse conditions.
- **Test loss-absorption thresholds** (clearinghouse vs. SDR levels).

### Phase 6: Analysis and Synthesis (Months 17-18)

- Aggregate results across all arms.
- Compare against theoretical predictions.
- Identify failure modes and parameter sensitivities.
- Produce simulation report.
- **Recommend design variable values** based on simulation outcomes.

---

## VIII. SUCCESS CRITERIA SUMMARY

| Criteria | Arm A (Baseline) | Arm B (Shock) | Arm C (Hostile) | Arm D (Low-Growth) | Arm E (Immigration) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| TFP Growth | > 5% comp. | > 3% post-shock | > 2% post-suppression | > 0.5% | > 3% |
| Price Deflation | > 90% by T+10 | > 70% by T+10 | > 60% by T+10 | > 50% by T+10 | > 80% by T+10 |
| Credit-Output Ratio | ±10% | ±15% | ±20% | ±15% | ±10% |
| SDR Reserve | > 200% | > 100% | > 80% | > 150% | > 150% |
| Node Survival | > 95% | > 90% | > 70% | > 95% | > 90% |
| Governance Turnover | > 20% | > 15% | > 10% | > 15% | > 20% |
| Populist Sentiment | < 10% | < 15% | < 20% | < 15% | < 20% |

### Design Variable Success Criteria

| Design Variable | Success Indicator | Failure Indicator |
| :--- | :--- | :--- |
| **Reputation Decay** | New entrants can access credit within 3-5 cycles; reputation Gini < 0.4 | Reputation Gini > 0.6; entrenched core dominates credit |
| **Validator Liability** | Collusion index < 0.1; validation accuracy > 90% | Collusion index > 0.3; validation accuracy < 70% |
| **Audit Funding** | Audit independence score > 0.8; no systematic bias | Audit independence score < 0.5; systematic pro-node bias |
| **Loss Absorption** | System recovers within 5 cycles; no node cascade | System takes > 10 cycles to recover; node cascade occurs |

---

## IX. OPEN QUESTIONS FOR MODELERS

1. **Calibration:** What is the optimal initial technology level and resource distribution for realistic baseline behavior?

2. **Participation Dynamics:** How do we model varying participation rates and their impact on governance quality?

3. **Adoption Rate:** What is the realistic adoption curve for open-source IP protocols across LMFs?

4. **Regional Variation:** How should we model regional differences in resource availability and TMC thresholds?

5. **Feedback Loops:** How do we account for secondary effects (e.g., time-dividends leading to increased leisure and reduced production)?

6. **State Behavior:** How should we model state actor decision-making in hostile interaction scenarios?

7. **Immigration Dynamics:** How do we model the integration of new households and their impact on culture and infrastructure?

8. **Reputation Convergence:** How do we measure and model the convergence of reputation scores across LMFs under different decay policies?

9. **Validator Incentives:** How do we model validator incentives under different liability structures?

10. **Auditor Independence:** How do we measure and model auditor independence under different funding structures?

These questions are offered as invitations for refinement, not as barriers to simulation.

---

## X. RELATION TO FULL PROJECT

This Simulation Framework Specification is part of the broader IFMP documentation suite. It translates the theoretical and technical specifications into testable propositions.

**Related Documents:**
- `paper/paper.md` — Core propositions
- `docs/EXECUTIVE_SUMMARY.md` — Overview
- `docs/FAQ.md` — Common questions
- `docs/GLOSSARY.md` — Terms and acronyms
- `ODD_MODEL_DESCRIPTION.md` — Model description

---

**Document Classification:** Technical Specification / Simulation Framework  
**Complementary Documents:** All IFMP primary documents  
**Status:** Draft for Review

--- END OF FILE SIMULATION_FRAMEWORK_SPECIFICATION_v1.1.md ---