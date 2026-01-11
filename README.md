# Insurance Claim Prediction

## Project Overview
This project aims to **predict whether a building will have at least one insurance claim** during the insured period based on its characteristics. The target variable `Claim` is:

- `1` if the building has at least one claim 
- `0` if the building has no claims 

The dataset includes building features, observation year, insured period, and other categorical and numerical attributes.

---

## Project Structure

Insurance-claim-prediction/
├── data/
│   ├── cleaned_train_data.csv
│   ├── Train_data.csv
│   └── Variable_Description.csv
├── notebooks/
│   ├── 01_data_cleaning.ipynb
│   ├── 02_eda.ipynb
│   ├── 03_modeling.ipynb
└── README.md

---

## Data Cleaning & Preprocessing

- Checked for missing values and handled them appropriately. 
- Encoded categorical variables using one-hot encoding. 
- Selected numeric and boolean features for modeling. 
- Split data into **train and test sets** (80-20). 

---

## Exploratory Data Analysis (EDA)

- The target variable `Claim` is **imbalanced**, with fewer buildings having claims. 
- Most numeric features are boolean (0/1) with a few continuous features like building dimensions. 
- Correlations with the target are generally weak to moderate. 
- Feature importance and visualization highlight key predictors.

---

## Modeling

### 1. Logistic Regression

- Baseline model with class balancing. 
- ROC-AUC: `0.688` 
- Handles linear relationships; struggles with rare claims. 

### 2. Random Forest Classifier

- Captures non-linear interactions and complex relationships. 
- ROC-AUC: `0.678` 
- Better precision for minority class but recall remains low due to class imbalance. 

---

## Feature Importance (Random Forest)

Top 10 features driving predictions:

1. Building dimension 
2. Date of occupancy 
3. Year of observation 
4. Insured period 
5. Building type 
6. Residential 
7. Numberofwindow_2 
8. Numberofwindow_V 
9. Numberofwindow_3 
10. Numberofwindow_7 

**Insights:**

- Building characteristics such as size, type, and occupancy date are most predictive of claims. 
- Window-related features contribute slightly but are less important. 
- Older buildings and certain building types may have higher risk.

---

## Limitations & Next Steps

- **Class imbalance** affects minority class (Claim = 1) prediction. 
- Some features are weakly correlated with the target. 
- **Future improvements:**
  - Apply oversampling techniques (e.g., SMOTE) 
  - Try boosting models (XGBoost, LightGBM) 
  - Feature engineering to create aggregated metrics (e.g., total windows, age of building) 

---

## How to Run

1. Clone this repository: 
```bash
git clone <https://github.com/PreciousUzoka-Analyst/Insurance-claim-prediction.git>

# Note: Due to GitHub file size limits, the dataset is not included in the repository. The notebooks assume the data is placed in the data/folder as described.