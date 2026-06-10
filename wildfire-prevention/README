# Wildfire Risk Prediction — Predicting Fire Radiative Power from Satellite Data

**Course:** OPIM 5604 Group Project 2 | University of Connecticut — Spring 2026  
**Team:** Danilo Tambone · Esha Reddy Ramireddy Gari · Mohammed Rafi · Wenting Wang

## Business Problem

Wildfires cause billions in annual damage and overwhelm emergency response systems.
This project builds a machine learning system to predict **Fire Radiative Power (FRP, in MW)**
— a satellite-derived measure of fire intensity — enabling agencies to pre-position resources
*before* fires spread rather than react after the fact.

## Dataset

**Global Wildfire Satellite Dataset (2024–2025)**
- 7 global regions · 35 countries (reduced to 11 via frequency threshold)
- Features: satellite brightness, meteorological (temp, humidity, wind),
  geographic (lat/lon, region), fire classification (type, season)
- Target: `frp_mw` — Fire Radiative Power in megawatts

## Modeling Approach

Data split: 60% train / 20% validation / 20% test — all models tuned via GridSearchCV (3-fold CV).

| Model | Test RMSE | Test R² | Overfitting |
|---|---|---|---|
| Linear Regression (baseline) | ~161 | 0.026 | None |
| KNN (K=7) | 117.21 | 0.484 | Severe |
| Gradient Boosted Tree | 101.32 | 0.615 | Minimal |
| Random Forest (basic) | 85.63 | 0.725 | High |
| Neural Network (MLP, tuned) | 84.02 | 0.735 | Minimal |
| **Random Forest (tuned) ★** | **83.94** | **0.735** | **Controlled** |

## Results

The **Tuned Random Forest** achieved a Test R² of **0.735** — explaining 73.5% of variance
in fire intensity on unseen data. This represents a **28× improvement** over the linear baseline.

Top predictors by feature importance: `longitude`, `latitude`, `humidity`, `brightness_k`, `temperature`.
Geographic coordinates alone account for ~40% of predictive power.

## Key Recommendations

1. **Geospatial pre-positioning** — deploy firefighting assets to historically high-FRP coordinate
   clusters before peak fire season
2. **Automated humidity thresholds** — trigger burn bans and increased satellite monitoring
   when humidity drops below critical levels in high-risk zones
3. **Real-time GIS risk scoring** — integrate the model into a live dashboard ingesting
   real-time meteorological data to generate continuous FRP risk scores

## Files

| File | Description |
|---|---|
| `notebook.ipynb` | Full modeling pipeline: EDA → preprocessing → 5 model families → evaluation |
| `executive_summary.pdf` | Business-facing summary of findings and recommendations |
| `presentation.pptx` | Final group presentation slides |
