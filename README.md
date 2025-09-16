
# Predicting School Dropout in Uganda
## Notebook Demo Video: https://drive.google.com/file/d/1KCOBadlr-40dNLgDE9dv8VppLhdoVBlf/view?usp=drive_link
## Presentation Slides: https://gamma.app/docs/Predicting-School-Dropout-in-Uganda-wfckyswti51ycog?mode=present#card-pqrt8r03jg0s5ni
## 1. Project Overview

This project uses machine learning to predict student dropout in Uganda, leveraging the UWIZA 2015 socio-economic dataset. By identifying the key factors that contribute to a student leaving school, this work aims to provide actionable insights for policymakers, NGOs, and educational institutions to develop targeted intervention strategies.

The project explores two distinct modeling approaches: a classical machine learning model (**Random Forest**) and a deep learning model (**Neural Network**).

---
## 2. Dataset

The analysis is based on the **UWIZA 2015 dataset**, which includes comprehensive survey data from Uganda.

* **Data Sources**: The initial dataset was created by merging three separate files: household data, school data, and village data.  
* **Feature Selection**: From an initial set of 456 variables, we selected 30 features most relevant to dropout, including student demographics, household characteristics, and environmental factors.  
* **Final Dataset**: To address class imbalance, the dataset was balanced by sampling an equal number of "Dropout" and "No Dropout" cases. The final dataset used for modeling contains **1,948 observations** and 30 features.

---
## 3. Methodology

The project follows a standard data science workflow:

### 3.1 Data Preprocessing
* **Data Cleaning**: Raw data was merged, and a relevant subset of features was selected. Missing values in the target variable were dropped.  
* **Imputation**: Missing values in feature columns were handled using median imputation for numerical features and mode imputation for categorical features.  
* **Encoding & Scaling**: Categorical features were one-hot encoded, and numerical features were standardized using `StandardScaler` to prepare them for modeling. These steps were managed efficiently using `scikit-learn` Pipelines.  

### 3.2 Exploratory Data Analysis (EDA)
Univariate and multivariate analyses were performed to understand the distributions of key variables (like age, gender, and household size) and their relationship with the `dropout` target variable.

### 3.3 Modeling
Two models were developed and evaluated:

1. **Random Forest Classifier**: A tree-based model known for its high performance and interpretability. The model was fine-tuned using `GridSearchCV` to find the optimal hyperparameters.  
2. **Feedforward Neural Network**: A deep learning model with three hidden layers ($64 → 32 → 16$), using Batch Normalization and Dropout for regularization. The model was trained with early stopping to prevent overfitting.

---
## 4. Results & Key Findings

### 4.1 Model Performance
The models were evaluated on an unseen test set, with the Random Forest model achieving superior performance.

* **Random Forest**:
  * **Accuracy: 88%**  
  * Precision: 0.89 (Dropout), 0.87 (No Dropout)  
  * Recall: 0.87 (Dropout), 0.90 (No Dropout)  
* **Neural Network**:
  * **Accuracy: 83%**  
  * Precision: 0.82  
  * Recall: 0.84  

### 4.2 Feature Importance
The Random Forest model identified the most influential factors for predicting dropout:

1. **Student Age**: The single most critical predictor (Importance: 0.168).  
2. **Household Head's Age**: (Importance: 0.074).  
3. **Household Size**: (Importance: 0.053).  
4. **Household Gender Composition**: The number of males and females in the household.  

These findings suggest that dropout risk is more closely tied to individual and household characteristics than to broader geographical factors.

---
## 5. Stakeholder Implications
The results from this project provide a data-driven foundation for creating targeted interventions, such as:

* Developing retention programs aimed at **older students**.  
* Providing support to **large households** that may be struggling with educational expenses.  
* Considering the **demographics of the household head** when designing support programs.  

---
## 6. Project Members
* Eugene Katusiime  
* Stephen Njuki  
* Joshua Kayongo  
* Akwi Tracy Aidah  
* Higenyi Yurri  
* Nabuyondo Hamirat Shibah  
* Alex Wadaba  
