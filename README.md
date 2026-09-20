# 📈 COVID-19 Regional Forecasting — Italy

![Python](https://img.shields.io/badge/Python-3.8+-blue?style=flat-square&logo=python)
![Forecasting](https://img.shields.io/badge/Time%20Series-Forecasting-orange?style=flat-square)
![SARIMA](https://img.shields.io/badge/Model-SARIMA-purple?style=flat-square)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=flat-square)

> **Can historical COVID-19 trends be used to generate more reliable short-term forecasts for regional planning?**

This project evaluates multiple time-series forecasting approaches using regional COVID-19 data from Italy, with a focus on Lombardia.

---

## 📌 Project Overview

The goal of this project was to build and compare forecasting models for regional COVID-19 case trends while following a time-aware validation process appropriate for sequential data.

Three approaches were evaluated:

- Naive Baseline
- SARIMA
- Random Forest

The project also identified and corrected an evaluation issue during model validation, helping ensure that the final model comparison reflected true out-of-sample forecasting performance.

---
## 📊 Forecast Preview

![Model Forecast Comparison](images/model_forecast_comparison.png)

**Result:** SARIMA achieved the strongest validated forecasting performance,
with MAE **180.42** compared with **205.84** for the Naive baseline and
**259.18** for Random Forest.
---

## 📊 Model Performance

| Model | MAE | RMSE |
|---|---:|---:|
| Naive Baseline | 205.84 | 270.71 |
| Random Forest | 259.18 | 314.70 |
| SARIMA | **180.42** | **212.13** |

**Best validated model:** SARIMA

SARIMA reduced Mean Absolute Error from **206 to 180** compared with the Naive baseline, demonstrating improved short-term forecasting performance.

---

## 🔍 Key Analytical Takeaway

The project showed that model performance depends not only on the forecasting algorithm but also on using a correct **time-based validation strategy**.

An earlier evaluation approach was reviewed and corrected to avoid overstating model performance. After re-evaluation, SARIMA provided the strongest validated result.

---
## 📈 Supporting Analysis

### Regional Trends

![Top Regions 7-Day Moving Average](images/top_regions_ma7.png)

The 7-day moving average shows a common late-March peak followed by a gradual
decline across the most affected regions.

### Lombardia Outbreak

![COVID-19 Outbreak in Lombardia](images/lombardia_outbreak.png)

Lombardia experienced the most severe outbreak in the dataset and was selected
as the primary region for forecasting analysis.

### Random Forest Feature Importance

![Random Forest Feature Importance](images/rf_feature_importance.png)

The feature-importance analysis helps explain the Random Forest benchmark,
with lagged case counts and recent moving-average information contributing
most strongly to its predictions.
---
## ⚙️ Workflow

```text
COVID-19 Regional Data
        ↓
Data Cleaning & Preparation
        ↓
Exploratory Time-Series Analysis
        ↓
Train / Validation Split
        ↓
Naive Baseline
        ↓
SARIMA
        ↓
Random Forest
        ↓
Model Comparison & Validation
