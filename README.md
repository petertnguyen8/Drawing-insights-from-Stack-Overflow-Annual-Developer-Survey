# Drawing Insights from Stack Overflow 2024 Annual Developer Survey

## Project Overview

This project analyzes data from the **Stack Overflow 2024 Annual Developer Survey** to uncover business insights regarding developer demographics and compensation. Additionally, the project involves building and evaluating a supervised learning model to predict developer income in the United States based on specific professional attributes.

## Dataset

The analysis uses the official 2024 Stack Overflow survey data, which covers seven sections, including professional experience, education, and technology culture. For this specific project, the focus is restricted to:

* **Section 1:** Basic Information (e.g., Age, Country)
* **Section 2:** Education, Work, and Career (e.g., Organization Size, Professional Experience, Total Compensation)

**Data Source:** [Stack Overflow Survey Data](https://survey.stackoverflow.co/)

## Business Questions

The project addresses three primary objectives:

1. **Organization Demographics:** Identify the most common organization sizes among survey respondents.
2. **Compensation Trends:** Determine how organization size influences developer income.
3. **Predictive Modeling:** Develop a machine learning model to predict income based on 'Age', 'EdLevel' (Education Level), 'OrgSize' (Organization Size), and 'YearsCodePro' (Years of Professional Coding Experience) for developers in the US.

## Data Cleaning & Preparation

To ensure the accuracy of the predictive model, significant data preprocessing was performed:

* **Geographic Filtering:** The dataset was filtered to include only respondents from the **United States** to maintain consistency in currency (USD) and economic scaling.
* **Handling Missing Values:** Null entries in critical fields like compensation and experience were removed.
* **Outlier Removal:** Respondents reporting an annual compensation greater than **$500,000** were excluded as outliers to prevent model skewing.
* **Feature Engineering:** * The `YearsCodePro` field was converted from categorical strings (e.g., "Less than 1 year") to numerical values (e.g., 0.5) to enable regression analysis.
* Categorical variables like `Age`, `EdLevel`, and `OrgSize` were simplified through mapping to reduce dimensionality and improve model interpretability.



## Machine Learning Workflow

The project implements a supervised learning pipeline using **Scikit-Learn**:

* **Models Used:** `RandomForestRegressor`.
* **Evaluation Metrics:** The models were evaluated using **R-squared (R2)** and **Root Mean Squared Error (RMSE)**.
* **Validation Strategy:** The data was split into training and testing sets using `train_test_split`.

## Results & Reflections

The initial modeling phase revealed the following:

* **Overfitting:** The training R2 score was significantly higher than the test R2 score, indicating that the model did not generalize well to unseen data.
* **Model Accuracy:** Both R2 and RMSE values indicated room for significant improvement.
* **Next Steps:** Future iterations could involve hyperparameter tuning, feature selection, or exploring alternative algorithms to mitigate overfitting and improve predictive accuracy.

## Requirements

To run this notebook, the following Python libraries are required:

* `pandas`
* `numpy`
* `matplotlib`
* `seaborn`
* `scikit-learn`

## Acknowledgements & Licenses
Data Source: https://survey.stackoverflow.co/

Data licensed under Open Database License (ODbL). 

User contributions licensed under CC BY-SA.

Thank you to Udacity for guiding me through this project. 
Also to Stack Overflow for gathering and providing this dataset for developers to use.
