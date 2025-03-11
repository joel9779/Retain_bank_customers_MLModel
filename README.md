# Retain_Bank_Customers
Bank Customer Churn Prediction

This project aims to predict customer churn using machine learning techniques, with a particular focus on addressing class imbalance. By exploring various resampling strategies and model tuning methods, the project demonstrates how to improve predictions for the minority class (customers who churn).

## Overview

- **Objective:**  
  Predict whether a customer will exit the bank using features such as credit score, age, balance, and more.

- **Challenge:**  
  The dataset exhibits class imbalance, with fewer examples of churned customers compared to non-churned ones.

- **Approach:**  
  Two main strategies were used to handle class imbalance:
  1. **Oversampling:** Duplicating minority class samples.
  2. **SMOTETomek:** Combining synthetic minority oversampling (SMOTE) with Tomek links to remove ambiguous samples.
  
  Hyperparameter tuning using GridSearchCV and threshold adjustment were performed to optimize model performance.

## Key Steps

1. **Data Preprocessing:**  
   - Encoding categorical variables (e.g., Geography, Gender).
   - Imputing missing values in the Tenure column using the median.
   - Scaling features using StandardScaler.

2. **Model Training:**  
   - Two models were trained: Logistic Regression and Random Forest.
   - Hyperparameter tuning was done using GridSearchCV with F1-score as the evaluation metric.
  
3. **Evaluation:**  
   - Initial results with imbalanced data showed high overall accuracy but very poor recall for the minority class.
   - Addressing class imbalance significantly improved the detection of churned customers, as measured by F1-score and AUC-ROC.
   - Final adjustments, including threshold tuning (optimal threshold found at 0.44), further enhanced performance.

## Results

- **Initial Logistic Regression:**  
  Overall accuracy ~80.45% but very low recall for churned customers.

- **Random Forest (Oversampling):**  
  Accuracy improved to ~84.8%, with an F1-score of 0.5789 and AUC-ROC of 0.7235.

- **Random Forest (SMOTETomek and Threshold Tuning):**  
  Further improvements with an F1-score of 0.5955 and AUC-ROC of 0.7346, indicating a balanced performance between precision and recall.

## Conclusion

By effectively handling class imbalance and fine-tuning model parameters and decision thresholds, the final Random Forest model provides a robust solution for predicting customer churn. This project demonstrates the importance of data preprocessing and the use of advanced resampling techniques in imbalanced classification tasks.

## License

This project is licensed under the [MIT License](LICENSE).

