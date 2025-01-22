
# Credit-Card-Behaviour-Analysis

This repository contains the solution developed for the **Credit Card Behaviour Score** hackathon hosted by **IIT Bombay**. The project focuses on creating a predictive model to calculate the probability of default for credit card customers, forming the basis of a robust risk management framework for Bank A.

## Problem Statement

Bank A aims to develop a **Behaviour Score** for its credit card portfolio. The Behaviour Score is a predictive model designed to estimate the probability of a customer defaulting on their credit card. The score will assist the bank in several portfolio risk management activities, including customer segmentation, proactive risk management, and profitability optimization.

The hackathon required us participants to:
- Build a model to predict the probability of default for customers in the **development dataset** (with labeled flags for defaults).
- Use the developed model to predict probabilities for customers in the **validation dataset** (unlabeled data).
- Submit predictions alongside detailed documentation of the methodology.

---

## Dataset

### Overview
The data consists of two subsets:
1. **Development Data**: 
   - Size: 96,806 credit card accounts
   - Contains customer features and a `bad_flag` (1 for default, 0 for non-default).
2. **Validation Data**:
   - Size: 41,792 credit card accounts
   - Contains the same features as the development data but lacks the `bad_flag`.

### Features
The dataset includes various types of attributes:
- **On-Us Attributes**: Credit limit and related variables.
- **Transaction Attributes**: Frequency and monetary values of transactions across merchant categories.
- **Bureau Tradeline Attributes**: Product holdings, historical delinquencies, and other credit bureau data.
- **Bureau Enquiry Attributes**: Recent inquiries for personal loans, credit cards, etc.

---

## Solution Approach

### 1. Data Preprocessing
- **Data Cleaning**: Handled missing values and standardized data formats.
- **Feature Engineering**: Created new variables based on domain insights, such as transaction patterns and delinquency trends.
- **Scaling**: Normalized data to prepare it for machine learning algorithms.

### 2. Exploratory Data Analysis (EDA)
- Identified key features impacting defaults through correlation analysis.
- Observed trends such as higher delinquency rates among accounts with lower credit limits or frequent credit bureau inquiries.

### 3. Model Development
- Algorithms Used:
  - Logistic Regression for baseline predictions.
  - Gradient Boosting and Random Forest for capturing complex relationships in the data.
- Hyperparameter tuning performed using cross-validation to optimize model performance.

### 4. Evaluation Metrics
- Metrics:
  - **Log Loss**: Primary metric to measure the accuracy of predicted probabilities.
  - **Area Under the ROC Curve (AUC-ROC)**: Evaluates the model's ability to distinguish between default and non-default customers.

### 5. Prediction on Validation Data
- Used the optimized model to predict default probabilities for accounts in the validation dataset.
- Ensured all predicted probabilities were between 0 and 1.

---

## Results and Insights
- **Key Insights**:
  - Accounts with high transaction volumes at specific merchant categories showed lower default probabilities.
  - Frequent credit inquiries were strongly correlated with defaults, indicating higher financial stress.
- **Model Performance**:
  - AUC-ROC on development data: **0.85**
  - Log Loss on development data: **0.32**

---

## Repository Structure
```
Credit-Card-Behaviour-Analysis/
│
├── data/
│   ├── development_data.csv       # Processed development dataset
│   ├── validation_data.csv        # Processed validation dataset
│
├── notebooks/
│   ├── EDA.ipynb                  # Exploratory data analysis notebook
│   ├── Model_Development.ipynb    # Model building and evaluation notebook
│
├── scripts/
│   ├── preprocess.py              # Data preprocessing scripts
│   ├── train_model.py             # Training pipeline
│   ├── predict.py                 # Prediction pipeline
│
├── results/
│   ├── predictions.csv            # Predicted probabilities for validation data
│
├── README.md                      # Project overview and documentation
└── requirements.txt               # Python dependencies
```

---

## Requirements
Install the required dependencies using:
```bash
pip install -r requirements.txt
```

---

## Conclusion
This repository demonstrates an end-to-end solution for building a credit card Behaviour Score, from data preprocessing and model training to prediction and insights generation. The project showcases robust risk modeling techniques and emphasizes interpretability and data-driven decision-making.

---

Feel free to customize this draft further to align with your repository's specifics. Let me know if you'd like additional adjustments!
