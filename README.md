# Predicting School Dropout in Uganda

## 1. Project Overview

This project uses machine learning to predict student dropout in Uganda, leveraging the UWIZA 2015 socio-economic dataset. By identifying the key factors that contribute to a student leaving school, this work aims to provide actionable insights for policymakers, NGOs, and educational institutions to develop targeted intervention strategies.

The project explores two distinct modeling approaches: a classical machine learning model (**Random Forest**) and a deep learning model (**Neural Network**).

---
## 2. Dataset

[cite_start]The analysis is based on the **UWIZA 2015 dataset**, which includes comprehensive survey data from Uganda[cite: 46].

* [cite_start]**Data Sources**: The initial dataset was created by merging three separate files: household data, school data, and village data[cite: 48, 54, 55].
* [cite_start]**Feature Selection**: From an initial set of 456 variables, we selected 30 features most relevant to dropout, including student demographics, household characteristics, and environmental factors[cite: 56, 57].
* [cite_start]**Final Dataset**: To address class imbalance, the dataset was balanced by sampling an equal number of "Dropout" and "No Dropout" cases[cite: 62]. [cite_start]The final dataset used for modeling contains **1,948 observations** and 30 features[cite: 63, 124].

---
## 3. Methodology

The project follows a standard data science workflow:

### 3.1 Data Preprocessing
* [cite_start]**Data Cleaning**: Raw data was merged, and a relevant subset of features was selected[cite: 88, 105]. [cite_start]Missing values in the target variable were dropped[cite: 107].
* [cite_start]**Imputation**: Missing values in feature columns were handled using median imputation for numerical features and mode imputation for categorical features[cite: 199, 203].
* [cite_start]**Encoding & Scaling**: Categorical features were one-hot encoded, and numerical features were standardized using `StandardScaler` to prepare them for modeling[cite: 410, 411]. [cite_start]These steps were managed efficiently using `scikit-learn` Pipelines[cite: 413].

### 3.2 Exploratory Data Analysis (EDA)
[cite_start]Univariate and multivariate analyses were performed to understand the distributions of key variables (like age, gender, and household size) and their relationship with the `dropout` target variable[cite: 227, 328].

### 3.3 Modeling
Two models were developed and evaluated:

1.  **Random Forest Classifier**: A tree-based model known for its high performance and interpretability. [cite_start]The model was fine-tuned using `GridSearchCV` to find the optimal hyperparameters[cite: 453].
2.  [cite_start]**Feedforward Neural Network**: A deep learning model with three hidden layers ($64 \rightarrow 32 \rightarrow 16$), using Batch Normalization and Dropout for regularization[cite: 914]. [cite_start]The model was trained with early stopping to prevent overfitting[cite: 915].

---
## 4. Results & Key Findings

### 4.1 Model Performance
The models were evaluated on an unseen test set, with the Random Forest model achieving superior performance.

* **Random Forest**:
    * [cite_start]**Accuracy: 88%** [cite: 476]
    * [cite_start]Precision: 0.89 (Dropout), 0.87 (No Dropout) [cite: 546]
    * [cite_start]Recall: 0.87 (Dropout), 0.90 (No Dropout) [cite: 547]
* **Neural Network**:
    * [cite_start]**Accuracy: 83%** [cite: 917]
    * [cite_start]Precision: 0.82 [cite: 847]
    * [cite_start]Recall: 0.84 [cite: 848]

### 4.2 Feature Importance
The Random Forest model identified the most influential factors for predicting dropout:

1.  [cite_start]**Student Age**: The single most critical predictor (Importance: 0.168)[cite: 554].
2.  [cite_start]**Household Head's Age**: (Importance: 0.074)[cite: 556].
3.  [cite_start]**Household Size**: (Importance: 0.053)[cite: 557].
4.  [cite_start]**Household Gender Composition**: The number of males and females in the household[cite: 558].

[cite_start]These findings suggest that dropout risk is more closely tied to individual and household characteristics than to broader geographical factors[cite: 559].


---
## 5. Stakeholder Implications
[cite_start]The results from this project provide a data-driven foundation for creating targeted interventions, such as[cite: 561]:
* [cite_start]Developing retention programs aimed at **older students**[cite: 562].
* [cite_start]Providing support to **large households** that may be struggling with educational expenses[cite: 563].
* [cite_start]Considering the **demographics of the household head** when designing support programs[cite: 564].

---
## 6. Project Members
* [cite_start]Eugene Katusiime [cite: 11]
* [cite_start]Stephen Njuki [cite: 12]
* [cite_start]Joshua Kayongo [cite: 13]
* [cite_start]Akwi Tracy Aidah [cite: 14]
* [cite_start]Higenyi Yurri [cite: 15]
* [cite_start]Nabuyondo Hamirat Shibah [cite: 16]
* [cite_start]Alex Wadaba [cite: 17]
