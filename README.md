# Finance Analytics

## Notebook Overview
The notebook `Notebook/Finance Analytics.ipynb` performs a complete investment customer analytics workflow. It connects to a local SQL Server database, loads the `Finance_data` and `Original_data` tables, explores the data, generates visualizations, builds churn risk features, trains models, evaluates results, and segments customers by risk.

## Purpose
This notebook is designed to:
- analyze investment customer behavior and demographics
- evaluate investment preferences and participation trends
- derive churn risk indicators and engagement features
- train and compare predictive models for churn risk
- identify customer segments with high, medium, and low churn probability
- export actionable results for operational use

## Actions in the Notebook
1. Environment setup
   - installs required Python packages
   - imports `pandas`, `numpy`, `matplotlib`, `seaborn`, and scikit-learn modules

2. Database connection and data loading
   - connects to SQL Server using `pyodbc`
   - reads `Finance_data` and `Original_data` tables
   - reports dataset shape and feature counts

3. Data inspection and quality assessment
   - prints dataset shape, column types, and summary statistics
   - checks for missing values
   - inspects distribution of demographic fields and investment flags

4. Exploratory analysis
   - demographic analysis for gender and age
   - investment participation analysis for general investment avenues and stock market investing
   - average ranking of investment products and first-choice preference counts
   - analysis of investment characteristics such as objective, purpose, duration, monitoring frequency, expected returns, information source, and savings goals
   - review of reasons for selecting equity, mutual funds, bonds, and fixed deposits

5. Visualization
   - creates six charts showing customer demographics, investment participation, rank preferences, and monitoring frequency
   - displays gender distribution, age distribution, investment participation, stock market investment, avenue ranking, and monitoring behavior

6. Feature engineering
   - creates a churn risk target and engagement metrics
   - defines `investment_count`, `low_diversity`, and `engagement_score`
   - derives `is_churn_risk` from stock market participation, overall investment participation, and monitoring frequency

7. Model training and evaluation
   - encodes categorical features using `LabelEncoder`
   - prepares a feature matrix and target labels
   - splits data into training and test sets
   - scales numeric features with `StandardScaler`
   - trains Logistic Regression and Random Forest models
   - compares model performance using AUC-ROC and selects the best model

8. Model performance reporting
   - computes accuracy, precision, recall, F1-score, and AUC-ROC
   - prints classification report and confusion matrix
   - visualizes performance with confusion matrix, ROC curve, metrics bar chart, and feature importance for the Random Forest model

9. Customer churn risk segmentation
   - predicts churn probability for all customers
   - segments customers into high, medium, and low risk groups
   - reports segment counts and typical characteristics of each risk group
   - visualizes churn risk distribution, probability histogram, age distribution by risk, and investment participation by risk level

10. Export results
    - prepares an export dataset with demographic fields, engagement metrics, predicted churn risk, and risk segment labels
    - prints a summary of exported records and sample high-risk customers

## Key Results
- descriptive summary of investment customer profiles
- visual charts for demographics and investment behavior
- churn risk model evaluation and selected best model
- segmented customer risk groups for targeted action
- export-ready dataset for follow-up analysis or operational campaigns

## How to use this project
1. Open `Notebook/Finance Analytics.ipynb` in Jupyter or VS Code.
2. Run the notebook cells sequentially.
3. Review the generated analysis, visualizations, and model evaluation metrics.
4. Use the exported customer segmentation output for decision-making or further analysis.
