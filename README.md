# Gold Price Forecasting (2013–2023)

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue)]()
[![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange)]()
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Wrangling-informational)]()
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebooks-yellow)]()
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)]()

> **TL;DR**: A lightweight, reproducible pipeline that benchmarks classic ML models for daily gold-price forecasting. On this dataset, **Linear Regression** outperformed **Random Forest** (lower RMSE).  
> _Re-run the notebook to reproduce results and update the metrics table below._

---

## ✨ What’s inside
- Clean time-series pipeline (train/validate/test split, scaling, lag features)
- Benchmarks: **Linear Regression**, **Random Forest**
- Reproducible **Jupyter** notebook and saved artifacts
- Clear metrics & plots (error curve, predictions vs. actual)

---

## 📊 Results 
| Model              | RMSE  | MSE   | R²     |
|--------------------|------:|------:|:------:|
| Linear Regression  | 15.03 | 3.87 | 0.9998 |
| Random Forest      | 26.15 | 683.8 | 0.9996 |

This repository provides a concise, reproducible pipeline for forecasting daily gold prices. The focus is on robust time-series preparation (time-aware train/validation/test splits, scaling, and lag/rolling features) and apples-to-apples model benchmarking with consistent metrics. The current window covers 2013–2023 daily prices; the pipeline can optionally ingest exogenous signals (e.g., FX rates, interest rates, indices) without changing the interface, so you can iterate quickly as data availability evolves.

Evaluation emphasizes RMSE, MSE, and R². On this dataset, Linear Regression delivered **≈42.5% lower RMSE** than Random Forest (15.03 vs 26.15), with MSE values consistent with RMSE² (≈226 vs ≈683.8) and very high R² for both models. Practically, that means a well-specified linear baseline captures most of the signal here, while tree ensembles add complexity without improving error on this configuration. The goal isn’t to crown a universal winner, but to keep a transparent benchmark you can extend: add external variables, adjust forecast horizons, swap in alternative learners (e.g., XGBoost/LightGBM), and validate changes with the same time-aware evaluation.

Reproducibility is straightforward: Python 3.10+, scikit-learn, Pandas, and Jupyter. Install requirements, drop the CSV into your `data` folder, and re-run the notebook to regenerate figures and metrics; commit updated artifacts so results are traceable. Code is MIT-licensed—use and adapt freely.

![image](https://github.com/user-attachments/assets/6b32d56f-dd9c-47f5-a875-67918522177d)
