--- START OF FILE README.md ---

# IFMP-ABM: Integrated Federated Mutualist Protocol
## Agent-Based Modeling for Economic Transition

**Version:** 1.4 (Draft)  
**License:** MIT  
**Status:** Research Prototype  
**Author:** Kirtus J.

---

## Overview

The **Integrated Federated Mutualist Protocol (IFMP)** is a draft proposal for a systems-engineering framework for economic transition. It draws on two historical traditions—Georgism and Mutualism—and proposes that they are not separate theories but complementary halves of a single unified framework: **Mutualist Georgism**.

**Core Insight:** IFMP does not abolish markets, money, or private property. It **redirects** the flow of wealth created by global trade back to its sources—labor, innovation, and production capacity. This is not redistribution. It is **reduction of friction**. Extractive mechanisms (land rent, interest, IP royalties, and cross-border wealth capture) are not eliminated; they are redirected to more efficient purposes.

**Key Principle:** IFMP is not designed to govern markets. It is designed to govern the **transition** from a cash-based economy to a **cash-contribution hybrid economy**—a gradient where UBS (cashless essential services) and DSM (cash-based discretionary exchange) coexist in dynamic equilibrium.

This repository contains the complete Agent-Based Model (ABM) simulation, conceptual documentation, and research paper.

---

### Why Efficiency, Not Redistribution

IFMP is not a redistribution mechanism. It is an **efficiency optimization protocol**.

Today, global trade generates enormous wealth. But much of it is captured before it reaches producers—through:

| Extraction Type | Mechanism | IFMP Redirects To |
| :--- | :--- | :--- |
| **Wage Extraction** | Employers capture surplus value | LMF worker ownership |
| **Resource Extraction** | Landowners capture rent | LVC public use |
| **Dividend Extraction** | Financiers capture interest | MCC productive investment |
| **Polity Extraction** | Cross-border wealth capture | SDR global coordination |

Redirecting wealth back to its sources is not about taking from the rich and giving to the poor. It is about **reducing system friction** so that value flows more efficiently to where it creates the most growth, innovation, and shared prosperity.

---

## Key Components

- **Four-Dimensional Dynamic Gradient** (UBS, DSM, TFP, Time)
- **IFMP Mechanisms** (LVC, MCC, LMF, DEAP, ATD, TMC)
- **Full ABM Implementation** in Python/Mesa
- **Academic Paper** with simulation results

---

## Repository Structure

```
IFMP-ABM/
├── README.md                    # Project overview
├── LICENSE                      # MIT License
├── requirements.txt             # Python dependencies
├── setup.py                     # Installation script
├── paper/
│   └── paper.md                 # Complete academic paper
├── src/
│   ├── models/                  # ABM implementation
│   ├── mechanisms/              # IFMP mechanisms (LVC, MCC, LMF, DEAP, TMC)
│   ├── dynamics/                # Core equations & diffusion
│   └── environment/             # Regions, resources, networks
├── data/                        # Datasets
│   ├── alpha_dataset.json       # Synthetic data
│   └── key_metrics.csv          # Simulation metrics
├── docs/                        # Documentation
│   ├── EXECUTIVE_SUMMARY.md
│   ├── FAQ.md
│   ├── GLOSSARY.md
│   └── SIMULATION_FRAMEWORK_SPECIFICATION.md
├── visualizations/              # Generated figures
└── notebooks/                   # Analysis notebooks
```

---

## Installation

```bash
# Clone the repository
git clone https://github.com/KirtusJ/IFMP-ABM.git
cd IFMP-ABM

# Install dependencies
pip install -r requirements.txt
```

---

## Usage

```bash
# Run the simulation
cd src
python models/complete_model.py

# Run the analysis notebook
jupyter notebook notebooks/analysis.ipynb
```

---

## Key Results

The simulation models the transition of the Alpha economy from 2000 to 2050 under IFMP mechanisms. The "green coordinate" (UBS ≥ 0.85, DSM ≥ 0.70, TFP ≥ 2.0) represents a high-stability equilibrium on the gradient—not an endpoint, but a reference point for continued evolution.

| Scenario | Final UBS | Final DSM | Final TFP | Green Coordinate Reached? |
| :--- | :--- | :--- | :--- | :--- |
| Baseline | 0.87 | 0.72 | 2.15 | ✅ (2043) |
| Financial Shock | 0.84 | 0.69 | 2.08 | ❌ (near) |
| Regulatory Suppression | 0.76 | 0.61 | 1.85 | ❌ |
| Low Growth | 0.74 | 0.58 | 1.45 | ❌ |
| Immigration Surge | 0.86 | 0.74 | 2.20 | ✅ (2046) |

**Key Insight:** IFMP successfully guides the economy toward the green coordinate under baseline and immigration surge scenarios. The system shows resilience under financial shock, regulatory suppression, and low growth conditions—though low growth delays convergence, it does not cause collapse.

---

## Documentation

Complete documentation is available in the `/docs` directory:

- **Executive Summary** – 1-2 page overview
- **FAQ** – Common questions and responses
- **Glossary** – Terms and acronyms
- **Simulation Framework** – ABM architecture and parameters

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Citation

If you use this work, please cite:

```
Kirtus J. (2026). IFMP-ABM: Agent-Based Modeling for Economic Transition.
GitHub Repository. https://github.com/KirtusJ/IFMP-ABM
```

---

## Acknowledgments

This work builds on the intellectual traditions of:
- **Henry George** (Land Value Capture)
- **Pierre-Joseph Proudhon** (Mutual Credit)
- **Elinor Ostrom** (Commons Governance)
- **The Cooperative Movement** (Worker Ownership)

---

## Contact

- **Author:** Kirtus J.
- **GitHub:** [KirtusJ](https://github.com/KirtusJ)
