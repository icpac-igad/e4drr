---
title: Interactive Storymaps with NASA VEDA Platform
summary: Building narrative-driven geospatial visualizations using MDX and TiTiler components in NASA's VEDA platform.
date: 2025-07-25

authors:
  # -

tags:
  - Storymaps
  - VEDA
  - TiTiler
  - MDX
---

## NASA VEDA Platform

[VEDA](https://www.earthdata.nasa.gov/dashboard/) (Visualization, Exploration, and Data Analysis) is NASA's open-source Earth Science platform in the cloud. It enables researchers and communicators to create interactive storymaps that combine narrative text with dynamic geospatial visualizations, making complex Earth observation data accessible to broader audiences.

## MDX: Extensible Markdown for Storymaps

VEDA storymaps leverage MDX (Markdown with JSX), allowing authors to embed interactive components directly within markdown documents:

- **Video embeds** - YouTube, Vimeo integration for multimedia narratives
- **Interactive maps** - TiTiler-powered dynamic tile layers
- **Data visualizations** - Charts and graphs rendered from live data
- **Custom React components** - Specialized UI elements for Earth science communication

This extensibility transforms static documents into rich, interactive experiences without requiring frontend development expertise.

## TiTiler Components in VEDA

[TiTiler](https://developmentseed.org/titiler/), developed by Development Seed, provides the dynamic tiling backbone for VEDA visualizations:

| Component | Purpose |
|-----------|---------|
| **TiTiler (Core)** | FastAPI application for on-the-fly COG tile generation |
| **TiTiler-CMR** | Dynamic tiles from NASA Common Metadata Repository queries |
| **TiTiler-pgstac** | STAC-based spatial data queries via PgSTAC |
| **TiTiler-Multidim** | Multidimensional NetCDF/Zarr data support |

### VEDA-Data-Advisor

The [VEDA-Data-Advisor](https://github.com/NASA-IMPACT/veda-data-advisor) is a React single-page application that helps users select the appropriate visualization service based on their data type and requirements. It routes requests to the correct TiTiler instance configuration.

## Deployment Architecture

VEDA deployments configure TiTiler instances through the [veda-deploy](https://github.com/NASA-IMPACT/veda-deploy) repository, orchestrating:

- Cloud-optimized data access patterns
- Scalable tile serving infrastructure
- Integration with NASA CMR for data discovery
- Authentication and access control

## Application for Climate Storylines

This architecture enables creating event-based climate storylines that combine:
- Satellite imagery time series
- Model outputs and forecasts
- Impact assessments
- Narrative context for decision-makers

## Resources

- [NASA VEDA Dashboard](https://www.earthdata.nasa.gov/dashboard/)
- [TiTiler Documentation](https://developmentseed.org/titiler/)
- [VEDA GitHub Organization](https://github.com/NASA-IMPACT)


