# 🪐 AI Planet Hackathon – Age Group Classifier

[![Event: AI Planet Hackathon](https://img.shields.io/badge/Event-AI%20Planet%20Hackathon-blue)](https://ai-planethackathon.example.com) [![Python 3.8+](https://img.shields.io/badge/Python-3.8%2B-green)]() [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

> A clean, end-to-end ML pipeline that predicts whether someone is an **Adult** or a **Senior**, built for the AI Planet Hackathon.

---

## 📋 Table of Contents

- [✨ Features](#-features)  
- [🗂️ Project Structure](#️-project-structure)  
- [🚀 Installation](#-installation)
- [🛠️ How It Works](#️-how-it-works)

---

## ✨ Features

- 🔍 **Exploratory Data Analysis**  
- 🧹 **Preprocessing**: median imputation + standard scaling  
- 🌳 **Models**: Random Forest & XGBoost  
- 🔧 **Hyperparameter Tuning** via GridSearchCV (F1-score)  
- 🏆 **Automatic Model Selection** based on validation F1  
- 📦 **Easy deployment**: outputs a ready-to-submit `submission.csv`  

---

## 🗂️ Project Structure

```bash
├─── Train_Data.csv         # Training data (with labels)
│─── Test_Data.csv          # Test data (no labels)
|─── submission.csv         # Conatining the Result
├── notebook.ipynb    # All-in-one training & inference script
└── README.md                  # This file

```

## 🚀 Installation
```
pip install pandas
pip install numpy
pip install matplotlib
pip install seaborn
pip install scikit-learn
pip install xgboost
```

---

## 🛠️ How It Works
**Data Loading & Cleaning**
- Reads CSVs, maps Adult→0, Senior→1
- Drops any rows with missing targets

**Preprocessing Pipeline**
- Median imputation for missing values
- Standard scaling for all numeric features

**Model Training & Tuning**
- Splits data (80/20 stratified)
- Builds two pipelines:
  1. Random Forest
  2. XGBoost (with eval_metric='logloss')

**GridSearchCV over:**

- n_estimators, max_depth, and more
- Optimizes F1-score on 5-fold stratified CV

**Model Selection**
- Compares validation F1 of both models
- Picks the best performer automatically

**Inference & Submission**
- Applies the same preprocessing to test set
- Outputs predictions to submission.csv

---
