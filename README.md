🏠 House Price Prediction Project
📌 Project Overview

This project focuses on predicting house prices using Linear Regression.
It includes a full data science pipeline:

Data loading

Data cleaning

Handling missing values

Outlier detection & treatment

Feature engineering

Data visualization (EDA)

Encoding categorical variables

Model training & evaluation

The goal is to build a reliable regression model that can estimate house prices based on different property features.

📊 Dataset Description

The dataset contains real estate information such as:

price → House price (target variable)

bedrooms

bathrooms

sqft_living

sqft_lot

floors

waterfront

view

condition

sqft_above

sqft_basement

yr_built

yr_renovated

street

city

statezip

country

date

🧹 Data Preprocessing
✔ Handling Missing Values

Dropped rows with null values.

Removed invalid zero values (e.g. price = 0, bedrooms = 0, bathrooms = 0).

✔ Outlier Treatment

Applied clipping to reduce extreme values:

sqft_living → max = 6000

sqft_basement → max = 2000

sqft_above → max = 5000

price → removed extreme high values

bedrooms → clipped to max = 7

bathrooms → normalized rare values and clipped to max = 4.25

📈 Exploratory Data Analysis (EDA)

Used visualizations to understand data patterns:

Heatmaps for correlation

Histograms for price distribution

Scatter plots (price vs features)

Bar plots for categorical relations

Libraries used:

matplotlib

seaborn

🧠 Feature Engineering
Feature Selection

Dropped weak or high-cardinality features:

street

country

date

yr_built

yr_renovated

condition

sqft_above

sqft_lot

Encoding

Applied One-Hot Encoding for categorical features:

city

statezip

pd.get_dummies(data, columns=["statezip", "city"])

🤖 Model Building
Algorithm Used

Linear Regression from scikit-learn

from sklearn.linear_model import LinearRegression

Training
model = LinearRegression()
x = data.drop(["price"], axis=1)
y = data["price"]
model.fit(x, y)

Model Accuracy (R² Score)
model.score(x, y)


Final Accuracy:

✅ 0.76 (76%)

📦 Technologies Used

Python

Pandas

NumPy

Matplotlib

Seaborn

Scikit-learn

📁 Project Structure
📦 House-Price-Prediction
 ┣ 📜 task.csv
 ┣ 📜 main.py / notebook.ipynb
 ┣ 📜 README.md

🎯 Objective

Build a clean, structured, and optimized regression model that can:

Predict house prices

Handle real-world noisy data

Apply proper feature engineering

Follow data science best practices

🚀 Future Improvements

Train/Test split

Cross-validation

Try advanced models:

Random Forest

XGBoost

Gradient Boosting

Feature scaling

Model comparison

Deployment (Streamlit / Flask API)
