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

## 📊 Model Performance

| Model | Result |
|---|---|
| Naive Baseline | MAE: 206 |
| SARIMA | **MAE: 180** |
| Random Forest | Used as an additional forecasting benchmark |

**Best validated model:** SARIMA

SARIMA reduced Mean Absolute Error from **206 to 180** compared with the Naive baseline, demonstrating improved short-term forecasting performance.

---

## 🔍 Key Analytical Takeaway

The project showed that model performance depends not only on the forecasting algorithm but also on using a correct **time-based validation strategy**.

An earlier evaluation approach was reviewed and corrected to avoid overstating model performance. After re-evaluation, SARIMA provided the strongest validated result.

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
