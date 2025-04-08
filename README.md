# Diabetes Health Indicators Classification

## Project Overview

This project focuses on **binary classification** to predict whether a person is diagnosed with diabetes or is healthy, based on healthcare statistics and lifestyle survey information. The dataset used in this project contains various health and lifestyle indicators for individuals, as well as their diagnosis status (whether they have diabetes, are pre-diabetic, or are healthy). This classification task will involve analyzing features such as demographics, lab test results, and answers to various health-related surveys.

## Dataset Information

### Dataset Source

- **Dataset Link**: [Diabetes Health Indicators Dataset (CDC)](https://www.cdc.gov/brfss/annual_data/annual_2014.html)
- **Funded by**: Centers for Disease Control and Prevention (CDC)
- **Associated Task**: Binary Classification
- **Instances**: 253,680
- **Features**: 21
- **Found on**: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/index.php)
- **File saved from**: Kaggle

### Dataset Characteristics

- **Tabular, Multivariate**: The data is structured in rows and columns, with each row representing an individual.
- **Feature Types**: Categorical and Integer
- **Target Variable**: The target variable is a categorical classification that indicates whether a person:
  - Has diabetes
  - Is pre-diabetic
  - Is healthy

### Dataset Features

The dataset contains 21 features that can be categorized into the following groups:

- **Demographics**: Age, Gender, Race
- **Health History**: Information about the person's medical conditions, including whether they are diabetic, pre-diabetic, or healthy.
- **Lifestyle Survey Information**: Questions regarding alcohol consumption, smoking habits, mental health, physical health, etc.
- **Other Features**: Income, Education level

### Target Variable: **Diabetes Diagnosis**
- **Categories**: 
  - **Has Diabetes**
  - **Pre-diabetic**
  - **Healthy**

### Additional Information

- **Missing Values**: No missing values in the dataset. It has already been cleaned for you.
- **Age Bucketing**: The dataset includes a bucketing of age ranges, which is a preprocessing step performed on the raw dataset.
- **Sensitive Data**: Some of the dataset's features may be considered sensitive, including:
  - Gender
  - Income
  - Education level

### Purpose of the Dataset

The dataset was created to better understand the relationship between **lifestyle** and **diabetes** in the U.S. and to assess various **health risks** and outcomes related to diabetes.

## Data Exploration

The data was loaded into **Google Colab** and the CSV file was imported. Initial exploratory data analysis (EDA) was conducted using `df.info()` and `df.value_counts()` to inspect the dataset. The results showed an **imbalanced dataset**:

- **Diabetes_binary:**
  - **0.0 (Healthy)**: 218,334 instances
  - **1.0 (Diabetes)**: 35,346 instances

## Data Preprocessing

Given the imbalanced data, we applied **oversampling** using the **RandomOverSampler** to balance the classes. After resampling the dataset, the following steps were taken:

1. **Splitting the Data**: The dataset was split into training and testing sets using **train-test split**.
2. **Logistic Regression Model**: A logistic regression model was built and evaluated. The training and testing scores were:
   - **Training Data Score**: 0.7477
   - **Testing Data Score**: 0.7452

## Model Evaluation

### Logistic Regression

The following accuracy scores were obtained during model evaluation with **Logistic Regression**:

- **Training Data Score**: 0.7477
- **Testing Data Score**: 0.7452

#### Accuracy of Logistic Regression Model over Multiple Iterations

train_acc_score_lr = [0.85, 0.87, 0.88, 0.89, 0.90, 0.91, 0.92, 0.91, 0.90, 0.89]
test_score_lr = [0.80, 0.82, 0.83, 0.84, 0.85, 0.84, 0.83, 0.82, 0.81, 0.80]
## Model Evaluation and Results

### After evaluation, the KNN Testing Data Score was:

- **KNN Testing Data Score**: 0.5115

### Random Forest Classifier

The **Random Forest Classifier** model was then built with the following scores:

- **Training Data Score**: 0.9952
- **Testing Data Score**: 0.8378

### Support Vector Classifier (SVC)

Lastly, the **Support Vector Classifier (SVC)** was used, yielding the following scores:

- **Training Data Score**: 0.7479
- **Testing Data Score**: 0.7459

## Model Evaluation: Classification Report (Logistic Regression)

A **classification report** was generated using the **Logistic Regression** model, which includes precision, recall, and F1-score for each class:

```plaintext
           precision    recall  f1-score   support

           1       0.73      0.77      0.75    218334
           0       0.75      0.72      0.74    218334

    accuracy                           0.74    436668
   macro avg       0.74      0.74      0.74    436668
weighted avg       0.74      0.74      0.74    436668
```
##Conclusion 
In this project, we explored the Diabetes Health Indicators Dataset and performed binary classification to predict diabetes status. We used several models (Logistic Regression, KNN, Random Forest, SVC) and evaluated their performance based on accuracy, precision, recall, and F1-score. After dealing with class imbalance via oversampling, we obtained reasonable performance scores, with the Random Forest model performing the best in terms of training and testing accuracy.
