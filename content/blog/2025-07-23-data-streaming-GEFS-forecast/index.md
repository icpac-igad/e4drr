---
title: Data Streaming NOAA GEFS for cGAN Inference
summary: Streaming GEFS forecast variables from AWS S3 Open Data using grib-index-kerchunk for cGAN precipitation downscaling.
date: 2025-07-23

authors:
  # -

tags:
  - GEFS
  - Kerchunk
  - cGAN
  - Data Streaming
---

## GEFS Data Streaming for cGAN Inference

The NOAA Global Ensemble Forecast System (GEFS) provides ensemble weather predictions hosted on AWS S3 Open Data. Accessing multiple forecast variables efficiently is critical for machine learning applications like cGAN (conditional Generative Adversarial Network) precipitation downscaling.

## The Challenge: 11 Variables for cGAN

cGAN precipitation downscaling requires **11 different atmospheric variables** from GEFS as input features (temperature, humidity, wind components, geopotential heights, etc.). Traditional approaches would require downloading entire GRIB2 files for each variable and ensemble member—potentially hundreds of gigabytes per forecast cycle. This creates significant bandwidth, storage, and time overhead for operational workflows.

## Grib-Index-Kerchunk Method

Using grib-index and Kerchunk, GEFS GRIB2 files can be virtualized into Zarr format without downloading entire files. This enables:

- **Selective variable extraction** - Stream only required variables for cGAN inference
- **Efficient cloud access** - Byte-range requests to AWS S3
- **Zarr-to-NetCDF conversion** - Transform streamed data into NetCDF for model input

## Workflow Components

| Script | Purpose |
|--------|---------|
| `run_gefs_inference_raw.py` | Self-contained cGAN inference pipeline |
| `zarr_to_raw_netcdf.py` | Convert GIK Zarr to NetCDF for cGAN input |
| `tfrecords_generator.py` | Generate TFRecords for model training |

The workflow streams GEFS variables, converts to normalized NetCDF format, and feeds into the cGAN model to produce downscaled precipitation ensemble forecasts.

## Resources

- [Video Demo: Data Streaming NOAA GEFS for cGAN Inference](https://www.youtube.com/watch?v=UkBNaXhVHgc)
- [Example Notebooks](https://github.com/icpac-igad/cGAN_tutorial/tree/main/example_notebooks)
- [cGAN Tutorial Repository](https://github.com/icpac-igad/cGAN_tutorial)


