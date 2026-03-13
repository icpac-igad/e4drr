---
title: Continuous Risk Monitoring and Assessment - A Bayesian Network Framework for Flood and Drought in East Africa
summary: Formalizing hydrometeorological early warning into an auditable, evidence-driven Bayesian risk assessment process for operational impact-based forecasting.
date: 2026-01-15

authors:
  # -

tags:
  - Bayesian Networks
  - CRMA
  - Impact-Based Forecasting
  - Flood
  - Drought
  - East Africa
---

*This post is a continuation of the earlier discussion on [Decision-Centric Verification for Impact-Based Forecasting](/e4drr/blog/2024-12-dcv/), which introduced Bayesian frameworks and event-based storylines as tools for aligning forecasts with real-world decision-making.*

## From Verification to Continuous Monitoring

The [decision-centric verification (DCV) framework](/e4drr/blog/2024-12-dcv/) shifted the question from "Was the forecast accurate?" to "Did the forecast lead to better decisions?". Extending this logic further: rather than verifying decisions after the fact, can we build a system that continuously updates risk assessments as new evidence arrives—before the decision window closes?

This is the premise of **Continuous Risk Monitoring and Assessment (CRMA)**.

## CRMA: A Concept from Finance and Cyber-Risk

CRMA is well-established in financial auditing and cyber-risk management, where risk states are updated in real-time and escalated as conditions evolve. The core idea is simple: risk is not a static score computed once, but a continuously revised state conditioned on accumulating evidence.

Hydrometeorological early warning systems already operate this way in practice—daily flood monitoring, monthly drought tracking, seasonal outlooks—but often informally and without a unified probabilistic framework that is transparent, auditable, and reproducible.

The CRMA framework introduced here formalizes these existing monitoring practices into a **continuous, conditional, evidence-driven hydrometeorological risk assessment process**, where evolving observations, forecasts, and expert knowledge are systematically integrated, documented, and auditable across time.

## Bayesian Networks as the Engine

The technical core of the framework is the **Bayesian Network (BN)**—a probabilistic graphical model that encodes causal relationships between variables through directed acyclic graphs. As discussed in the DCV post (referencing [Vogel et al., 2014](https://nhess.copernicus.org/articles/14/2605/2014/)), BNs are well-suited to natural hazard analysis because they:

- Represent compound risk mechanisms explicitly
- Handle incomplete or uncertain observations
- Encode expert knowledge through **Conditional Probability Tables (CPTs)**
- Produce interpretable, uncertainty-quantified outputs

In the CRMA framework, BNs aggregate multiple forecast and observation streams into a single risk state, updated as new data arrives. CPTs serve as the structured record of expert knowledge—transparent, reviewable, and versioned over time—directly supporting the auditable decision histories that the DCV framework demands.

## Two Hazard Contexts: Drought and Flood

### Drought: Seasonal Evidence Accumulation

Drought risk is inherently slow-moving, building across agricultural seasons. The framework combines:

- **Observed antecedent conditions** — multi-month Combined Drought Indicators (CDI) derived from satellite and in-situ observations
- **Seasonal forecasts** — ECMWF SEAS5 Standard Precipitation Index (SPI) ensemble forecasts across the primary agricultural seasons (MAM and OND)

The BN encodes how antecedent moisture deficits interact with forecast signals to produce compound drought risk, incorporating temporal persistence—a key mechanism where drought conditions reinforce themselves across months.

### Flood: Short-Range Fusion

Flood risk requires integrating faster-evolving signals. The framework fuses:

- **Antecedent rainfall and soil saturation** — derived from satellite observations (e.g., GPM, ASCAT)
- **Short-range ensemble precipitation forecasts** — from NOAA GEFS

Here the BN captures a compound mechanism: saturated soils amplify the flood response to incoming rainfall in a way that is non-linear and context-dependent. CPTs encode this interaction based on expert knowledge of regional hydrology.

## Outputs: Traffic-Light Risk at Admin-1 Level

The framework produces **admin-1–level (district) risk categories** in a traffic-light format—linked directly to anticipatory action pathways. This design reflects the DCV principle: risk outputs are structured around decision thresholds, not just probabilistic scores.

Risk categories include spatial coverage metrics and data confidence indicators, ensuring that the uncertainty in the underlying observations is visible to decision-makers rather than absorbed silently into the model.

## Implementation: Reproducible and Operational

The framework was validated using the Python [pgmpy](https://pgmpy.org/) library for BN inference. Key components of the operational stack include:

- **Workflow automation** — scheduled, repeatable risk computation
- **Calendar-based web application** — for operational teams to navigate risk histories and current states
- **Structured CPT management** — versioned tables that make expert knowledge updates traceable and auditable
- **Analysis-ready, cloud-optimized datasets** — enabling consistent, reproducible data access across runs

The combination of these tools supports the auditable decision history that CRMA demands: not just what the risk level was today, but why, based on which evidence, and using which version of expert knowledge.

## Storymaps and Climate Storylines

Integration with **Storymaps** complements the quantitative risk framework with event-based climate storylines—a concept discussed in the DCV post referencing [Sillmann et al. (2021)](https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2020EF001783). Where the BN provides probabilistic risk inference, storymaps provide the narrative structure that links risk knowledge to operational communication and stakeholder understanding—addressing both the technical and communicative dimensions of impact-based forecasting.

## Implications for E4DRR

For the E4DRR context, the CRMA framework offers a pathway from ad hoc monitoring practices to a systematic, auditable risk assessment system. The key contributions are:

1. **Formalisation** — existing expert knowledge encoded in CPTs rather than held implicitly
2. **Continuity** — risk states updated operationally, not computed episodically
3. **Auditability** — every risk assessment traceable to its evidence and assumptions
4. **Interoperability** — connects to anticipatory action triggers, storymaps, and forecast pipelines

The pilot study demonstrates that parsimonious BN modelling—when combined with cloud-optimized data infrastructure and structured knowledge management—can deliver operational-grade continuous risk monitoring without requiring large-scale computational resources.

## Resources

- [Complex Risk Analytics Fund (CRAF'd)](https://www.craf-d.com/)
- [pgmpy: Probabilistic Graphical Models in Python](https://pgmpy.org/)
- [Vogel et al. (2014) - Bayesian network learning for natural hazard analyses](https://nhess.copernicus.org/articles/14/2605/2014/)
- [ECMWF SEAS5 Seasonal Forecasts](https://www.ecmwf.int/en/forecasts/documentation-and-support/long-range/seasonal-forecast-documentation/seas5)
- [NOAA GEFS Ensemble Forecasts](https://www.ncei.noaa.gov/products/weather-climate-models/global-ensemble-forecast)
