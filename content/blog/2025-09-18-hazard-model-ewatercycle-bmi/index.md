---
title: FAIR Hazard Modeling - Reproducible Hydrological Frameworks
summary: Exploring FAIR principles for reproducible hazard modeling using wflow.jl, and RIM2D.
date: 2025-09-18

authors:
  # -

tags:
  - FAIR
  - eWaterCycle
  - wflow.jl
  - RIM2D
  - Hazard Modeling
---

## The Standards Problem

The classic XKCD cartoon captures a familiar dilemma: faced with 14 competing standards, someone creates a 15th "universal" standard—resulting in 15 competing standards. Yet sometimes standardization genuinely solves interoperability challenges, particularly when grounded in principled frameworks like FAIR.

## FAIR Principles for Hydrological Modeling

The FAIR principles—Findable, Accessible, Interoperable, and Reusable—originally developed for research data, have profound implications for computational hydrology. A [comprehensive review in Water Resources Research](https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2021WR031753) examines how these principles apply to hydrological modeling workflows, highlighting challenges in:

- **Findability** - Locating appropriate models for specific applications
- **Accessibility** - Obtaining models with clear licensing and documentation
- **Interoperability** - Coupling models through standardized interfaces
- **Reusability** - Reproducing results across different computing environments

The paper argues that achieving FAIR hydrology requires not just open-source code, but systematic attention to metadata, provenance tracking, and containerized execution environments.

## Basic Model Interface: Enabling Interoperability

The [Basic Model Interface (BMI)](https://bmi.csdms.io/en/latest/) from CSDMS addresses the interoperability challenge through standardization. Consider how drivers benefit from familiar vehicle controls—steering wheels, brake pedals, and speedometers work predictably whether operating a compact car or heavy truck. BMI brings this philosophy to numerical models through a set of standard control and query functions.

BMI-compliant models expose consistent methods for:
- **Initialization** - Setting up model state and parameters
- **Time stepping** - Advancing the simulation
- **Data exchange** - Getting and setting variable values
- **Finalization** - Cleaning up resources

This standardization enables model coupling and platform integration while supporting FAIR principles—models become more findable through registries, accessible through common APIs, interoperable through shared interfaces, and reusable across computing environments.

## eWaterCycle: A Reproducible Modeling Platform

The [eWaterCycle](https://www.ewatercycle.org/) project directly addresses FAIR challenges through a platform for reproducible hydrological experiments. Their [GMD paper](https://gmd.copernicus.org/articles/15/5371/2022/) describes an architecture leveraging BMI-wrapped models within containerized environments. This combination enables eWaterCycle to orchestrate diverse hydrological models through a unified interface while ensuring reproducibility across computing platforms.

The [eWaterCycle model landscape](https://www.ewatercycle.org/Landscape.html) includes adapters for various models, though maintenance varies across implementations. Recent GitHub discussions reveal ongoing challenges:
- [wflow.jl integration](https://github.com/eWaterCycle/ewatercycle-wflowjl/issues/15) - Exploring Julia-based modeling within eWaterCycle
- [HYPE model support](https://github.com/eWaterCycle/ewatercycle-hype/issues/5#issuecomment-3311200321) - Community efforts to maintain model wrappers

These discussions illustrate both the promise and maintenance burden of supporting multiple models through standardized interfaces.

## Parsimonious Models for Operational Hazard Forecasting

For impact-based forecasting, computational efficiency matters as much as physical accuracy. Two models stand out for their balance of parsimony and FAIR compliance:

### wflow.jl - Distributed Hydrological Modeling

[wflow.jl](https://github.com/Deltares/Wflow.jl), written in Julia, provides distributed hydrological modeling with excellent computational performance. The [GMD paper](https://gmd.copernicus.org/articles/17/3199/2024/) demonstrates its efficiency for large-domain applications, making it suitable for:
- Soil moisture monitoring
- Drought index calculation
- Streamflow forecasting

The Julia implementation offers significant speed advantages over Python equivalents while maintaining scientific rigor. Its open-source nature and growing BMI support position it well for FAIR-compliant workflows.

### RIM2D - Rapid Flood Inundation Modeling

For hydrodynamic hazard modeling, [RIM2D](https://www.frontiersin.org/journals/water/articles/10.3389/frwa.2024.1310182/full) offers a parsimonious approach to flood inundation simulation. By simplifying the shallow water equations while preserving essential dynamics, RIM2D enables rapid scenario analysis for:
- Real-time flood forecasting
- Ensemble-based uncertainty quantification
- Impact assessment at scale

## Implications for E4DRR

The combination of FAIR principles, eWaterCycle orchestration, and parsimonious models like wflow.jl and RIM2D presents a pathway for operational hazard modeling in East Africa. Rather than building monolithic systems, this approach favors:

1. **Modular components** - Swap models as better alternatives emerge
2. **Reproducible workflows** - Containerized environments ensure consistency
3. **Computational efficiency** - Run ensemble forecasts within operational time constraints
4. **Provenance tracking** - Document model configurations and input data sources

The challenge remains maintaining standardized wrappers and ensuring compatibility as upstream models evolve—the ongoing cost of interoperability that the XKCD cartoon humorously acknowledges.

## Resources

- [FAIR Principles for Hydrology (WRR)](https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2021WR031753)
- [eWaterCycle Platform Paper (GMD)](https://gmd.copernicus.org/articles/15/5371/2022/)
- [eWaterCycle Project](https://www.ewatercycle.org/)
- [wflow.jl Paper (GMD)](https://gmd.copernicus.org/articles/17/3199/2024/)
- [RIM2D Paper (Frontiers)](https://www.frontiersin.org/journals/water/articles/10.3389/frwa.2024.1310182/full)
- [Basic Model Interface Documentation](https://bmi.csdms.io/en/latest/)
