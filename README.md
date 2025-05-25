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
# Task2

# Multi-Tool Conversational AI with LangGraph and Google Gemini
-- This notebook builds a chatbot that can solve math problems, check the weather, and share fashion trends based on location. It uses Google’s Gemini model through LangChain for smart responses and spaCy for understanding locations. LangGraph manages the conversation flow to decide which tool to call.

## How the Notebook is Structured

1. # Setup and API Key Handling
We start by importing required libraries and setting your Google API key securely with getpass. This keeps your key safe while the notebook runs.

2. # Initialize the Language Model
Next, we create a Google Gemini chat model instance (gemini-1.5-flash) with a moderate temperature for balanced replies.

3. # Calculator Tool
We define a simple calculator tool that evaluates basic math expressions. If the input isn’t a clear math expression, it passes it to the language model to respond naturally.

4. # Basic Chatbot Logic with LangGraph
We write a chatbot function that checks your input:

If it contains math operators, it uses the calculator tool.

Otherwise, it sends the input to the language model.
This logic is wrapped in a LangGraph StateGraph with a single node handling the chat.

5. # Visualizing the Chatbot Graph
The notebook then generates and displays a flowchart (using Mermaid format) showing the chatbot’s simple graph structure.

6. # Fashion Tool
We add a new tool to detect locations using spaCy’s named entity recognition. When it finds a city or country, it asks the language model for current fashion trends there. If no location is found, it prompts the user to specify one.

7. # Weather Tool
This tool also uses spaCy to find city names in your input, then calls the OpenWeatherMap API to get current weather details like temperature, humidity, wind, and sunrise/sunset times.

8. # Improved Chatbot Node with Multiple Tools
We upgrade the chatbot function so it:
Uses the calculator for math expressions,
Calls the weather tool if the input mentions weather-related words,
Uses the fashion tool if the input relates to clothing or trends,
Otherwise, asks the user to keep to one topic at a time.
API keys for weather are requested securely when needed.

9. # Conversation Loop
Finally, there’s an interactive loop that:
Prompts you for input,
Sends your input through the chatbot graph,
Prints the bot’s response,
Keeps a running memory of the chat,
Ends when you type exit.


