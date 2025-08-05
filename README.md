# Big Mart Sales Prediction

## Overview

This project aims to predict the sales of various products at different Big Mart outlets. The dataset contains sales data for 1559 products across 10 outlets in different cities. The goal is to build a predictive model that can help Big Mart understand the factors affecting sales and predict future sales.

## Dataset

The dataset used in this project is `train.csv`. It contains the following features:

*   `Item_Identifier`: Unique product ID
*   `Item_Weight`: Weight of the product
*   `Item_Fat_Content`: Fat content of the product (Low Fat, Regular, etc.)
*   `Item_Visibility`: The percentage of total display area of all products in a store allocated to the particular product
*   `Item_Type`: The category to which the product belongs (Dairy, Soft Drinks, etc.)
*   `Item_MRP`: Maximum Retail Price (list price) of the product
*   `Outlet_Identifier`: Unique store ID
*   `Outlet_Establishment_Year`: The year in which the store was established
*   `Outlet_Size`: The size of the store (Small, Medium, High)
*   `Outlet_Location_Type`: The type of city in which the store is located (Tier 1, Tier 2, Tier 3)
*   `Outlet_Type`: Whether the outlet is a grocery store or some sort of supermarket
*   `Item_Outlet_Sales`: Sales of the product in the particular store. This is the target variable to predict.

## Project Steps

The project follows a typical machine learning workflow:

1.  **Data Loading and Exploration:** Load the dataset and perform initial data exploration to understand its structure, features, and identify potential issues.
2.  **Data Cleaning and Preprocessing:** Handle missing values, inconsistencies, and transform categorical features into numerical representations suitable for modeling. This includes:
    *   Handling missing `Item_Weight` using KNN Imputer.
    *   Handling missing `Outlet_Size` (although in this notebook, it was shown to have no missing values).
    *   Standardizing `Item_Fat_Content` categories.
    *   Handling zero values in `Item_Visibility` using interpolation.
    *   Simplifying `Item_Identifier` to its first two characters.
    *   Encoding categorical features using Ordinal Encoding.
3.  **Feature Selection:** Analyze feature importances to identify the most relevant features for the prediction task. Based on the analysis, less important features were dropped.
4.  **Model Selection and Training:** Train different regression models to predict `Item_Outlet_Sales`. In this notebook, Random Forest Regressor and XGBoost Regressor were explored, with XGBoost showing slightly better performance. A Linear Regression model was also trained for comparison.
5.  **Model Evaluation:** Evaluate the performance of the trained models using appropriate metrics like R-squared and Mean Absolute Error (MAE). Cross-validation was used to assess the model's generalization ability.
6.  **Prediction:** Use the trained model to make predictions on new data.

## Code

The project code is written in Python using libraries like pandas, numpy, matplotlib, seaborn, and scikit-learn. The notebook includes steps for data loading, exploration, cleaning, feature engineering, model training, and evaluation.

## How to Run the Code

1.  Clone this repository to your local machine.
2.  Make sure you have the necessary libraries installed (`pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `xgboost`). You can install them using pip:
