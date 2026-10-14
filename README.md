Submitted by: Saba Saleh Alghufaili — academy: @SDAIAAcademy

# CyberPulse — Network Traffic Forecasting

CyberPulse is a time series forecasting project developed for the SDAIA Time Series Capstone.

## Project Overview

The project forecasts hourly network flow counts using historical network traffic data.

The forecasting pipeline includes:
- Exploratory Data Analysis (EDA)
- STL Decomposition and Autocorrelation Analysis
- Naive and Seasonal Naive Baselines
- AutoGluon Time Series Models
- Rolling-Origin Backtesting
- Forecast Evaluation using MASE, Scaled CRPS, and 80% Coverage

## Dataset

The project uses sampled network flow data aggregated into hourly observations.

- Frequency: Hourly
- Forecast Horizon: 24 hours
- Seasonal Period: 24 hours

## Results

Chronos2 achieved better forecasting accuracy than the Seasonal Naive baseline across five rolling backtesting windows.

However, its 80% prediction intervals showed insufficient coverage.

## Project Files

- `CyberPulse_Forecasting.ipynb` — Forecasting pipeline and analysis
- `network_flows.csv` — Dataset
- `report.md` — Final forecasting report
- `rubric.md` — SDAIA grading criteria

## Submission

This repository is a fork of the SDAIA Academy Time Series Capstone starter repository.
