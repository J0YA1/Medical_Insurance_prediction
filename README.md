# Medical Insurance Cost Prediction

## Project Overview

This project aims to predict medical insurance charges based on an individual's demographic and health-related information. The objective is to build a machine learning regression model that can estimate insurance costs using features such as age, BMI, smoking status, region, sex, and number of children.

---

## Dataset Description

The dataset contains the following features:

| Feature | Description |
|----------|-------------|
| age | Age of the primary beneficiary |
| sex | Gender of the beneficiary |
| bmi | Body Mass Index |
| children | Number of dependents covered by health insurance |
| smoker | Whether the beneficiary is a smoker or not |
| region | Residential area in the US |
| charges | Individual medical insurance cost (Target Variable) |

---

## Exploratory Data Analysis (EDA)

Several exploratory data analysis techniques were performed to understand the dataset and identify important patterns.

### Data Inspection

- Checked dataset shape and structure.
- Examined data types of each feature.
- Verified the presence of missing values.
- Generated descriptive statistics for numerical features.

### Univariate Analysis

- Analyzed the distribution of:
  - Age
  - BMI
  - Children
  - Charges
- Identified skewness in the target variable (charges).

### Categorical Analysis

- Examined frequency distributions for:
  - Sex
  - Smoker
  - Region

### Bivariate Analysis

- Investigated relationships between features and insurance charges.
- Compared insurance charges across:
  - Smokers vs Non-Smokers
  - Different regions
  - Gender categories

### Correlation Analysis

- Generated a correlation matrix for numerical features.
- Identified important factors influencing insurance charges.

### Key Insights

- Smoking status has a significant impact on insurance charges.
- Higher BMI values tend to be associated with higher medical expenses.
- Age shows a positive relationship with insurance costs.
- Region and sex have comparatively smaller impacts on charges.

---

## Data Preprocessing

### Categorical Encoding

The following categorical features were converted into numerical format using **One-Hot Encoding**:

- sex
- smoker
- region

This transformation created binary columns for each category while preserving information and avoiding ordinal relationships.

### Example

| smoker |
|----------|
| yes |

After One-Hot Encoding:

| smoker_no | smoker_yes |
|------------|------------|
| 0 | 1 |

---

## Model Selection

Several regression algorithms can be used for insurance cost prediction. For this project, **XGBoost Regressor** was selected because of its ability to handle complex non-linear relationships and provide high predictive performance.

### Model Used

```python
XGBRegressor(
    objective='reg:squarederror',
    n_estimators=100,
    learning_rate=0.1,
    max_depth=3,
    random_state=42
)
