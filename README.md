Bank Customer Churn Prediction

This project aims to predict customer churn for a bank using machine learning techniques. It includes data preprocessing, addressing class imbalance, model tuning, and final evaluation.
Table of Contents

    Overview
    Project Structure
    Data
    Installation and Dependencies
    Usage
    Modeling Approach
        Data Preprocessing
        Handling Class Imbalance
        Model Training and Hyperparameter Tuning
        Final Evaluation and Threshold Tuning
    Results
    Conclusion
    License

Overview

This project builds and tunes machine learning models (Logistic Regression and Random Forest) to predict whether a customer will exit (churn). A significant challenge in this dataset is class imbalance, which was addressed using oversampling and the SMOTETomek technique. Hyperparameter tuning and decision threshold adjustments further improved the model's performance for the minority class.
Project Structure

├── churn.csv                  # Dataset containing bank customer information
├── notebooks/                 # Jupyter Notebooks for exploratory data analysis and modeling
├── src/
│   ├── preprocessing.py       # Data cleaning and preprocessing routines
│   ├── modeling.py            # Model training and evaluation scripts
│   └── utils.py               # Utility functions (e.g., for plotting, metrics)
├── README.md                  # This file
└── requirements.txt           # Python package dependencies

Data

The dataset (churn.csv) contains 10,000 entries with the following features:

    RowNumber, CustomerId, Surname: Identifiers (not used for modeling)
    CreditScore, Age, Balance, EstimatedSalary: Numerical features
    Geography, Gender: Categorical features
    Tenure: Period of maturation for a fixed deposit (contains missing values)
    NumOfProducts, HasCrCard, IsActiveMember: Categorical or binary features
    Exited: Target variable (1 for churn, 0 for not churn)

Installation and Dependencies

Make sure you have Python 3.7 or later installed. Then, install the required packages using pip:

pip install -r requirements.txt

The key dependencies include:

    pandas
    numpy
    matplotlib
    seaborn
    scikit-learn
    imbalanced-learn

Usage

    Data Exploration and Preprocessing:
        Open the Jupyter Notebook in the notebooks/ directory.
        Run the cells to load the dataset, explore missing values, and perform data cleaning and encoding.

    Model Training and Tuning:
        The notebooks demonstrate different approaches for handling class imbalance.
        Models are trained with hyperparameter tuning using GridSearchCV.
        Both Logistic Regression and Random Forest classifiers are evaluated.

    Final Testing and Evaluation:
        The final model (Random Forest) is tested on a hold-out test set.
        Evaluation metrics include Accuracy, AUC-ROC, and F1-Score.
        The decision threshold is tuned to optimize the F1-Score.

Modeling Approach
Data Preprocessing

    Encoding: Categorical variables such as Geography and Gender are label-encoded.
    Missing Values: Missing values in Tenure are imputed using the median.
    Scaling: Features are standardized with StandardScaler.

Handling Class Imbalance

Two techniques were used:

    Oversampling: The minority class was oversampled to balance the classes.
    SMOTETomek: A combination of Synthetic Minority Oversampling Technique (SMOTE) and Tomek links was applied to both synthesize new samples and remove ambiguous majority samples.

Model Training and Hyperparameter Tuning

    Logistic Regression and Random Forest: Both models were tuned using GridSearchCV on a balanced training set.
    Parameter Grid: Various values for regularization (for Logistic Regression) and number of trees / depth (for Random Forest) were explored.

Final Evaluation and Threshold Tuning

    Evaluation Metrics: Accuracy, classification report (precision, recall, F1-score), AUC-ROC, and F1-score were computed.
    Threshold Tuning: The prediction probability threshold was optimized to maximize the F1-score for the minority class.

Results

    Logistic Regression: After balancing, the Logistic Regression model showed improvement in recall for the minority class but overall performance was still limited.
    Random Forest: The best performing model was the Random Forest classifier.
        Accuracy: ~84.8%
        AUC-ROC: 0.7235 (baseline), improved to 0.7346 with SMOTETomek.
        F1-Score: Improved from 0.5789 to 0.5955 after threshold tuning.

Conclusion

By addressing class imbalance using both oversampling and the SMOTETomek method, and by tuning hyperparameters and prediction thresholds, the final Random Forest model provides a better balance between sensitivity and specificity for predicting customer churn. This process underscores the importance of not only model selection but also data preprocessing in imbalanced classification tasks.