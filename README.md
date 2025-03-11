# Bank Customer Churn Prediction

This project aims to predict customer churn for a bank using machine learning techniques. The focus is on handling class imbalance using multiple resampling strategies and optimizing model performance through hyperparameter tuning and threshold adjustment.

## Table of Contents

- [Overview](#overview)
- [Project Structure](#project-structure)
- [Data](#data)
- [Installation and Dependencies](#installation-and-dependencies)
- [Usage](#usage)
- [Modeling Approach](#modeling-approach)
  - [Data Preprocessing](#data-preprocessing)
  - [Handling Class Imbalance](#handling-class-imbalance)
  - [Model Training and Hyperparameter Tuning](#model-training-and-hyperparameter-tuning)
  - [Final Evaluation and Threshold Tuning](#final-evaluation-and-threshold-tuning)
- [Results](#results)
- [Conclusion](#conclusion)
- [License](#license)

## Overview

This project builds machine learning models (Logistic Regression and Random Forest) to predict whether a customer will churn (exit). Due to class imbalance in the dataset, multiple resampling techniques (oversampling and SMOTETomek) are employed to improve the detection of the minority class. The project also demonstrates hyperparameter tuning and probability threshold adjustment to optimize model performance.

## Project Structure


## Data

The dataset (`churn.csv`) contains 10,000 records with the following key features:
- **Identifiers:** `RowNumber`, `CustomerId`, `Surname` (not used for modeling)
- **Numerical Features:** `CreditScore`, `Age`, `Balance`, `EstimatedSalary`
- **Categorical Features:** `Geography`, `Gender`
- **Additional Features:** `Tenure` (with some missing values), `NumOfProducts`, `HasCrCard`, `IsActiveMember`
- **Target Variable:** `Exited` (1 if the customer churned, 0 otherwise)

## Installation and Dependencies

Ensure you have Python 3.7 or later installed. Install the required packages using pip:

```bash
pip install -r requirements.txt
