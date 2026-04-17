# CardioRisk v7 — No-Blood-Test Cardiovascular Disease Screening


> ⚠️ **Research Disclaimer**  
This system provides a statistical estimate of cardiovascular risk for research and educational use only.  
It must NOT be used for diagnosis, treatment decisions, or clinical management.

---

## 🧠 Overview

CardioRisk v7 is an end-to-end machine learning system for predicting cardiovascular disease (CVD) using **non-invasive clinical variables only**.

This project demonstrates a complete research-grade pipeline including:
- Clinical data preprocessing
- Multi-tier feature engineering
- Model comparison and selection
- Probability calibration
- Explainability (SHAP)
- Deployment via Flask GUI

---

## 🎯 Objective

The goal is to develop a **robust and interpretable model** for early cardiovascular risk estimation that:
- Works without laboratory tests
- Supports screening scenarios
- Demonstrates clinically meaningful feature engineering

---

## 📊 Dataset Description

**Source:** Kaggle Cardiovascular Dataset  
https://www.kaggle.com/datasets/sulianova/cardiovascular-disease-dataset  

### Dataset Evolution

| Stage | Description |
|------|------------|
| Original | 70,000 samples, 13 features |
| Cleaned | ~65,000 samples after filtering |
| Enhanced | 41 engineered features |

### Features

- Demographics: age, gender  
- Anthropometrics: height, weight  
- Clinical: systolic & diastolic BP  
- Biochemical (ordinal): cholesterol, glucose  
- Lifestyle: smoking, alcohol, activity  

### Target

`cardio`  
- 0 = No disease  
- 1 = Disease  

---

## 🧹 Data Processing

- Clinical filtering (physiological ranges)
- Outlier removal
- Constraint enforcement (ap_hi > ap_lo)
- Noise reduction

---

## 🧬 Feature Engineering

| Tier | Description |
|------|------------|
| T1 | Original features |
| T2 | Derived clinical metrics |
| T3 | Proxy biomarkers |
| T4 | Composite features |

Examples:
- BMI, MAP, Pulse Pressure
- Hypertension flag
- Metabolic score
- Age × BP interaction

---

## 📊 Results

| Metric | Value |
|-------|------|
| Model | HistGradientBoosting |
| CV AUC | 0.797 |
| Test AUC | 0.795 |
| Brier Score | 0.184 |

---

## 🏗️ Notebook Structure (Detailed)

### Section 1 — Setup
Install libraries and environment configuration.

### Section 2 — Imports
Load libraries and define reproducibility seed.

### Section 3 — Data Loading
Load dataset using flexible path handling.

### Section 4 — Inspection
Explore structure, missing values, distributions.

### Section 5 — Cleaning
Apply clinical constraints and remove invalid data.

### Section 6 — Feature Engineering
Create derived and composite features.

### Section 7 — EDA
Visualize distributions and relationships.

### Section 8 — Split
Stratified train/test split.

### Section 9 — Models
Compare LR, RF, HistGB.

### Section 10 — Tuning
GridSearch for best model.

### Section 11 — Evaluation
Metrics, confusion matrix, threshold tuning.

### Section 12 — Calibration
Apply isotonic regression.

### Section 13 — Visualization
ROC, PR curves.

### Section 14 — Deciles
Risk stratification validation.

### Section 15 — SHAP
Explain model predictions.

### Section 16 — Save Model
Export pipeline and metadata.

### Section 17 — GUI
Launch web interface.

---

## 🖥️ GUI Features

- Risk score visualization
- Clinical interpretation (non-directive)
- SHAP importance
- Threshold comparison
- Data validation warnings

---

## ⚙️ Installation

pip install -r requirements.txt

---

## ▶️ Usage

jupyter notebook  
python cardiorisk_gui.py  

---

## 🔬 Reproducibility

- Fixed seed (42)
- Deterministic pipeline

---

## ⚖️ Ethics

- No clinical claims
- No diagnostic usage

---

## 📄 License

Academic use only.

