# Data

This project uses two public climate datasets:

- **ERA5-Land** monthly precipitation data for Vietnam
- **NOAA ERSSTv5** monthly sea surface temperature data for the Niño 3.4 region

The raw datasets are not included in this repository because of file size.

## Precipitation

ERA5-Land total precipitation is converted from metres to millimetres per month using the number of days in each month.

The analysis covers January 1950 to August 2026 and is conducted at both grid-cell and regional levels.

## ENSO

ENSO is represented using a standardized monthly Niño 3.4 sea surface temperature anomaly derived from NOAA ERSSTv5.

The Niño 3.4 region is defined as 5°S–5°N and 170°W–120°W.

## Reproducibility

Users wishing to reproduce the analysis should download the source datasets and update the local file paths in the analysis notebook.
# Data

This project uses two public climate datasets:

1. **ERA5-Land monthly precipitation data** from the Copernicus Climate Data Store
2. **NOAA ERSSTv5 monthly sea surface temperature data** used to construct the Niño 3.4 ENSO index

The raw files are not included in this repository because of file size.

## 1. ERA5-Land Precipitation

**Source:** Copernicus Climate Data Store (CDS)  
**Dataset:** ERA5-Land monthly averaged data  
**Variable:** Total precipitation (`tp`)  
**Period:** January 1950 to August 2026  
**Spatial coverage used in this project:** Vietnam and surrounding region  
**Source link:** https://cds.climate.copernicus.eu/

### Processing

ERA5-Land total precipitation is provided in metres as a monthly mean of daily accumulation.

It is converted to monthly precipitation in millimetres using:

```text
monthly precipitation (mm)
= tp × 1000 × number of days in month
```

The precipitation data are analysed at both the grid-cell level and across six broad regions of Vietnam:

- Northern Mountains
- Red River Delta
- North Central Vietnam
- South Central Vietnam
- Central Highlands
- Southern Vietnam

Regional precipitation is calculated using area-weighted averages.

Historical monthly climatologies are constructed separately for each calendar month. Rainfall anomalies are then calculated relative to the corresponding historical monthly mean.

For the 2025 analysis, the historical reference period is 1950–2024. For observations in 2026, the historical reference period is extended through 2025.

## 2. NOAA ERSSTv5

**Source:** NOAA Climate Prediction Center  
**Dataset:** Extended Reconstructed Sea Surface Temperature Version 5 (ERSSTv5)  
**Variable:** Monthly sea surface temperature  
**Source link:** https://www.cpc.ncep.noaa.gov/products/analysis_monitoring/enso/oni/v5/

### ENSO Index Construction

The ENSO index used in this project is constructed from sea surface temperatures in the Niño 3.4 region:

- **Latitude:** 5°S–5°N
- **Longitude:** 170°W–120°W

The processing steps are:

1. Calculate the area-weighted mean sea surface temperature over the Niño 3.4 region.
2. Remove the monthly climatology to obtain SST anomalies.
3. Standardize the anomaly series into z-scores.
4. Use the standardized Niño 3.4 anomaly as a continuous ENSO index in the statistical analysis.

Positive values indicate relatively warmer Niño 3.4 conditions, negative values indicate relatively cooler conditions, and values close to zero indicate conditions near the historical mean.

The standardized ENSO index is used for the statistical analysis and is not itself used to classify operational ENSO phases.

## Raw Data

The raw datasets are not stored in this repository because of file size:

- ERA5-Land precipitation file: approximately **215 MB**
- ERSSTv5 SST file: approximately **155 MB**

## Reproducibility

To reproduce the analysis:

1. Download the ERA5-Land precipitation data from the Copernicus Climate Data Store.
2. Download the ERSSTv5 sea surface temperature data from NOAA.
3. Update the local file paths in the analysis notebook.
4. Run the notebook from top to bottom.

The complete analysis is contained in:

`notebook/Vietnam_Rainfall_ENSO_Analysis.ipynb`
