# Real Estate Price Prediction in Bengaluru

## Dataset
The dataset used in this project is publicly available. You can download it from the following link:

[Kaggle - Bengaluru Housing Data](https://www.kaggle.com/Bengaluru_House_Data.csv)

---

## Dataset Overview
This project utilizes a real-world dataset focusing on housing prices in Bengaluru, India. The dataset was selected due to its complexity, offering a chance to apply a variety of data science techniques such as data cleaning, exploratory data analysis, and feature engineering. The dataset posed challenges like missing values, logical errors, and outliers, which made it ideal for simulating real-world data science workflows.

---

## Project Overview
This project aims to predict housing prices in Bengaluru using machine learning techniques. The workflow includes data cleaning, exploratory data analysis, feature engineering, and regression modeling. The focus is on building a robust model while addressing the challenges presented by the dataset.

### Key Features:
- **Techniques:** Dimensionality reduction, one-hot encoding, K-Fold cross-validation, GridSearchCV, ShuffleSplit.
- **Libraries Used:** NumPy, pandas, matplotlib, scikit-learn.

---

## Key Steps

### 1. **Exploratory Data Analysis (EDA)**
- Examined the structure and summary of the dataset.
- Analyzed dataset features to understand contents and identify potential issues.
- Visualized relationships between key features, such as total square feet and location, to gain insights.

### 2. **Data Cleaning**
- Removed irrelevant columns and rows with significant missing values to maintain data quality.
- Addressed inconsistencies in the `total_sqft` column by converting range values into averages rather than discarding them.
- Eliminated outliers based on logical assumptions:
  - Ensured each bedroom had at least 300 square feet (e.g., 2 BHK apartments require a minimum of 600 square feet).
  - Created and utilized a new feature, `price_per_square_feet`, to identify and remove rows with abnormal price variances.
  - Filtered out rows where 2 BHK prices exceeded 3 BHK prices in the same location.
  - Removed rows where bathrooms exceeded the number of bedrooms by more than one.

### 3. **Feature Engineering**
- Added new features:
  - `BHK` (Bedrooms, Hall, Kitchen): Extracted integer values from the `size` column.
  - `price_per_square_feet`: Calculated to assist in identifying and handling outliers.
- Applied dimensionality reduction on the `location` column:
  - Grouped locations with fewer than 10 data points into a single category labeled as "other."

### 4. **Modeling**
- Trained regression models to predict housing prices based on the cleaned and processed dataset.
- Selected regression because the target variable (price) is continuous.
- Explored multiple regression models, including linear regression, lasso regression, and decision tree regression.
- Evaluated models using K-Fold cross-validation and optimized hyperparameters with GridSearchCV.

### 5. **Prediction**
- Created a function to predict housing prices based on input features such as location, total square feet, number of bathrooms, and BHK.

---

## Final Thoughts
This project showcases the end-to-end process of handling a real-world dataset, from cleaning and exploring the data to building and evaluating machine learning models. It highlights the practical challenges of working with real-world data and provides insights into developing solutions for robust predictive modeling.
