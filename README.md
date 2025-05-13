# 🌍 Earthquake Data Analysis and Modeling

This project performs data cleaning, statistical analysis, visualization, and predictive modeling on global earthquake data. The work is structured across **three main code files**, each building upon the previous step for a complete data science pipeline.

---

## 📄 `part1.pdf` – Feature Selection & Descriptive Statistics

This script performs data preprocessing and basic statistical analysis on an earthquake dataset. The main operations include **feature selection**, **descriptive statistics**, **correlation analysis**, and a **summary overview**.

### ✅ Feature Selection
- Extracts specific features: `latitude`, `longitude`, `gap`, `nst`, `mag`, `depth`
- Saves them into `selected_features.csv` for streamlined analysis

### 📊 Descriptive Statistical Analysis
Calculates for each feature:
- Mean, Median, Mode
- Standard Deviation, Variance, Range

### 🔗 Correlation Matrix
- Computes Pearson correlation coefficients between selected features
- Helps identify inter-feature relationships (e.g., magnitude vs. depth)

### 🧾 Summary Statistics
Uses `.describe()` to generate:
- Count, Mean, Std, Min, Max, and Quartiles

### 📁 Output
- `selected_features.csv`
- Console outputs of statistics and correlation matrix

---

## 📊 `part2.ipynb` – Data Cleaning & Visualization

This notebook continues the pipeline by performing **exploratory data analysis (EDA)**, cleaning missing/duplicate values, and visualizing distributions and outliers.

### 🧹 Initial Data Inspection
- Loads `selected_features.csv`
- Displays shape, data types, summary stats, and unique values

### ❓ Null Value Analysis
- Counts and visualizes missing values using bar plots

### 📈 Feature Distribution Visualization
- Histograms of all selected features using `matplotlib`

### 🛠️ Handling Missing Values
Interactive menu to:
1. Impute with mean/median
2. Drop rows with nulls
3. Replace with constant value

Cleansed dataset saved as `selected_features_cleaned.csv`

### 🧼 Duplicate & Outlier Removal
- Removes duplicates and outliers using **Z-score**
- Saves:
  - `cleaned_data_without_duplicates.csv`
  - `cleaned_data_without_outliers.csv`

### 📉 Post-Cleaning Visuals
- Replots distributions
- Shows changes in row counts using bar charts

### 📁 Output Files
- Cleaned and filtered datasets for modeling

---

## 📈 `part3.ipynb` – Time Series Analysis & Prediction

This notebook focuses on **time-based insights**, **feature engineering**, and **predictive modeling** using linear regression.

### 🗂️ Data Preparation
- Loads full dataset `earthquakes_2023_global.csv`
- Parses date and handles nulls
- Adds `date_ordinal` for regression

### 🧠 Feature Engineering
- Extracts `day_of_week` and `month`
- Aggregates magnitudes daily

### 🔍 Seasonal Decomposition
- Decomposes time series into:
  - Trend
  - Seasonality
  - Residuals

### 📉 Autocorrelation Analysis
- Plots ACF and PACF to inspect time-based dependencies

### 🤖 Predictive Modeling
- Features: `date_ordinal`, `latitude`, `longitude`, `horizontalError`, `depthError`, `day_of_week`, `month`
- Target: `mag` (earthquake magnitude)
- Trains `LinearRegression` model and predicts on test set
- Evaluation:
  - MAE (Mean Absolute Error)
  - MSE (Mean Squared Error)

### 📌 Additional Visualizations
- Magnitude distribution (KDE + Histogram)
- Geospatial scatter plot (Longitude vs Latitude) colored by magnitude and sized by depth

---

## ✅ Conclusion

This 3-part project takes you from **raw earthquake data to cleaned datasets, rich visualizations, and predictive models**. The code is modular and extensible for deeper analytics or deployment.

