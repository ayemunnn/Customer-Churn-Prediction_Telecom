# Customer Churn Prediction

This project predicts whether a telecom customer is likely to leave the company. The notebook walks through the full machine learning workflow: loading customer data, cleaning it, exploring churn patterns, training several classification models, and comparing their performance.

## Project Files

- `customer_churn_prediction.ipynb` - main Jupyter notebook with the churn prediction pipeline
- `Telcom_df.csv` - telecom customer churn dataset used by the notebook
- `customer-churn-prediction-documentation.md` - plain-language explanation of the notebook

## What The Notebook Does

1. Imports data science and machine learning libraries.
2. Loads the telecom churn dataset from `Telcom_df.csv`.
3. Inspects columns, data types, missing values, and summary statistics.
4. Cleans the data by handling missing values and removing unnecessary columns.
5. Explores churn patterns using visualizations.
6. Converts categorical values into numeric values for machine learning.
7. Splits the data into training and test sets.
8. Scales numeric features.
9. Trains and compares multiple classification models.
10. Evaluates model performance with accuracy, reports, confusion matrices, and ROC curves.

## Models Used

The notebook trains several models, including:

- K-Nearest Neighbors
- Support Vector Machine
- Random Forest
- Logistic Regression
- Decision Tree
- AdaBoost
- Gradient Boosting
- Voting Classifier

## Main Churn Signals

The analysis focuses on customer and service factors such as:

- contract type
- tenure
- monthly charges
- internet service type
- payment method
- online security, backup, and support services
- partner and dependent status

## Requirements

Install the common Python data science packages before running the notebook:

```bash
pip install pandas numpy matplotlib seaborn plotly missingno scikit-learn
```

## How To Run

1. Open `customer_churn_prediction.ipynb` in Jupyter Notebook, JupyterLab, or VS Code.
2. Make sure `Telcom_df.csv` is in the same folder as the notebook.
3. Run the cells from top to bottom.
4. Review the charts and model evaluation results.

## Goal

The goal is to understand which customers are more likely to churn so the business can identify high-risk customers and take action to improve retention.
