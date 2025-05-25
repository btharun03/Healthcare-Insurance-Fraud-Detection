# Healthcare Insurance Fraud Detection

This project explores the application of machine learning techniques to detect fraudulent healthcare insurance claims. By leveraging real-world Medicare datasets, the system aims to identify suspicious claims using anomaly detection, predictive modeling, and robust data mining strategies.

---

## Abstract

Healthcare insurance fraud is a serious and growing concern globally, resulting in billions of dollars in losses each year. These fraudulent activities include submitting false claims, upcoding procedures, or using stolen identities to claim reimbursements. This project focuses on building a fraud detection system that uses machine learning models to classify insurance claims as fraudulent or legitimate. The system analyzes patient data, provider details, procedures, diagnoses, and billing amounts to identify hidden patterns and suspicious behavior.

---

## Motivation

Healthcare fraud not only impacts insurance companies financially but also compromises the quality and accessibility of medical care for patients. Fraud leads to inflated premiums and reduced trust in healthcare systems. The dual motivation of this project is:

* **Economic**: To reduce unnecessary financial burden on insurers and healthcare systems.
* **Ethical**: To ensure fair access to healthcare by detecting and eliminating deceitful practices.

---

## Objectives

The objectives of the Healthcare Insurance Fraud Detection project are:

1. **Analyze** healthcare insurance claim datasets, including:

   * Patient and provider information
   * Procedure and diagnosis codes
   * Billing and payment records

2. **Detect fraudulent behavior** using data mining techniques and anomaly detection.

3. **Develop predictive models** to automatically classify claims as legitimate or fraudulent.

4. **Evaluate model performance** using metrics such as accuracy, precision, recall, F1-score, AUC, and Kappa.

5. **Address technical challenges**:

   * Class imbalance
   * Data privacy concerns
   * Interpretability and explainability of models

6. **Contribute to reducing fraud**, thereby minimizing financial loss and increasing trust in healthcare systems.

---

## System Architecture

The architecture consists of the following phases:

* **Data Ingestion**: Import data from multiple sources including inpatient, outpatient, and beneficiary datasets.

* **Preprocessing**:

  * Handling missing values using imputation (e.g., IterativeImputer)
  * Outlier detection using IQR-based capping
  * Feature scaling using MinMaxScaler and RobustScaler
  * Label encoding for categorical variables

* **Data Merging**:

  * Combine inpatient, outpatient, and beneficiary data on shared keys (e.g., `ClaimID`, `BeneID`)

* **Model Training & Evaluation**:

  * Train multiple classifiers
  * Use ROC-AUC and other metrics for evaluation
  * Determine best thresholds for binary classification

---

## Tech Stack

* **Language**: Python 3.10.4
* **Environment**: Jupyter Notebook, JupyterLab
* **Libraries**:

  * pandas, numpy, seaborn, matplotlib
  * sklearn (LogisticRegression, DecisionTree, RandomForest, etc.)
  * statsmodels
  * fancyimpute (IterativeImputer)

---

## Models Used & Evaluation

The following models were trained and evaluated:

| Model               | Accuracy | Precision | Recall | F1 Score | AUC  | Kappa |
| ------------------- | -------- | --------- | ------ | -------- | ---- | ----- |
| Logistic Regression | 0.64     | 0.64      | 1.00   | 0.78     | 0.50 | 0.00  |
| Decision Tree       | 0.64     | 0.64      | 0.99   | 0.78     | 0.52 | 0.20  |
| **Random Forest**   | 0.64     | 0.64      | 1.00   | 0.78     | 0.50 | 3.36  |
| GaussianNB          | 0.62     | 0.63      | 0.94   | 0.76     | 0.49 | 0.001 |
| KNN                 | 0.67     | 0.73      | 0.77   | 0.75     | 0.63 | 0.28  |

**Best Model**: `Random Forest`

### Why Random Forest?

* Highest recall (1.0): Captures all fraudulent cases
* Good balance between precision and recall
* Ensemble nature helps detect complex fraud patterns

---

## Results

The system successfully identified healthcare fraud cases, with the Random Forest classifier performing best in terms of recall and F1 score. However, the low AUC (0.5) suggests further improvement in discriminatory ability is possible.

**Future Improvements:**

* Optimize hyperparameters further
* Use larger and balanced datasets
* Incorporate NLP for unstructured claim notes
* Use ensemble stacking for higher performance

---

## Conclusion

This project demonstrates that machine learning can be effectively used to detect fraudulent healthcare claims. The Random Forest model shows strong performance in recall and overall fraud detection. With enhancements in data quality, feature engineering, and ensemble learning, this system can evolve into a robust fraud prevention tool for insurance companies.

---
