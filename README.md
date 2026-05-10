# Groundwater Trend Analysis: ET/Precipitation Ratio and Aridity Index

## Purpose

This repository contains the analysis pipeline for examining the relationship between groundwater level trends and the ratio of evapotranspiration (ET) to precipitation across 50 irrigated agricultural wellsites in the United States. Sites span six regions and cover the period 2000–2020 (with some wells having incomplete records for up to 7 sites).

The central output is a scatter plot with the ET/Precipitation ratio on the x-axis and the 20-year groundwater trend (m/yr) on the y-axis, where each point represents a single well. This analysis is repeated for four spatial bounding box scales: 1 km, 2 km, 4 km, and 10 km. Aridity Index is calculated per wellsite, and Spearman's rank correlation is applied to the final figure.

---

## Contents

### Repository Tree



> **Note:** Scripts are intended to be run in the order listed under [Directions for Use](#directions-for-use). Each script (or set of scripts) writes results to an `outputs/` folder created on first run. Downstream scripts reference this folder.

---

### Folder Descriptions

- **`aridity_index/`**
  - `aridity_index.ipynb` —
  - `budyko_curve.png`, `budyko_curve_sqrtroot.png`, `budyko_curve_xlog.png`, `budyko_scale_comparison.png` —

- **`cultivation/`**
  - *(scripts to be added)*

- **`ET/`**
  - `usgs_water_level_cleaning.ipynb` —
  - `open-et-timeseries.ipynb` —
  - `modis-et-timeseries.ipynb` —
  - `water_level_et_plots.ipynb` —

- **`precipitation/`**
  - `chirps_API.ipynb` —
  - `chirps_precipt_USGS_analysis_openET.ipynb` —
  - `precipt_variation.ipynb` —

- **`scratch/`** — Exploratory and developmental notebooks not part of the main pipeline.

- **`spearman_stats.ipynb`** —

- **`yml/`**
  - `arid_gw.yml` — Conda environment file for reproducing the project environment.

---

## Data Access

Begin by creating a folder named `data/` in the root of the repository. All datasets should be placed within this folder as described below.

### USGS Well Data
Groundwater monitoring site metadata and associated groundwater level records are hosted on HydroShare. Download the CSV from the following link and place it in a folder named `gw_data/` within `data/`:

[Groundwater Site Data – HydroShare](https://www.hydroshare.org/resource/04b9eebf0d4b4490a15e1f27be46f7e4/)

### USDA Cropland Cultivation Data
Cultivation data are sourced from the USDA Cropland Data Layer (CDL), available for 2008–2025. Download the 'National CDL' for zip file for the years 2000-2020. All zip files should then be placed in a folder named `cdl_data/` within `data/`. Once all files are in `cdl_data/`, they can be unzipped.

[Cropland Cultivation Data - USDA](https://www.nass.usda.gov/Research_and_Science/Cropland/Release/index.php)

### OpenET Evapotranspiration Data

### CHIRPS Precipitation Data

### Aridity Index Data
Aridity data were obtained from the [Global Aridity Index and Potential Evapotranspiration (ET₀) Database: Version 3.1](https://doi.org/10.6084/m9.figshare.7504448), available through Figshare. Download and unzip the `Global-AI_ET0_annual_v3_1` folder. This analysis uses the annual raster file `ai_v31_yr.tif`.

---

## Statistical Methods and Sensitivity Testing

### 1. Spearman's Rank Correlation

Spearman's rank correlation is a non-parametric measure of the monotonic relationship between two variables. Here, it is used to assess whether wells with a higher ET/Precipitation ratio tend to show a stronger declining (or recovering) groundwater trend over the 20-year period. Because the data are ranked rather than used as raw values, Spearman's is appropriate when the relationship between variables may not be linear or when the data cannot be assumed to follow a normal distribution.

### 2. Sensitivity Testing

The analysis is repeated across four spatial scales — 1 km, 2 km, 4 km, and 10 km bounding boxes — to evaluate how sensitive the ET estimates and resulting correlations are to the spatial extent used when sampling ET around each well.

---

## Directions for Use

> The following directions pertain to the **1 km bounding box** analysis. All scripts should be run in the order listed. Each step writes outputs to an `outputs/` folder that is created during step 1 and referenced by all subsequent steps.

### 1. Cultivation

### 2. Evapotranspiration

### 3. Precipitation

### 4. Creating the Final Figure

### 5. Aridity Index

### 6. Spearman's Rank

---

## Authors

---

## Acknowledgements

---

## References
