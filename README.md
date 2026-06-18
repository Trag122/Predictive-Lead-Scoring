# Predictive Lead Scoring using Machine Learning

## Project Overview

This project focuses on developing a predictive lead scoring system using machine learning models within the context of digital banking. The primary objective is to maximize **Recall** to accurately identify the maximum number of potential customers who are likely to convert to financial products, thereby minimizing missed business opportunities from a telemarketing campaign.

## Dataset
**Data Source:** Information collected from a telemarketing campaign conducted by a bank in Portugal.
**Size:** **41,188** customer profiles.
**Features:** The dataset includes demographic data (age, job, marital status, education), financial attributes (default history, housing/loan status), behavioral interaction data, and macroeconomic indicators (employment variation, consumer confidence index, interest rates).

## Architecture and Pipeline

The solution is structured into five main architectural components:

1. **Input Layer:** Ingests data from the multiple domains mentioned above.

2. **Preprocessing Layer:** * Handles missing values using mean imputation.

* Detects and filters outliers using a Z-score threshold of 3.0.
* Standardizes numerical features using `StandardScaler`.
* Encodes categorical variables using `LabelEncoder`.
* Balances the dataset using the **SMOTE** technique to mitigate class imbalance.

3. **Machine Learning Layer:** Implements four models (Logistic Regression, Decision Tree, Random Forest, LightGBM) and optimizes hyperparameters using Optuna.

4. **Evaluation Layer:** Assesses model quality using metrics such as ROC-AUC, Precision, Recall, and F1-score.

5. **Output Layer:** Outputs the predicted label (0 or 1) and conversion probability, utilizing a lowered classification threshold of **0.4** to predict more cases as positive and catch more potential leads.

## Technologies & Libraries
 
**Language & Environment:** Python executed within Jupyter Notebook.
 
**Data Manipulation:** Pandas, NumPy.
 
**Machine Learning:** Scikit-learn (training, preprocessing, evaluation), Imbalanced-learn (SMOTE), Optuna (hyperparameter optimization).
 
**Visualization:** Matplotlib.

## Evaluation Results

After comparing the four models, **LightGBM** was selected as the optimal model because it is the most balanced. It successfully achieves high recall while maintaining accuracy and stability across other metrics:
 
**ROC-AUC:** 0.9392 
**Recall:** 0.9262 
**Precision:** 0.4122 
**F1-score:** 0.5705 
**Test Accuracy:** 0.8417 

When sorting the evaluation dataset by predicted probability, the LightGBM model achieved a **Precision@50 of 86%**. This indicates that actions taken on the Top 50 individuals prioritized by the model will hit the actual target 86% of the time.

## Author 
@All Rights Reserved.
* **Nguyen Pham Quynh Trang**
* **Major:** Fintech and Digital Business 
* **Institution:** VNU International School

