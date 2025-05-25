# 🧠 ML Task 1 – Romantic Relationship Prediction (Coding Club)

## 📌 Objective
The goal of this project is to perform **Exploratory Data Analysis (EDA)** on a student dataset, clean it, and train appropriate models to **predict whether a student is in a romantic relationship**.

---

## 🧼 Data Cleaning
- Checked for missing/null values across all columns.
- Imputed missing values using:
  - **Mean/Median** for normally distributed columns.
  - **Mode** for categorical columns.
  - **Relationship-based filling** for highly correlated features.
  
---

## 🔍 Feature Analysis (Feature_1, Feature_2, Feature_3)
- Used `describe()` to get statistical insights (mean, median, min, max).
- Visualized correlations of these features with variables like:
  - **absences**, **health**, **alcohol use (Dalc)**, **goout**, **freetime**
- Plotted:
  - **Boxplots**
  - **Stacked bar charts**
  - **Countplots**
- Inferred the nature of the unknown features based on patterns and distributions.

---

## ❓ Insightful Questions Answered
1. **How does parental education affect student performance?**
2. **Do urban vs rural students differ in performance and facilities?**
3. **Gender distribution among students in romantic relationships?**
4. **Comparison of grades between students in and not in romantic relationships.**
5. **Alcohol consumption patterns in romantic vs non-romantic students.**

---

## 🤖 Model Training

### 🔧 Preprocessing
- Converted `romantic` to binary (`yes` → 1, `no` → 0).
- One-hot encoded all categorical features.
- Removed low-correlation features.
- Applied `StandardScaler` to normalize numeric features.
- Tuned models using `GridSearchCV`.

### 🧪 Models Used
- **Naive Bayes Classifier**
  - Accuracy: ~70%
  - Confusion Matrix:
    ```
    [[73  9]
     [30 18]]
    ```
  - Precision:
    - Yes: 67%
    - No: 71%

- **Logistic Regression**
  - Accuracy: ~62%
  - Precision:
    - Yes: 49%
    - No: 75%

- **Random Forest Classifier**
  - Accuracy: ~62%
  - Precision:
    - Yes: 47%
    - No: 67%

💡 **Chose Logistic Regression** for its better interpretability with SHAP.

---

## 🔍 SHAP Interpretability

- Used **SHAP Beeswarm Plot** to identify global feature importance.
- Plotted **decision boundary** using `Feature_1 (age)` and `absences`.
- Generated **local explanations** for:
  - A student predicted as **Yes (in a relationship)**.
  - A student predicted as **No (not in a relationship)**.

These visualizations provided clear, interpretable reasons for the model’s predictions.

---

## 📁 Files Overview

| File / Folder       | Description                                 |
|---------------------|---------------------------------------------|
|        | Jupyter notebooks for EDA and model building |
|          | Plots generated for analysis and SHAP       |
| `       | Trained models and evaluation reports       |
| `README.md`         | This documentation                         |

---

## ✅ Conclusion
This project showcases how to:
- Clean and explore data effectively.
- Formulate and answer meaningful questions using visualizations.
- Train and compare classification models.
- Use SHAP to interpret ML model predictions with confidence.

---
