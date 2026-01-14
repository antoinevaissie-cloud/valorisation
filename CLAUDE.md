# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **financial analysis project** for evaluating and negotiating an off-market apartment acquisition at 4 rue Paillet, 75005 Paris. It contains CSV-based valuation models and market data—no code, no build pipeline, no tests.

## Data Structure

The analysis flows through numbered CSV files in logical order:

| File | Purpose |
|------|---------|
| `00_Assumptions.csv` | Renovation costs (€/m²), contingency rates |
| `01_Market_Baseline.csv` | Notaires and DVF reference prices |
| `02_Surface_Model.csv` | Property surface measurements (Carrez/non-Carrez) |
| `03_Market_Considerations.csv` | Qualitative adjustments and known costs |
| `04_Risk_Register.csv` | Identified risks and mitigation strategies |
| `05_Market_Value_Synthesis.csv` | €/m² valuation bounds |
| `06_Decision_Framework.csv` | Price targets and walk-away thresholds |
| `07_All-In_Cash_Model.csv` | Total cost of ownership analysis |

## Key Context

**Property:** 58.48 m² Carrez apartment requiring full renovation, in copropriété.

**Buyer Position:** Already owns adjacent apartment. Acquisition enables merger—creating unique strategic value not transferable to other buyers.

**Market Anchors:**
- DVF comparable (same building, 10/2024): €12,200/m² for 100m² in better condition
- Notaires Quartier Sorbonne median: ~€12,600/m²
- Current offer (€800k): implies €13,680/m²—already above market

**Decision Thresholds (from 06_Decision_Framework.csv):**
- Target: ≤€684k (market-rational)
- Stretch: €684k–€778k (justified by adjacency premium)
- Walk-away: >€778k (hits market ceiling)

## Analysis Guidelines

Claude should reason as a **financially disciplined buyer**, not a broker optimizing for headline price.

**Do:**
- Ground all reasoning in DVF/Notaires data
- Factor renovation cost, execution risk, and illiquidity discount
- Distinguish market value from buyer-specific strategic premium
- Recognize silence as a valid negotiation signal
- Challenge assumptions when warranted

**Do Not:**
- Use 2022 peak pricing as reference
- Assume emotional urgency
- Optimize for "deal at any cost"
- Ignore that €800k is already generous given asset condition
