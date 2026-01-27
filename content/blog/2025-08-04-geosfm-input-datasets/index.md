---
title: GeoSFM Model Input Preparation with Cloud-Native Tools
summary: Preparing hydrological model inputs using Icechunk, Zarr-Parquet, and Flox-Dask for efficient zonal aggregation.
date: 2025-08-04

authors:
  # -

tags:
  - GeoSFM
  - Icechunk
  - Flox
  - Hydrological Modeling
---

## GeoSFM Hydrological Model

GeoSFM (Geospatial Stream Flow Model) is a distributed hydrological model used for flood forecasting and water resource assessment across East Africa. The model requires gridded precipitation and evapotranspiration inputs aggregated to hydrological response units (zones), making efficient data processing essential for operational workflows.

## Cloud-Native Data Pipeline

The input preparation workflow leverages modern cloud-native tools to handle large-scale geospatial data processing:

### Icechunk and Zarr Storage

[Icechunk](https://icechunk.io/) provides versioned, cloud-optimized storage for Zarr datasets. The workflow stores raw and regridded data in Icechunk Zarr format, enabling:
- Efficient chunk-based access for large arrays
- Version control for reproducible workflows
- Seamless integration with Xarray and Dask

### Flox-Dask for Zonal Aggregation

[Flox](https://flox.readthedocs.io/) accelerates grouped operations on labeled arrays, replacing slow Xarray groupby operations with optimized algorithms. Combined with Dask, it enables parallel zonal statistics computation across thousands of hydrological zones efficiently.

### Parquet for Tabular Output

Aggregated zone-wise data is exported to Parquet format for efficient storage and fast analytical queries, facilitating integration with downstream analysis tools.

## Workflow Architecture

The three-stage pipeline processes data from multiple sources:

1. **Download & Regrid** (`01-get-regrid.py`): Fetches CHIRPS-GEFS forecasts, IMERG observations, and PET data; regrids to unified 0.02° resolution
2. **Flox Groupby** (`02-flox-groupby.py`): Converts shapefiles to raster zones; performs zone-based aggregation using Flox
3. **Zone Text Generation** (`03-zone-txt.py`): Produces `rain.txt` and `evap.txt` files for each GeoSFM zone

## Resources

- [Workflow Documentation](https://github.com/icpac-igad/DevOps-hazard-modeling/blob/main/geosfm/docs/COMPLETE_GEOSFM_INPUT_WORKFLOW_DOCUMENTATION.md)
- [Video Demonstration](https://www.youtube.com/watch?v=naZ9W9AcaPM)


