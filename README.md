# Anxiety or Depression Indicator Analysis and Prediction

## Project Overview
This project aims to analyze and predict the values of an **Anxiety or Depression Indicator** using machine learning models. The dataset includes features such as time period, confidence intervals, and geographical data. Our goal is to create a reliable predictive model for forecasting these indicator values, which could be beneficial for healthcare professionals and policymakers.

## Dataset Description
The dataset contains 16,092 rows and 14 columns. The key columns include:
- **Indicator**: Type of mental health issue (e.g., anxiety, depression).
- **State**: The geographical state where the data is collected.
- **Time Period**: The year in which the data was recorded.
- **Confidence Intervals**: Upper and lower bounds for the reported value.
- **Value**: The actual reported value of the mental health indicator.

## Workflow

### 1. Data Preprocessing
Data preprocessing is an essential step before modeling. Here's a breakdown of what was done:
- **Handling Missing Values**: Missing values were handled by dropping rows where essential values like `Value`, `Low CI`, and `High CI` were null.
- **Feature Selection**: Key features such as `Time Period`, `Low CI`, and `High CI` were selected based on their relevance to the target column (`Value`). These features were used as predictors for the model.
- **Encoding Categorical Variables**: Columns with categorical data (e.g., `State`, `Indicator`) were transformed into numerical representations using one-hot encoding.
- **Scaling**: Numerical features were scaled to ensure consistency and to help the models learn better.

### 2. Exploratory Data Analysis (EDA)
Before building models, it’s important to explore the data and understand its structure and relationships. Various visualizations were generated to help with this:
- **Correlation Heatmap**: This was used to visualize correlations between numerical variables such as `Value`, `Low CI`, and `High CI`.
- **Time Series Plots**: To show trends in the anxiety or depression indicator over time for different states.
- **Boxplots**: Illustrated the distribution of values across different states or subgroups, giving an idea of variation and spread.
- **Distribution Plots**: These plots helped us understand the overall distribution of the `Value` column.

### 3. Modeling
Three machine learning models were applied to predict the `Value` of the anxiety or depression indicator:
- **Linear Regression**: A simple linear approach that attempts to fit a straight line through the data.
- **Random Forest Regressor**: A tree-based ensemble model that aggregates predictions from multiple decision trees.
- **XGBoost Regressor**: A more sophisticated ensemble technique that uses gradient boosting to build a model sequentially.

Each model was trained on the preprocessed dataset and then evaluated using the test data.

### 4. Model Evaluation
To evaluate the performance of the models, two key metrics were used:
- **Mean Squared Error (MSE)**: A measurement of the average squared difference between predicted and actual values.
- **R-squared (R²)**: A statistical measure that explains how well the model fits the data. An R² close to 1 indicates a very good fit.

#### Model Results:
- **Linear Regression**: 
  - MSE: 0.0071
  - R-squared: 0.9999
- **Random Forest Regressor**: 
  - MSE: 0.0083
  - R-squared: 0.9999
- **XGBoost Regressor**: 
  - MSE: 0.0182
  - R-squared: 0.9998

### 5. Conclusion
All three models performed remarkably well, with very low MSE values and R-squared values close to 1. **Linear Regression** marginally outperformed the others, but all models were successful in predicting the anxiety or depression indicator accurately.



