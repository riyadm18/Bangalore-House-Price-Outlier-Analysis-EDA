# 🏡 Bangalore House Price Outlier Analysis & EDA

## 📌 Project Title
**Bangalore House Price Outlier Detection, Cleaning & Exploratory Data Analysis**

## 🎯 Objective

This project aims to:
- Perform **Exploratory Data Analysis (EDA)** on Bangalore housing data.
- Detect and handle **outliers** in the `price_per_sqft` column using statistical techniques.
- Visualize data distributions using **boxplots**, **histograms**, and **scatter plots**.
- Apply data transformation to address **skewness and kurtosis**.
- Explore relationships between variables using **correlation heatmaps**.

## 📂 Dataset

- **Original Dataset**: `house_price.csv`
- **Cleaned Dataset**: `house_price_cleaned.csv`

Each row represents a residential property listing in Bangalore.

### 📋 Features:
- `location`: Area or region in Bangalore
- `size`: Property size label (e.g., "2 BHK", "4 Bedroom")
- `total_sqft`: Total built-up area in square feet
- `bath`: Number of bathrooms
- `price`: Price of the property (in Lakhs)
- `bhk`: Number of bedrooms (extracted from `size`)
- `price_per_sqft`: Derived column = `(price / total_sqft) × 100000`

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- SciPy
- Jupyter Notebook

## ✅ Project Steps

### 1️⃣ Data Loading & EDA
- Loaded data from `house_price.csv`
- Explored the shape, info, null values, and distributions
- Derived `bhk` and `price_per_sqft` from raw columns

### 2️⃣ Outlier Detection Methods
Applied on `price_per_sqft`:
- **Mean ± 3*Standard Deviation**
- **Percentile Method** (trim below 5th and above 95th percentile)
- **IQR Method** (Q1 - 1.5×IQR to Q3 + 1.5×IQR)
- **Z-Score Method** (values where z > 3)

### 3️⃣ Outlier Removal Techniques
- Used **trimming** and **capping** methods
- Removed/limited extreme `price_per_sqft` values to reduce noise

### 4️⃣ Visualizations
- Used **boxplots** to compare data before and after each outlier removal technique
- Used **histograms** and **distplots** to check for normality
- Applied **log and Box-Cox transformation** to handle skewness

### 5️⃣ Correlation Analysis
- Generated a **heatmap** of numeric features
- Created **scatter plots** of:
  - `size` vs `price_per_sqft`
  - `total_sqft` vs `price_per_sqft`
  - `bath` vs `price_per_sqft`
  - `bhk` vs `price_per_sqft`

## 📉 Key Observations

- Significant outliers in the dataset from high-end listings
- The **IQR method** was most effective for balanced outlier removal
- The dataset was positively skewed and benefited from transformation
- Variables like `bhk`, `bath`, and `total_sqft` show a positive correlation with `price_per_sqft`

## 📊 Output

- Cleaned and transformed dataset: `house_price_cleaned.csv`
- Visual evidence (boxplots, histograms, scatter plots) of data cleaning
- Ready for ML models with reduced noise and outliers
