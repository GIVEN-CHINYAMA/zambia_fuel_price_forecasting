# ⛽ Zambia Fuel Price Forecasting
## A Comparative Time Series Analysis of Petrol and Diesel Prices
### Using ARIMA · SARIMA · Holt-Winters · Prophet

---

> **Author:** Given Chinyama
> **Institution:** Kwame Nkrumah University
> **Date:** May 2026
> **GitHub:** [github.com/GIVEN-CHINYAMA](https://github.com/GIVEN-CHINYAMA)

---

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/GIVEN-CHINYAMA/zambia_fuel_price_forecasting/blob/main/zambia_fuel_price_forecasting.ipynb)
![Python](https://img.shields.io/badge/Python-3.10+-blue?style=flat-square&logo=python)
![Prophet](https://img.shields.io/badge/Prophet-Meta-blue?style=flat-square)
![Statsmodels](https://img.shields.io/badge/Statsmodels-ARIMA%2FSARIMA-green?style=flat-square)
![Platform](https://img.shields.io/badge/Platform-Google%20Colab-F9AB00?style=flat-square&logo=google-colab)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=flat-square)
![Data](https://img.shields.io/badge/Data-ERB%20Zambia-orange?style=flat-square)

---

## 👆 Click "Open in Colab" Above to View the Full Notebook

> GitHub cannot render large notebooks with embedded visualisations. Click the **Open in Colab** button above to view the complete project with all code, outputs, and professional charts.

---

## 📊 Results Summary

### Petrol Forecast Performance

| Model | RMSE (K/litre) | MAE (K/litre) | MAPE | R² |
|-------|---------------|--------------|------|-----|
| ARIMA(1,1,0) | 12.91 | 10.76 | 28.26% | -2.43 |
| SARIMA(1,1,0)(0,0,0,12) | 12.95 | 10.80 | 28.37% | -2.45 |
| Holt-Winters | 20.56 | 17.25 | 45.44% | -7.71 |
| **Prophet** | **3.77** | **3.14** | **9.54%** | **0.71** |

### Diesel Forecast Performance

| Model | RMSE (K/litre) | MAE (K/litre) | MAPE | R² |
|-------|---------------|--------------|------|-----|
| ARIMA(1,1,0) | 12.65 | 10.58 | 28.68% | -2.50 |
| SARIMA(1,1,0)(0,0,0,12) | 12.69 | 10.62 | 28.80% | -2.52 |
| Holt-Winters | 20.09 | 16.86 | 45.84% | -7.82 |
| **Prophet** | **3.64** | **3.02** | **9.52%** | **0.71** |

> 🏆 **Prophet achieved the best performance on all metrics for both Petrol and Diesel — 81%+ better RMSE than the worst model.**

---

## 📅 2025 Fuel Price Forecast (Prophet — Best Model, ZMW per litre)

| Month | Petrol (K) | Diesel (K) |
|-------|-----------|-----------|
| January 2025 | 47.21 | 45.77 |
| February 2025 | 48.17 | 46.69 |
| March 2025 | 49.01 | 47.51 |
| April 2025 | 50.05 | 48.51 |
| May 2025 | 51.14 | 49.58 |
| June 2025 | 52.28 | 50.68 |
| July 2025 | 53.32 | 51.67 |
| August 2025 | 54.43 | 52.76 |
| September 2025 | 55.55 | 53.85 |
| October 2025 | 56.52 | 54.80 |
| November 2025 | 57.58 | 55.82 |
| December 2025 | 58.42 | 56.62 |

---

## 📁 Project Overview

Fuel prices in Zambia are regulated by the **Energy Regulation Board (ERB)** and are among the most consequential economic indicators affecting citizens and businesses. This project builds, trains, evaluates, and compares four time series forecasting models on real ERB-published Zambian fuel price data — forecasting both Petrol and Diesel prices 12 months into the future.

### Why This Project Is Unique

Unlike most forecasting projects that use freely available API data, this project works with **real ERB-published Zambian fuel price data** — a dataset requiring manual curation from official government sources. This makes it a genuinely original contribution to the Zambian data science landscape, highly relevant to local employers, NGOs, and policy institutions.

---

## 🔍 Problem Statement

> **How will petrol and diesel prices in Zambia evolve over the next 12 months, and which forecasting model best captures the complex dynamics of Zambia's regulated fuel market?**

Zambia's fuel prices are driven by:

| Factor | Impact |
|--------|--------|
| International crude oil price (USD/barrel) | Direct cost driver |
| USD/ZMW exchange rate | Import cost multiplier |
| ZRA taxes and levies | Fixed cost component |
| ERB marketing margin and distribution costs | Retail markup |
| Global supply chain disruptions | Volatility trigger |

---

## 🗂️ Project Stages

| Stage | Description |
|-------|-------------|
| Stage 1 | Environment setup — libraries and imports |
| Stage 2 | Data collection — ERB historical fuel prices (2015–2024) |
| Stage 3 | Preprocessing and EDA — cleaning, visualisation |
| Stage 4 | Stationarity testing — ADF test, decomposition, ACF/PACF |
| Stage 5 | ARIMA model — auto_arima order selection and evaluation |
| Stage 6 | SARIMA model — seasonal ARIMA with m=12 |
| Stage 7 | Holt-Winters model — exponential smoothing |
| Stage 8 | Prophet model — Meta's production forecasting framework |
| Stage 9 | Model comparison — MAE, RMSE, MAPE, R² |
| Stage 10 | 12-month future forecast — January to December 2025 |
| Stage 11 | Conclusion — findings and recommendations |

---

## 🛠️ Technologies Used

| Tool | Purpose |
|------|---------|
| Python 3.10+ | Core language |
| Prophet (Meta) | Best-performing forecasting model |
| Statsmodels | ARIMA and SARIMA models |
| pmdarima | auto_arima order selection |
| scikit-learn | Metrics (RMSE, MAE, R²) |
| pandas / numpy | Data manipulation |
| matplotlib / seaborn | Visualisation |
| Google Colab | Cloud execution platform |

---

## 💡 Key Findings

- **Prophet outperformed all 3 models on every metric** for both Petrol and Diesel
- **ARIMA and SARIMA performed identically** — monthly ERB data has no detectable seasonal pattern that SARIMA could exploit
- **Holt-Winters was the worst model**, struggling with the non-linear trend and structural breaks in Zambian fuel prices
- **Petrol and Diesel prices move almost in lockstep**, differing by approximately K1–2/litre consistently
- Prophet's R² of **0.71** confirms strong explanatory power, while ARIMA/SARIMA negative R² values indicate poor fit
- The 2025 forecast projects petrol prices rising from **K47/litre in January to K58/litre by December 2025**

---

## 🚀 How to Run

**Option 1 — Google Colab (Recommended):**
Click the **Open in Colab** badge at the top of this page. No setup required.

**Option 2 — Run locally:**
```bash
git clone https://github.com/GIVEN-CHINYAMA/zambia_fuel_price_forecasting.git
cd zambia_fuel_price_forecasting
pip install pandas numpy matplotlib seaborn statsmodels pmdarima prophet scikit-learn
jupyter notebook zambia_fuel_price_forecasting.ipynb
```

---

## 📦 Dataset

- **Source:** Energy Regulation Board (ERB) of Zambia — official monthly fuel price announcements
- **Coverage:** 2015 to 2024
- **Variables:** Petrol price (ZMW/litre), Diesel price (ZMW/litre)
- **Frequency:** Monthly
- **Note:** Manually curated dataset from official ERB sources — not available via any public API

---

## 📌 Repository Structure
