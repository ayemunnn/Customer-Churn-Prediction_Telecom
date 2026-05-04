# Customer Churn Prediction Documentation

This document explains the notebook in simple language. The notebook itself now keeps only the code so it is easier to read, run, and edit.

## What this project does

The project predicts whether a telecom customer is likely to leave the company. This is called **churn prediction**.

The workflow is:

1. Load the customer dataset.
2. Inspect the data structure.
3. Clean missing or incorrect values.
4. Explore patterns with charts.
5. Convert the data into a machine-learning-friendly format.
6. Train multiple models.
7. Compare their performance.

## Files used

- Notebook: `customer-churn-prediction.ipynb`
- Dataset: `WA_Fn-UseC_-Telco-Customer-Churn.csv`

## Step-by-step explanation

## 1. Import libraries

The first cells import the tools used in the project:

- `pandas` and `numpy` for working with data
- `matplotlib`, `seaborn`, `plotly`, and `missingno` for charts
- `scikit-learn` for preprocessing, splitting data, training models, and measuring accuracy

## 2. Load the data

The notebook reads the churn CSV file into a dataframe called `df`.

This dataframe is the main table used throughout the notebook.

## 3. Understand the data

The notebook checks:

- the first few rows with `df.head()`
- the number of rows and columns with `df.shape`
- column names and data types with `df.info()`, `df.columns.values`, and `df.dtypes`

This helps confirm what kind of information is available before cleaning or modeling.

## 4. Check missing values

The notebook uses `missingno` to visualize missing data and also checks for hidden missing values.

One important fix is applied to `TotalCharges`:

- it is converted to numeric
- invalid blank values become missing values

## 5. Clean and prepare the data

Several cleaning steps are done:

- `customerID` is removed because it is just an identifier
- rows with `tenure == 0` are removed
- missing `TotalCharges` values are filled with the column mean
- `SeniorCitizen` is converted from `0/1` into `No/Yes`

The notebook also looks at summary statistics for the numeric columns:

- `tenure`
- `MonthlyCharges`
- `TotalCharges`

## 6. Explore the data visually

The notebook creates charts to understand churn patterns.

Examples of questions explored:

- How many customers churned?
- Does churn change by gender?
- Does contract type affect churn?
- Does payment method affect churn?
- Are customers with dependents or partners less likely to churn?
- Does internet service type affect churn?
- Are higher monthly charges linked to churn?
- Are newer customers more likely to leave?

These plots help identify possible churn signals before model training.

## 7. Encode the data for machine learning

Machine learning models need numbers, not text labels.

The helper function `object_to_int()` converts text columns into numeric labels using `LabelEncoder`.

After that:

- `X` stores the input features
- `y` stores the target column `Churn`

## 8. Split the data

The dataset is split into:

- training data: used to teach the model
- test data: used to check how well the model performs on unseen examples

The notebook uses a 70/30 split and keeps the churn ratio balanced with `stratify=y`.

## 9. Scale numeric columns

The numeric columns are standardized using `StandardScaler`.

This means values are adjusted to a common scale so some models can learn more effectively.

The scaled columns are:

- `tenure`
- `MonthlyCharges`
- `TotalCharges`

## 10. Train and compare models

The notebook trains several classification models:

- K-Nearest Neighbors
- Support Vector Machine
- Random Forest
- Logistic Regression
- Decision Tree
- AdaBoost
- Gradient Boosting
- Voting Classifier

For each model, the notebook predicts churn on the test set and prints performance results.

## 11. Evaluate performance

The notebook uses metrics such as:

- accuracy
- classification report
- confusion matrix
- ROC curve

These help answer:

- how many predictions were correct
- how well the model finds churn cases
- where the model makes mistakes

## Notes about the cleaned notebook

The notebook was simplified to make it easier to maintain:

- explanatory markdown cells were removed
- code comments were removed
- outputs were cleared to reduce file size
- the dataset path was updated to use the local CSV file in this folder
- unused imports were reduced

## Quick reading of the business meaning

The analysis suggests churn is strongly related to factors such as:

- contract type
- internet service type
- monthly charges
- support or security services
- customer tenure

In simple terms, customers are more likely to leave when their plan or service experience is less stable or less satisfying.

## How to use the notebook

1. Open `customer-churn-prediction.ipynb`.
2. Make sure the CSV file is in the same folder.
3. Run the cells from top to bottom.
4. Review the charts and model results.

## Final idea

This notebook is a full churn prediction pipeline:

- data loading
- cleaning
- exploration
- preprocessing
- model training
- evaluation

The code is now separated from the explanation so it is easier to read in both places.
