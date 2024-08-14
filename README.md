# Age Prediction Using Ensemble Learning
This project is designed to predict the age of individuals based on a dataset using various regression techniques and an ensemble model. The ensemble model includes several robust regression algorithms combined into a stacking regressor to improve the prediction accuracy.


## Data
The data consists of two CSV files: train.csv and test.csv. The training data includes features like id, Sex, Age, and other attributes. The target variable is Age, which we aim to predict using the test data.


## Pipeline Description
The code performs the following steps:


## Data Preprocessing: Loads the data, replaces certain values in the 'Sex' column, and encodes categorical data.
Feature Engineering: Generates polynomial features for the model to capture non-linear relationships.
Feature Selection: Uses Recursive Feature Elimination with Cross-Validation (RFECV) to select the most important features.
Model Training: Trains various regression models.
Ensemble Learning: Combines the regression models using a stacking approach.


## Modeling
The following regression models are used:

Linear Regression
Ridge Regression
Huber Regression
TheilSen Regression
RANSAC Regression
Each model is wrapped in a pipeline with a RobustScaler for data scaling.


## Feature Engineering
Polynomial features are generated from the original features to allow the model to capture more complex patterns in the data. The PolynomialFeatures transformer is used for this purpose with a degree of 2.


## Ensemble Model
A StackingRegressor is used to combine the predictions of the individual regression models. The final estimator in the ensemble is a HuberRegressor, which is less sensitive to outliers in the data.


## Output
The final predictions are adjusted slightly and rounded before being saved to a CSV file named final_test_wfd.csv. This file includes two columns:

id: The identifier for each test instance.
age: The predicted age for each test instance.


## Usage
Prepare Data: Place your training data in data/train.csv and test data in data/test.csv.
Run the Code: Execute the script using a Python environment:
Review Output: Check the final_test_wfd.csv file for the age predictions.


## Contributing
Contributions are welcome! Please open an issue to discuss your ideas or bug reports.