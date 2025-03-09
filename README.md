# Loan Default Analysis & Prediction Project

![](https://api.visitorbadge.io/api/visitors?path=https%3A%2F%2Fgithub.com%2FAklimaRimi%2FReal-time-Loan-Default-Dataset-Analysis-and-Prediction&label=watched&countColor=%23ff8a65)

## Overview
This project helps banks and financial institutions predict whether a loan will default. By using machine learning and big data tools, we make the process faster, smarter, and data-driven. We use Databricks, Kafka, and Power BI to handle large datasets in real time and present clear insights.

---

## Introduction

### Why This Matters
Traditional loan risk assessment methods can be slow and inaccurate, leading to financial losses. This project introduces a smarter way to analyze loan default risks using data and machine learning to improve decision-making.

### Goals
- Build an efficient system to analyze loan default risks.
- Process and clean data for better insights.
- Test and compare machine learning models for predicting loan defaults.
- Visualize key trends using Power BI.

---

## Design & Architecture

This project is structured with the following architecture:

![](https://github.com/AklimaRimi/Real-time-Loan-Default-Dataset-Analysis-and-Prediction/blob/main/Screenshot%202025-02-22%20124929.png)

---
## How It Works

1. **Collect Data**: Loan-related details (income, credit score, loan amount, etc.) [Dataset](https://www.kaggle.com/datasets/yasserh/loan-default-dataset).
2. **Process Data**: Handle missing values and refine key features.
3. **Select ML Models**: Compare Logistic Regression, Random Forest, and Gradient Boosting to find the best.
4. **Real-Time Prediction**: Use Kafka to process loan default risks instantly.
5. **Visualize Data**: Create easy-to-understand reports in Power BI.
6. **Integrate Everything**: Use Databricks for smooth workflow and scalability.
7. **Code Implementation:** [Code](https://github.com/AklimaRimi/Real-time-Loan-Default-Dataset-Analysis-and-Prediction/tree/main/Scripts)

---

## Key Insights

- **Loan Defaults**: 36.64K loans defaulted.
- **Property & Occupancy**: 93% of loan-backed properties belong to a single occupancy type.
- **Loan Type Trends**: Type 1 and 3 have higher default amounts; Type 2 defaults less.
- **Security Preference**: Direct security-backed loans have lower default rates.
- **Loan Purpose**: p1 and p3 have the most defaults.
- **Income & Gender**: Joint applicants have the highest income; males and females show balanced default rates.
- **Credit Score & Age**: Older applicants have higher credit scores; younger ones are more prone to defaults.

![Dashboard](https://github.com/AklimaRimi/Real-time-Loan-Default-Dataset-Analysis-and-Prediction/blob/main/PowerBI/Screenshot%202025-02-26%20190906.png)


---
## ETL Code Summary & Model Performance Analysis

## Data Preprocessing & Transformation

### 1. Data Cleaning & Feature Engineering
- Dropped irrelevant columns: `ID` and `year`.
- Extracted age ranges from the `age` column:
  - `Age_range_1` → Lower bound of the range.
  - `Age_range_2` → Upper bound of the range.
  - Dropped the original `age` column.

### 2. Data Type Conversion
- Defined numerical columns (`col_to_double`) and converted them to **DOUBLE**.
- Converted remaining categorical columns (`col_to_string`) to **STRING**.

### 3. Handling Missing Values
- Used `COALESCE` to replace NULL values in:
  - `rate_of_interest`, `Interest_rate_spread`, `Upfront_charges`, `dtir1` → Replaced with `0`.
- Removed remaining **NaN/NULL** values from the dataset.

---

## Feature Engineering & Model Optimization

### 4. Encoding Categorical Variables
- Loaded a **pre-trained `StringIndexerModel`** to encode categorical columns.
- Dropped original categorical columns after transformation.

### 5. Feature Selection & Vectorization
- **Dropped highly correlated columns** to prevent **overfitting**:
  - `rate_of_interest_`, `Upfront_charges_`, `Interest_rate_spread_`
  - Keeping these columns resulted in **100% accuracy**, which indicated overfitting.
  - Removing highly correlated features **prevented overfitting** and improved model generalization.
- Used `VectorAssembler` to create a single feature vector (`features`).
- Final dataset includes:
  - **`features`** → Feature vector for model input.
  - **`label`** → Renamed from `Status` for model training.

---

## Model Performance Comparison

| Model                 | Accuracy (%) |
|----------------------|--------------|
| **Gradient Boosting** | **87** (Best) |
| Logistic Regression  | **84** |
| Random Forest        | **83** |

- **Gradient Boosting provided the best results with 87% accuracy.**
- **Other models (Logistic Regression & Random Forest) also performed well but slightly lower than Gradient Boosting.**

---

## Conclusion
This project successfully integrates big data, machine learning, and visualization to improve loan default prediction. By leveraging Databricks, Kafka, and Power BI, we provide real-time predictions and better insights. Future improvements will focus on enhancing model accuracy and incorporating more data sources.



