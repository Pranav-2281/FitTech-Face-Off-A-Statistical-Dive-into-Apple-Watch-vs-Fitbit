# 📊 Bridging Technology and Health: A Comprehensive Analysis of Fitbit and Apple Watch in Enhancing User Engagement and Activity Efficiency

## 📌 Project Overview

This project investigates how wearable devices—specifically the **Apple Watch** and **Fitbit**—influence **user engagement**, **physical activity levels**, and **activity efficiency**. Using minute-level physiological data from real users, we explored the impact of device type and individual characteristics (age, gender, weight, height) on:

- Step count and distance covered  
- Activity classification  
- Calorie burn efficiency (calories/step)  
- Heart rate variability across age/activity groups  

Our goal is to generate insights that can influence consumer choice, device improvements, and personalized health recommendations.

---

## 📂 Dataset Description

The dataset contains over **78,000 records** collected at **1Hz frequency**, resampled to minute-level metrics from **Fitbit** and **Apple Watch** devices.

**Key features:**
- `Heart`: Heart rate (bpm)
- `Calories`: Calories burned
- `Steps`: Number of steps
- `Distance`: Distance in km
- `Age`, `Weight`, `Height`: Demographics
- `Gender`: Male or Female
- `Activity`: Sleep, Sedentary, Light, Moderate, Vigorous
- `Device`: Apple Watch or Fitbit

---

## 🧹 Data Preparation

- Interpolated missing heart rate data  
- Converted categorical features (e.g., Device, Gender) to dummy variables  
- Created derived features like `Calories_per_Step`  
- Standardized numerical features using `StandardScaler`  

---

## 🧠 Research Questions & Methods

### 1. Which device encourages more physical activity?
Compare average steps and distance between Apple Watch and Fitbit users.

**Methods**:
- Descriptive stats, bar plots
- Logistic regression (Low/Medium/High activity)

### 2. Can we classify activity type from physical metrics?
**Models**: Logistic Regression, Support Vector Machine  
**Evaluation**: F1-score, ROC-AUC

### 3. How efficient is physical activity (calories/step)?
**Models**: Ridge Regression, LASSO Regression (via `glmnet` in R)  
**Findings**:
- Higher heart rate and age → better efficiency
- Fitbit users slightly less efficient
- Ridge MSE: 0.02537, LASSO MSE: 0.02538

### 4. How does activity level affect HRV by age group?
- Step-based activity bins (Sedentary to Highly Active)
- Linear regression, ANCOVA
- Stratified analysis by age group

---

## 🔍 Exploratory Data Analysis

- **Correlation matrix**: Steps, Calories, Heart Rate are strongly related  
- **Pairplots**: Show gender differences in metrics  
- **Coefficient plots**: Ridge vs LASSO comparisons  

---

## 📈 Model Results

| Model                | Metric                    | Performance |
|---------------------|---------------------------|-------------|
| Ridge Regression     | MSE                       | 0.02537     |
| Lasso Regression     | MSE                       | 0.02538     |
| Logistic Regression  | F1-score (activity level) | Varies by class |
| Random Forest        | Age group classification  | Best classifier |
| Gradient Boosting    | Age group classification  | Competitive |

---

## 🧪 Validation & Tuning

- **Cross-validation**: K-Fold CV (K=5)  
- **Grid Search**: Hyperparameter tuning for SVM/logistic regression  
- **Metrics**: RMSE for regression; Accuracy, F1, ROC-AUC for classification  

---

## 📚 Acknowledgements

- **Course**: Statistical Learning, Georgetown University
- **Team Members:** Alex Choi, Pranav Patil, Will Corbin
- **Poster:** Presented at DSAN 5300, Spring 2025

---

## 📌 Future Work

- Expand to more wearable brands
- Include direct HRV sensors
- Deploy dashboard for real-time engagement insights

---
