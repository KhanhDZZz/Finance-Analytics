# Finance Analytics

## Notebook Overview
The notebook `Notebook/Finance Analytics.ipynb` performs a complete investment customer analytics workflow. It connects to a local SQL Server database, loads the `Finance_data` and `Original_data` tables, explores the data, generates visualizations, builds churn risk features, trains models, evaluates results, and segments customers by risk.

## Purpose
This notebook is designed to:
- Analyze investment customer behavior and demographics
- Evaluate investment preferences and participation trends
- Derive churn risk indicators and engagement features
- Train and compare predictive models for churn risk
- Identify customer segments with high, medium, and low churn probability
- Export actionable results for operational use

## Actions in the Notebook
1. Environment setup
   - Installs required Python packages
   - Imports `pandas`, `numpy`, `matplotlib`, `seaborn`, and scikit-learn modules

2. Database connection and data loading
   - Connects to SQL Server using `pyodbc`
   - Reads `Finance_data` and `Original_data` tables
   - Reports dataset shape and feature counts

3. Data inspection and quality assessment
   - Prints dataset shape, column types, and summary statistics
   - Checks for missing values
   - Inspects distribution of demographic fields and investment flags

4. Exploratory analysis
   - Demographic analysis for gender and age
   - Investment participation analysis for general investment avenues and stock market investing
   - Average ranking of investment products and first-choice preference counts
   - Analysis of investment characteristics such as objective, purpose, duration, monitoring frequency, expected returns, information source, and savings goals
   - Review of reasons for selecting equity, mutual funds, bonds, and fixed deposits

5. Visualization
   - Creates six charts showing customer demographics, investment participation, rank preferences, and monitoring frequency
   - Displays gender distribution, age distribution, investment participation, stock market investment, avenue ranking, and monitoring behavior

6. Feature engineering
   - Creates a churn risk target and engagement metrics
   - Defines `investment_count`, `low_diversity`, and `engagement_score`
   - Derives `is_churn_risk` from stock market participation, overall investment participation, and monitoring frequency

7. Model training and evaluation
   - Encodes categorical features using `LabelEncoder`
   - Prepares a feature matrix and target labels
   - Splits data into training and test sets
   - Scales numeric features with `StandardScaler`
   - Trains Logistic Regression and Random Forest models
   - Compares model performance using AUC-ROC and selects the best model

8. Model performance reporting
   - Computes accuracy, precision, recall, F1-score, and AUC-ROC
   - Prints classification report and confusion matrix
   - Visualizes performance with confusion matrix, ROC curve, metrics bar chart, and feature importance for the Random Forest model

9. Customer churn risk segmentation
   - Predicts churn probability for all customers
   - Segments customers into high, medium, and low risk groups
   - Reports segment counts and typical characteristics of each risk group
   - Visualizes churn risk distribution, probability histogram, age distribution by risk, and investment participation by risk level

10. Export results
    - Prepares an export dataset with demographic fields, engagement metrics, predicted churn risk, and risk segment labels
    - Prints a summary of exported records and sample high-risk customers

## Key Results
- Descriptive summary of investment customer profiles
- Visual charts for demographics and investment behavior
- Churn risk model evaluation and selected best model
- Segmented customer risk groups for targeted action
- Export-ready dataset for follow-up analysis or operational campaigns

## How to use this project
1. Open `Notebook/Finance Analytics.ipynb` in Jupyter or VS Code.
2. Run the notebook cells sequentially.
3. Review the generated analysis, visualizations, and model evaluation metrics.
4. Use the exported customer segmentation output for decision-making or further analysis.
