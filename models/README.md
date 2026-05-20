# Irrigation Need Prediction

## Overview

This project aims to predict irrigation requirements (Low, Medium, High) using environmental, soil, and agricultural data.

The goal is to identify the key drivers of irrigation demand and evaluate multiple machine learning models.

---

## Dataset

- Source: Kaggle  
- Size: 630,000 rows, 21 features  
- No missing values or duplicates  

### Feature Groups

- Soil: Soil_Moisture, Soil_pH, Organic_Carbon  
- Weather: Temperature_C, Rainfall_mm, Humidity  
- Agriculture: Crop_Type, Crop_Growth_Stage  
- Irrigation: Previous_Irrigation_mm, Water_Source  

---

## Target Variable

`Irrigation_Need`:

- Low: minimal irrigation required  
- Medium: moderate irrigation  
- High: high irrigation demand  

Class distribution:

- Low: ~59%  
- Medium: ~38%  
- High: ~3%  

---

## Exploratory Data Analysis

Key findings:

- Soil moisture is the strongest predictor of irrigation need  
- High irrigation demand occurs under:
  - low soil moisture  
  - high temperature  
  - low rainfall  

- Crop type has limited influence compared to environmental factors  

---

## Methodology

### Preprocessing

- One-hot encoding for categorical variables  
- Train/test split with stratification  
- Handling class imbalance using class weights  

### Evaluation Metrics

- Accuracy  
- F1-score (weighted)  
- Recall (focus on minority class "High")  

---

## Models

The following models were evaluated:

- Dummy Classifier (baseline)  
- Logistic Regression  
- K-Nearest Neighbors  
- Decision Tree  
- Random Forest  
- Gradient Boosting  
- XGBoost  
- Support Vector Machine  
- Naive Bayes  

-> Note: in comparison with class weight and SMOTE! 

---

## Results

| Model | Accuracy | F1 Score | Recall (High) |
|------|--------|---------|---------------|
| Dummy | 0.58 | low | 0.00 |
| Random Forest | ... | ... | ... |
| XGBoost | ... | ... | ... |

---

## Key Insights

- Tree-based models performed best  
- Soil moisture dominates prediction performance  
- Class imbalance significantly impacts minority class detection  

---

## Limitations

- Dataset appears partially synthetic  
- Strong feature separation simplifies the problem  
- No temporal component included  

---

## Project Structure
data/ raw and processed datasets
notebooks/ EDA and modeling notebooks
src/ reusable code (preprocessing, models)
images/ plots and visualizations
results/ model outputs

---

## Setup

Install dependencies:
pip install -r requirements.txt

---

## Usage

Run notebooks in order:

1. `01_eda.ipynb`  
2. `02_preprocessing.ipynb`  
3. `03_models.ipynb`  

---

## Team

- Hedyeh  
- Sajit  
- Valerie  
- Ziya 