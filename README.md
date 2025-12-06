# 🦠 Influenza Forecasting Analysis  
### *Produced by: Niyat Kahsay • Nancy Walker • Celina Velazquez*

This repository contains a full time-series forecasting analysis of U.S. influenza-like illness (ILI) rates.  
Our goal was to compare the short-term and long-term forecasting performance of ARIMA and TSLM models, evaluate model stability, and assess how the COVID-19 pandemic impacted influenza forecasting accuracy.

The analysis was completed as part of a graduate-level Data Science project.

---

## 📘 Project Summary

We analyzed weekly CDC influenza-like illness (ILI) data and built forecasting models under multiple horizons:

- **Short-term:** 12 weeks  
- **Medium-term:** 26 weeks  
- **Long-term:** 52 weeks  

To capture seasonality and structural breaks, we used:

- **ARIMA (Auto-ARIMA)**
- **TSLM with trend + Fourier terms + Box-Cox transformation**
- **Pandemic dummy variable** to account for COVID-19 disruption

To ensure robustness, we performed both **automated fable cross-validation** and a **manual sliding-window cross-validation**.

---

## ⭐ Key Findings

- **ARIMA performs best for very short-term forecasts (~12 weeks)**  
  Initial validation showed ARIMA had ~3% lower RMSE, making it ideal for near-term operational planning.

- **TSLM outperforms ARIMA for medium and long-term horizons (26–52 weeks)**  
  Both simplified and manual CV showed lower RMSE for TSLM across nearly all folds.

- **Both models are stable across years**  
  Residual diagnostics (Ljung–Box p > 0.05) confirmed minimal autocorrelation.

- **The COVID-19 dummy variable dramatically improves predictive consistency**  
  Models without it performed significantly worse, confirming a structural break during 2020–2022.

- **Practical Recommendation:**  
  - Use **ARIMA** for short-term staffing and operational decisions.  
  - Use **TSLM (with the pandemic dummy)** for long-term planning such as budgeting and vaccine strategy.

---

## 📂 Repository Structure

- `data/` — Processed influenza time series data  
- `models/` — ARIMA and TSLM model objects  
- `notebooks/` — R Markdown analysis and visualizations  
- `plots/` — Forecast charts and cross-validation plots  
- `README.md` — Project summary (this file)

---

## 📚 Data Source

Centers for Disease Control and Prevention. (n.d.). *FluView – Weekly U.S. influenza surveillance report*.  
Retrieved October 31, 2025, from: [https://gis.cdc.gov/grasp/fluview/fluportaldashboard.html](https://gis.cdc.gov/grasp/fluview/fluportaldashboard.html)
