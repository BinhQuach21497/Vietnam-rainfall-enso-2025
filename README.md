# Rainfall Anomalies and ENSO in Vietnam

This repository contains an independent analysis of rainfall conditions in Vietnam in 2025 and their historical relationship with the El Niño–Southern Oscillation (ENSO).

## Repository Structure

- `data/` — data sources and preprocessing notes
- `notebook/` — complete analysis notebook
- `report/` — final research report

## Data

The analysis uses:

- ERA5-Land monthly precipitation data
- NOAA ERSSTv5 sea surface temperature data

Raw datasets are not included in the repository because of file size. Source information and preprocessing notes are provided in `data/README.md`.

## Reproduce the Analysis

1. Download the required ERA5-Land and ERSSTv5 datasets.
2. Place the files in the local data directory specified in the notebook.
3. Open `notebook/Vietnam_Rainfall_ENSO_Analysis.ipynb`.
4. Update the data paths if necessary.
5. Run the notebook from top to bottom.

The notebook contains the full workflow, including precipitation preprocessing, rainfall climatology and anomalies, SPI calculation, ENSO index construction, regional and lagged correlation analysis, the 2025 ENSO-adjusted analysis, and local case studies.

## Report

The final report is available in:

`report/Rainfall_Anomalies_and_ENSO_in_Vietnam_2025.pdf`

## Author

Binh Quach  
MSc Climate & Sustainable Finance  
Vrije Universiteit Amsterdam
