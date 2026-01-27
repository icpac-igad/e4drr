---
title: Learning eoAPI - Deploying Titiler and TiPG
summary: A beginner-friendly approach to understanding eoAPI by deploying its core components on Replit without Kubernetes complexity.
date: 2025-07-25

authors:
  # -

tags:
  - eoAPI
  - Titiler
  - TiPG
  - STAC
---

## Introduction to eoAPI

[eoAPI](https://github.com/developmentseed/eoAPI) is an open-source ecosystem developed by Development Seed for building Earth Observation (EO) data APIs. It provides a complete stack for discovering, cataloging, and serving geospatial data through modern cloud-native patterns. The ecosystem follows the SpatioTemporal Asset Catalog (STAC) specification, making it interoperable with the broader geospatial data community.

Traditional eoAPI deployments rely on Kubernetes and Docker orchestration, which can be complex for newcomers. However, understanding the individual components separately offers a gentler learning curve before tackling the full infrastructure.

## Core Components: Titiler and TiPG

### Titiler - Dynamic Raster Tile Server

[Titiler](https://github.com/developmentseed/titiler) is a dynamic tile server for Cloud Optimized GeoTIFFs (COGs) and other raster formats. It generates map tiles on-the-fly without pre-processing, enabling efficient visualization of large raster datasets. Titiler integrates with PgSTAC to serve tiles directly from STAC catalog items, making it essential for any EO visualization workflow.

### TiPG - Vector Tile Server

[TiPG](https://github.com/developmentseed/tipg) (Tiles from PostGIS) serves vector tiles in Mapbox Vector Tile (MVT) format directly from PostGIS databases. It enables efficient streaming of vector data like administrative boundaries, river networks, and point features without pre-generating tile pyramids.

## Learning Through Simplified Deployment

A practical approach to learning eoAPI involves deploying Titiler and TiPG outside the typical Kubernetes setup. Using platforms like Replit with built-in PostgreSQL and AI agent support provides an accessible starting point for experimentation.

### Replit Templates

- [Titiler + PgSTAC Template](https://replit.com/@e4drr/TitilerPgstac-template)
- [TiPG + Tiler Template](https://replit.com/@e4drr/TipgTiler-template)

These templates simplify the learning process by handling common deployment challenges like reverse proxy configuration, allowing focus on understanding how the services work.

### Example Applications

**COG Visualization with Titiler:** A hands-on example demonstrating raster tile serving from a Replit-deployed endpoint.
- [Titiler Tiles COG Notebook](https://github.com/icpac-igad/arco-ibf/blob/titiler-pgstac/titiler-tiles-COG-replit.ipynb)

**Vector Tiles with TiPG:** Visualizing river networks using MVT format for web mapping applications.
- [River Network Data](https://github.com/icpac-igad/arco-ibf/tree/tipg/rivers)
- [Frontend Visualization](https://github.com/icpac-igad/arco-ibf/blob/155dfb3115ccc329f45a3ec43b4d833c62072b75/frontend/river_network_visualization.html#L296)

## Path Forward

This simplified deployment approach serves as a stepping stone toward production-ready setups. The knowledge gained helps when transitioning to Kubernetes orchestration or serverless platforms like GCP Cloud Run, while maintaining understanding of how eoAPI's interlinked components function together.

## Resources

- [GitHub Discussion: Learning eoAPI](https://github.com/developmentseed/eoAPI/discussions/212)
- [eoAPI Repository](https://github.com/developmentseed/eoAPI)
- [Titiler Documentation](https://developmentseed.org/titiler/)
- [TiPG Repository](https://github.com/developmentseed/tipg)


