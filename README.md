# 📈 COVID-19 Regional Forecasting — Italy

![Python](https://img.shields.io/badge/Python-3.8+-blue?style=flat-square&logo=python)
![Forecasting](https://img.shields.io/badge/Time%20Series-Forecasting-orange?style=flat-square)
![SARIMA](https://img.shields.io/badge/Model-SARIMA-purple?style=flat-square)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=flat-square)

> **Can historical COVID-19 trends be used to generate more reliable short-term forecasts for regional planning?**

This project evaluates multiple time-series forecasting approaches using regional COVID-19 data from Italy, with a focus on **Lombardia**, one of the most heavily affected regions in the dataset.

---

## 📌 Project Overview

The goal of this project was to build and compare forecasting models for regional COVID-19 case trends while following a **time-aware validation process** appropriate for sequential data.

Three forecasting approaches were evaluated:

- Naive Baseline
- Random Forest
- SARIMA

The project also identified and corrected an evaluation issue during model validation, helping ensure that the final comparison reflected true out-of-sample forecasting performance.

---

## 📊 Forecast Preview

![Model Forecast Comparison](images/Model%20Forecast%20Comparison.png)

**Result:** SARIMA achieved the strongest validated forecasting performance, with MAE **180.42** compared with **205.84** for the Naive baseline and **259.18** for Random Forest.

---

## 📊 Model Performance

| Model | MAE | RMSE |
|---|---:|---:|
| Naive Baseline | 205.84 | 270.71 |
| Random Forest | 259.18 | 314.70 |
| SARIMA | **180.42** | **212.13** |

**Best validated model:** SARIMA

SARIMA reduced Mean Absolute Error from approximately **206 to 180** compared with the Naive baseline, providing the strongest performance among the evaluated models.

---

## 🔍 Key Analytical Takeaway

The project showed that forecasting performance depends not only on the model itself but also on using an appropriate **time-based validation strategy**.

An earlier evaluation approach was reviewed and corrected to avoid overstating model performance. After re-evaluation, SARIMA produced the strongest validated result.

This reinforced an important modeling lesson:

> A more complex model does not necessarily outperform a simpler statistical forecasting approach when the validation process correctly reflects real-world forecasting conditions.

---

## 📈 Supporting Analysis

### Regional Trends

![Top Regions 7-Day Moving Average](images/7-Day%20Moving%20Average%20of%20Daily%20Cases%20%E2%80%94%20Top%20Regions.png)

The 7-day moving average shows a common late-March peak followed by a gradual decline across several of the most affected Italian regions.

### Lombardia Outbreak

![COVID-19 Outbreak in Lombardia](images/COVID-19%20Outbreak%20in%20Lombardia.png)

Lombardia experienced the most severe outbreak in the dataset and was selected as the primary region for forecasting analysis.

### Random Forest Feature Importance

![Random Forest Feature Importance](images/Feature%20Importance.png)

The feature-importance analysis helps explain the Random Forest benchmark by showing how lagged case counts, recent moving-average information, and calendar-related variables contributed to its predictions.

---

## ⚙️ Workflow

```text
COVID-19 Regional Data
        ↓
Data Cleaning & Preparation
        ↓
Wide-to-Long Reshaping
        ↓
Daily Case Calculation
        ↓
Feature Engineering
        ↓
Exploratory Time-Series Analysis
        ↓
Time-Based Train / Test Split
        ↓
Naive Baseline
        ↓
Random Forest
        ↓
SARIMA
        ↓
Model Comparison & Validation
```
