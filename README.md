# Models-.gitkeep
Building Insurance Claim Prediction

**Project Overview

Insurance companies need to identify buildings that are likely to record at least one insurance claim during an insured period.
This project builds a machine learning classification model to predict the probability of claim occurrence based on building characteristics.

Target Variable: Claim

1 → Building had at least one claim during the insured period

0 → Building had no claim during the insured period

The objective is to support risk assessment and decision-making in insurance underwriting.

**Dataset Summary

The dataset contains building-related features such as:

Year of observation

Insured period duration

Residential status

Building condition indicators (e.g., painted, fenced)

Location information (e.g., settlement type, geo code)

Structural details (e.g., number of windows, building dimension)

Date/year of occupancy

**Problem Type:

Supervised learning → Binary Classification

**Key Data Challenges:

Missing values in some categorical and location-related columns

Presence of outliers (notably in Building_Dimension)

Class imbalance (more 0s than 1s)

**Workflow / Methodology
1️. Data Cleaning & Preprocessing

Renamed ambiguous columns for clarity

Checked and handled missing values:

Categorical features filled with "Unknown"

Numerical features filled with median where applicable

Checked data types and ensured compatibility for modeling

Outlier/skewness detection using boxplots (notably for Building_Dimension)

2️. Exploratory Data Analysis (EDA)

Target distribution and class imbalance check

Numerical feature distribution analysis

Categorical feature count plots

Claim rate analysis across key categorical variables

Insights were used to guide preprocessing and feature handling

3️. Feature Engineering

Prepared numerical and categorical columns for model training

Used OneHotEncoding for categorical variables

Used StandardScaler for numerical variables (especially useful for linear models)

4️. Modeling

The following models were implemented and compared:

Logistic Regression (baseline)

Random Forest

Gradient Boosting

*Hyperparameter tuning was applied for:

Random Forest 

Gradient Boosting 

5️. Model Evaluation

Models were evaluated using:

Accuracy

F1-score (important for imbalanced classification)

ROC-AUC (important for probability ranking)

Confusion Matrix

Classification Report (precision, recall, f1-score)

**Results Summary (Tuned Models)

1. Random Forest (Tuned) — Best Performing for Claim Detection

Accuracy: 0.712

F1-score: 0.429

ROC-AUC: 0.693

Confusion Matrix:

TN = 864, FP = 241

FN = 172, TP = 155

This model achieved the best balance for identifying claim cases (higher recall and F1-score for Claim=1).

2. Gradient Boosting (Tuned)

Accuracy: 0.756

F1-score: 0.343

ROC-AUC: 0.664

Confusion Matrix:

TN = 992, FP = 113

FN = 236, TP = 91

This model achieved better accuracy but weaker claim detection performance compared to tuned Random Forest.

**Final Model Selection

The Tuned Random Forest model was selected as the final model because it produced the best overall performance for detecting Claim = 1 (higher F1-score and recall), which is critical for insurance risk prediction.

**How to Run This Project

1. Clone the Repository
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>

2. Install Required Libraries
pip install -r requirements.txt

pip install pandas numpy matplotlib seaborn scikit-learn

3. Open the Notebook

Run with JupyterLab:

jupyter lab


Then open:
*Insurance_Claim_Prediction.ipynb
