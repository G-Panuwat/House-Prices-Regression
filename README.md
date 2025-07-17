# Housing Prices Competition

This project is a machine learning solution for predict the sales price for each house, based on data from the Kaggle competition: [Housing Prices Competition for Kaggle Learn Users](https://www.kaggle.com/competitions/home-data-for-ml-course/).

## 📚 Overview

The notebook walks through the full machine learning pipeline:

- Data loading and exploration
- Data cleaning and preprocessing
- Feature engineering
- Model training using various algorithms
- Model evaluation
- Submission file generation

## 🛠️ Technologies Used

- Python 3
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

## 📁 Dataset

- `train.csv` and `test.csv` from the Titanic dataset available on Kaggle.
- Make sure to download the dataset from [here](https://www.kaggle.com/competitions/home-data-for-ml-course/data) and place it in the same directory as the notebook.

## Methodology

### 1. Download Acquisition
  - Dataset Download: The dataset for this project was obtained from [Housing Prices Competition for Kaggle Learn Users](https://www.kaggle.com/competitions/home-data-for-ml-course/).
### 2. Exploratory Data Analysis (EDA) and Data Cleaning
  - Initial Data Exploration: Conducted simple exploratory data anaylsis to understand the dataset's structure, distribution (mean, median, standard deviation, etc.).
  - Outlier Detection and Handling: Identified and addressed outliers that could impact to model performance, since there are small amount of instances. The data was visualized with scatterplot to determine the impactful outliers.
### 3. Feature Engineering
  - Feature Extraction: Transformed raw features and created new, more informative features to enhance the model prediction. This involved:
    - 'House_age' feature was extracted from year gap between year sold and year built.
    - 'houseremodelage' feature was built from year gap between year sold and remodel date.
    - 'totalsf' is total floor area in square feet, was extracted by accumulate all house floors (e.g., 1Floor, 2Floor, Basement floor)
    - 'totalarea' was created by summing living area in ground level and basement in square feet.
    - 'totalbaths' is total bathroom in one house.
    - 'totalporchsf' was extracted by summing all type porch's area in square feet.
### 4. Feature Preprocessing
  - Encoding Features:
    - One-Hot Encoding: Applied to nominal categorical features such as 'MSZoning', 'Street', 'LotConfig', 'Neighborhood', 'Condition1', 'Condition2', 'BldgType', 'HouseStyle', 'RoofStyle', 'RoofMatl', 'Exterior1st', 'Exterior2nd', 'MasVnrType','Foundation','Heating','CentralAir','Electrical','Functional','GarageType','PavedDrive','SaleType', and 'SaleCondition'.
    - Ordinal Encoding: Applied to ordinal catergorical features such as 'LotShape', 'LandContour', 'Utilities', 'LandSlope','ExterQual','ExterCond','BsmtQual','BsmtCond','BsmtExposure','BsmtFinType1','HeatingQC','KitchenQual','FireplaceQu','GarageFinish', and 'GarageQual'.
    - Impute NaN values to number features with categorical with most frequent value.
### 5. Data Pipeline Construction
  - Automated Workflow: A robust data preprocessing and feature engineering pipeline was built using scikit-learn's 'Pipeline'
### 6. Data Splitting
  - Train-Test Split: The dataset was split into training and testing sets (validation set)
    - The data was split into an 80% training set and a 20% testing set (validation set) using 'train_test_split' with 'random_state'.
### 7. Model Training and Hyperparameter Optimization
  - Model Selection: Explored and trained various machine learning models suitable for the problem.
    - Linear Regression, Ridge Regression, XGB Regressor, CatBoostRegressor, and ensemble models (Random Forest, Light Gradient Boosting, GradientBoosting, Voting Regressor, Stacking Regressor) 
  - Hyperparameter Optimization: Find the best-performing parameters for each model.
    - The given dataset is relatively small, Grid Search Optimization with 3 or 5 fold cross validation was chosen for its exhaustive search capability and robustness in finding optimal hyperparameters, mitigating overfitting to the training data.
### 8. Model Evaluation
  - Performance Assessment: The best-performing model was evaluated on the unseen test dataset.
    - The model was evaluated with Root Mean Squared Error (RMSE) to find the error between predicted value and observed sales price.
    - Results: The Ridge Regressor achieved a Root Mean Squared Error (RMSE) of 13222.33 on the original Kaggle test dataset. This performance placed it 65th out of over 5000 entries on the public leaderboard, putting it within the top ~1.3% of all submissions.
      
## 🚀 How to Run

1. Clone the repository or download the `.ipynb` file.
2. Download the Titanic dataset (`train.csv`, `test.csv`) from Kaggle and place them in the working directory.
3. Install the required Python libraries (if not already installed):

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
