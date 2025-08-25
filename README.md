# Projet Camille Schittly — R / RMarkdown Data Analysis

## Overview
This repository contains two data analyses implemented in **R** with **R Markdown** (readthedown theme):

1) **Time Series (Germany electricity prices)**  
   - Hourly data (`Germany.csv`), daily aggregation, moving-average smoothing  
   - Decomposition (trend/seasonality), **ACF/PACF**, **ADF** stationarity test  
   - Short-term forecasts with **ETS** and **(S)ARIMA** (full series vs end-segment)  
   - Residual diagnostics (ACF, QQ-plot, dispersion)

2) **Cross-country regression (Energy consumption & air-pollution mortality)**  
   - Datasets:  
     `death-rate-from-air-pollution-per-100000.csv` (mortality),  
     `energy-consumption-by-source-and-country.csv` (energy by source),  
     `population-and-demography.csv` (population)  
   - Per-capita scaling (join with population), merging, EDA (histograms, world map 2010, scatter)  
   - Multiple Linear Regression (9 energy sources per-capita)  
   - Model refinement: log-transform of target, **backward** selection on 2007 & 2017  
   - Diagnostics: global F-test, coefficient tests, **QQ-plot**, residual **ACF**, **ncvTest** (car), **VIF**

---

## Files
- `Projet CS.Rmd` — Main R Markdown report (rmdformats::readthedown)
- `Germany.csv` — Hourly electricity prices (Germany)
- `death-rate-from-air-pollution-per-100000.csv` — Air-pollution deaths
- `energy-consumption-by-source-and-country.csv` — Energy by source
- `population-and-demography.csv` — Population

> Place all CSV files **in the same folder** as the Rmd for knitting.

---

## Requirements
R (≥ 4.1 recommended) and the following packages:

```r
install.packages(c(
  "rmdformats","tidyverse","readr","dplyr","ggplot2","ggrepel",
  "forecast","tseries","broom","maps","car","see","Ecdat"
))
