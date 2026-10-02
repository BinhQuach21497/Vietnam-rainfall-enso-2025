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
