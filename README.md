# 🧠 ML Task 1 – Romantic Relationship Prediction (Coding Club)

## 📌 Objective
The aim of this project is to perform **Exploratory Data Analysis (EDA)** on a student dataset, clean it thoroughly, and train machine learning models to **predict whether a student is in a romantic relationship**.

---

## 🧼 Data Cleaning
- Checked for missing/null values in all columns.
- Imputed missing values using:
  - **Mean/Median** for numerical columns with normal distribution.
  - **Mode** for categorical columns.
  - **Relationship-based imputation** for features showing strong correlations.

---

## 🔍 Feature Analysis (Feature_1, Feature_2, Feature_3)
- Used `describe()` for statistical summaries (mean, median, min, max).
- Analyzed correlations between features and variables such as:
  - **absences**, **health**, **daily alcohol consumption (Dalc)**, **going out frequency (goout)**, **free time**
- Visualized data with:
  - **Boxplots**
  - **Stacked bar charts**
  - **Countplots**
- Deduced the nature and influence of the unknown features based on observed patterns.

---

## ❓ Insightful Questions Answered
1. **How does parental education affect student performance?**
2. **Do students from urban areas differ from rural students in performance and facilities?**
3. **How does parental separation affect students?**

5. **How do grades compare between students in and not in romantic relationships?**
6. **What are the alcohol consumption patterns in romantic versus non-romantic students?**

---

## 🤖 Model Training

### 🔧 Preprocessing
- Converted `romantic` column to binary values (`yes` → 1, `no` → 0).
- One-hot encoded categorical variables.
- Removed features with low correlation to the target variable.
- Normalized numerical features using `StandardScaler`.
- Used `GridSearchCV` for hyperparameter tuning.

### 🧪 Models Used and Performance

- **Naive Bayes Classifier**
  - Accuracy: ~70%
  - Confusion Matrix:
    ```
    [[73  9]
     [30 18]]
    ```
  - Precision:
    - Romantic = Yes: 67%
    - Romantic = No: 71%

- **Logistic Regression**
  - Accuracy: ~62%
  - Precision:
    - Romantic = Yes: 49%
    - Romantic = No: 75%

- **Random Forest Classifier**
  - Accuracy: ~62%
  - Precision:
    - Romantic = Yes: 47%
    - Romantic = No: 67%

💡 **Selected Model: Logistic Regression**  
Despite Naive Bayes having a higher accuracy, Logistic Regression was chosen for its interpretability and balanced precision on class labels.

---

## 🔍 Model Interpretation
- Used **SHAP** (SHapley Additive exPlanations) to interpret model predictions.
- Gained insights on feature importance and their effects on prediction confidence.

---

## 📦 Package Versions Used
- pandas: 2.2.3
- numpy: 1.26.4
- matplotlib: 3.7.2
- seaborn: 0.12.2
- shap: 0.44.1

---

## 📖 How to Run
1. Install required packages (versions noted above).
2. Load the dataset.
3. Perform EDA and data cleaning as described.
4. Train models and evaluate performance.
5. Use SHAP for model interpretation.

---

## 📝 Notes
- Focus was on thorough exploratory analysis before modeling.
- Model selection prioritized interpretability alongside accuracy.
- Parental status and alcohol consumption emerged as important factors.

---



