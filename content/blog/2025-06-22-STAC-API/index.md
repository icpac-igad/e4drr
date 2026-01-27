---
title: STAC API for Impact-Based Forecasting Data Catalogs
summary: Implementing STAC specification for organizing drought and flood forecasting data in the E4DRR project.
date: 2025-06-22

authors:
  # -

tags:
  - STAC
  - Data Catalog
  - Impact-Based Forecasting
---

## The Shift Toward STAC

The SpatioTemporal Asset Catalog (STAC) specification has emerged as the standard for organizing and discovering geospatial data. Major data providers have embraced this transformation:

- **NASA** now publishes Earth science data through STAC-compliant catalogs via their [CMR-STAC API](https://cmr.earthdata.nasa.gov/stac), enabling standardized access to satellite imagery and climate datasets.
- **ECMWF** provides climate reanalysis and forecast data through STAC interfaces, facilitating integration with cloud-native analysis workflows.

This industry-wide adoption signals a fundamental shift from proprietary data portals toward interoperable, machine-readable catalogs.

## E4DRR STAC Implementation

The [E4DRR STAC API](https://github.com/icpac-igad/stac-api) implements the STAC v1.1.0 specification for Impact-Based Forecasting (IBF) data. The catalog organizes drought and flood forecasting assets into a hierarchical structure designed for complex risk analytics.

### Catalog Structure

Both **Drought** and **Flood** catalogs contain six core collections aligned with the IBF chain:

| Collection | Purpose |
|------------|---------|
| Observations | Historical climate data |
| Ensemble Predictions | Forecast model outputs |
| Hazard Model | Drought/flood hazard assessments |
| Impact Model | Sectoral impact estimates |
| Forecast Verification | Model performance metrics |
| Risk Knowledge | Vulnerability and exposure data |

### Integration Features

The implementation supports Cloud Optimized GeoTIFFs (COGs) stored in Google Cloud Storage, enabling efficient data streaming. The catalog integrates with [STAC Browser](https://radiantearth.github.io/stac-browser/) for visual exploration and can serve as a foundation for programmatic data discovery using PySTAC.

## Enabling Complex Risk Analytics

By adopting STAC, E4DRR data becomes interoperable with the broader ecosystem of climate and Earth observation datasets. Analysts can combine ICPAC forecasts with NASA satellite observations or ECMWF reanalysis through unified query interfaces, supporting comprehensive risk assessments across the impact chain.

## Resources

- [E4DRR STAC API Repository](https://github.com/icpac-igad/stac-api)
- [STAC Specification](https://stacspec.org/)
- [NASA CMR-STAC](https://cmr.earthdata.nasa.gov/stac)


