
![](https://api.visitorbadge.io/api/visitors?path=https%3A%2F%2Fgithub.com%2FAklimaRimi%2FReal-time-Loan-Default-Dataset-Analysis-and-Prediction&label=watched&countColor=%23ff8a65)
<h1><Center>Loan Default Classification Dataset Analysis & Prediction Project</Center></h1>

**Developers: Aklima Akter Rimi, MD. Ismail Hasan Tanjer**

## Overview
This project helps banks and financial institutions decide whether to approve or reject loan applications. By using machine learning and big data tools, we make the process faster, more accurate, and data-driven. We leverage Databricks, Kafka, and Power BI to handle large amounts of loan data in real time and present useful insights visually.

---

## Introduction

### Why This Matters
Traditional loan approval processes can be slow and inaccurate, leading to financial risks. This project introduces a smarter way to analyze loan applications using data and machine learning to improve decision-making.

### Goals

- Build an efficient system to analyze loan data.
- Process and clean data for better insights.
- Test and compare machine learning models for loan approval predictions.
- Visualize key trends using Power BI.

---

## Literature Review
We reviewed studies on loan risk analysis, the role of machine learning in finance, and the impact of real-time data processing to establish a solid foundation for our project.

---

## Methodology

### How It Works
1. **Data Collection**: Gather loan-related data, including income, credit score, and loan amount [Dataset](https://www.kaggle.com/datasets/yasserh/loan-default-dataset).
2. **Data Processing**: Clean the data by handling missing values and selecting relevant features.
3. **Model Selection**: Evaluate different machine learning models (Logistic Regression, Random Forest, and Gradient Boosting) to determine the best performer.
4. **Real-Time Predictions**: Utilize Kafka to process loan applications instantly.
5. **Data Visualization**: Use Power BI to create interactive charts and dashboards.
6. **Integration**: Connect all tools using Databricks for smooth workflow and scalability.
7. **Code Implementation:** [Code](https://github.com/AklimaRimi/Real-time-Loan-Default-Dataset-Analysis-and-Prediction/tree/main/Scripts)

---

## ETL and Machine Learning Summary

### Dropped Columns
- The columns `'ID'` and `'year'` were removed as they were not relevant for modeling.  
- The `'age'` column was also dropped after being split into two separate features: `'Age_range_1'` and `'Age_range_2'`.  

### Handling Null Values
- Null values in key numerical columns (e.g., interest rate, upfront charges) were replaced with `0` using a coalescing function. We don't want to fill the null values with mean interest. 
- A null count analysis was performed to identify missing values before handling them.  

### Feature Creation
- The `'age'` column was split into two new features, `'Age_range_1'` and `'Age_range_2'`, to better represent age groups.  
- Other transformations and conversions were applied to ensure consistent data formatting.  

### Feature Selection
- Numerical columns were explicitly converted to `DOUBLE` for compatibility with machine learning models.  
- Categorical columns were converted to `STRINGNDEXER` to handle them appropriately in the pipeline.  


### Model Training
- Three machine learning models were trained:  
  - **Logistic Regression**  
  - **Random Forest Classifier**  
  - **Gradient Boosted Trees (GBT) Classifier**  

### Best Model and Accuracy
- **Logistic Regression** was identified as the best-performing model based on accuracy.  
- The exact accuracy for this dataset using Logistic Regression model is  `100%`.

  
---

## Design & Architecture

This is our final Architecture. This project is created based on these steps.

![](https://github.com/AklimaRimi/Real-time-Loan-Default-Dataset-Analysis-and-Prediction/blob/main/Screenshot%202025-02-22%20124929.png)


---

## Data Insights & Visualizations
### **Key Insights**

**Loan Approvals:** 36.64K loans approved.

**Property & Occupancy:** 93% of loan-backed properties belong to a single occupancy type.

**Loan Type Trends:** Type 1 and 3 receive higher amounts; Type 2 is lower.

**Security Preference:** Direct security-backed loans dominate, suggesting they’re lower risk.

**Loan Purpose:** p1 and p3 have the most interest.

**Income & Gender:** Joint applicants have the highest income; males and females are fairly balanced.

**Credit Score & Age:** Older applicants have higher credit scores; younger ones may struggle with approvals.
![Rimi's Dashboard](https://github.com/AklimaRimi/Real-time-Loan-Default-Dataset-Analysis-and-Prediction/blob/main/PowerBI/Screenshot%202025-02-26%20190906.png)

---

## Conclusion

### Summary
This project successfully integrates big data, machine learning, and visualization to enhance loan approval processes. By using Databricks, Kafka, and Power BI, we ensure real-time predictions and efficient data processing. Future improvements will focus on increasing model accuracy and incorporating additional data sources for better decision-making.

