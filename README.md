## Dataset
The dataset used in this project is publicly available. You can download it from the following link:

[Kaggle - Bengaluru Housing Data](https://www.kaggle.com/Bengaluru_House_Data.csv)

# Dataset Overview
The dataset used in this project focuses on real-world housing prices in Bengaluru, India. It was selected for its complexity, providing an opportunity to apply data science techniques such as data cleaning, exploration, and feature engineering. The dataset presented challenges, including missing values, logical errors, and outliers, making it ideal for testing real-world data science workflows.

# real-estate-price-prediction-bengaluru
A machine learning project predicting Bengaluru housing prices using Python. Includes data cleaning, EDA, feature engineering, dimensionality reduction, one-hot encoding, and regression modeling. Techniques: K-Fold, GridSearchCV, ShuffleSplit. Libraries: NumPy, pandas, matplotlib, scikit-learn.

## Key Steps
1. **Exploratory Data Analysis (EDA)**.
  i begin by exploring the structure,summary and analyze dataset features of the dataset to understand its contents and identify potential issues.
  i made a function to visualize to me "Total square feet " by "location" by passing to it dataset and location
3. **Data Cleaning**: 
  i begin with removing irrelevant columns does not that are not required to build our model and does not directly impact the model’s algorithms.
  i remove irrelevant rows with missing values that could affect the quality of the data. to ensure that data is clean and relevant for analysis and modeling phases
  i made a function to aplly it on column "total_sqft" because there is some values in form of range so this function get average for this range rather than renoving these record.
  i'll remove outliers by ensuring each bedroom has at least 300 sqft, as typically a 2 BHK apartment should be a minimum of 600 sqft. i make this assumption
  i made a function that remove outlier based on its variance to remove outliers on a new columns that i made "price_per_square_feet"
  i observed that on same location and tsqf the 2 BHK is greater than 3 BHK so it is not logic,so i made a function called remove_bhk_outlier
  i removed outlier on apartment that has baths more than rooms.
5. **Feature Engineering**: Create new features
  Add new feature(integer) for bhk(Bedrooms,hall,kitchen),because the existing fetaure have had a varies syntax so i extract the number only from this columns and put in new feature called(BHK)
  Add new feature called "price per square feet" for some analysis will help me to remove logical errors
  **Dimensionality Reduction:** on "location"Any location having less than 10 data points should be tagged as "other" location. it will help me to reduce number of columns when making dummy columns
   
6. **Modeling**: 
   train regression models using scikit-learn.
   i used a regression model in this project because the goal is to predict continuous values
   during exploratory data analysis, i examined the nature of the target variable (housing price) and the relationship between it and the other features (like area, location,etc.).
8. **Model Evaluation**: .
   lr_model.score(X_test,y_test)
   Optimize model using K-Fold cross-validation and GridSearchCV to make descison which one is best for this situation i maje grid search between(linear,lasso,decisiontree)
10. **Prediction**: Predict housing prices
