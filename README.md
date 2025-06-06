# Bangalore-House-Price-Outlier-Analysis-EDA
📌 Project Title
Bangalore House Price Outlier Analysis and Exploratory Data Analysis (EDA)

🎯 Objective
The objective of this project is to perform:

Basic EDA (Exploratory Data Analysis)

Detect and handle outliers in the price_per_sqft column using multiple statistical methods

Visualize the effect of outlier handling using boxplots and histograms

Analyze skewness and kurtosis before and after data transformations

Examine relationships between variables using scatter plots and correlation heatmaps

📁 Dataset
The dataset contains property listings from Bangalore with fields like:

location

size (e.g., "2 BHK", "4 Bedroom")

total_sqft

bath

price

bhk (number of bedrooms)

price_per_sqft (calculated as price / total_sqft × 100000)

📎 Note: Sample dataset provided for understanding, use actual .csv file in implementation.

🛠️ Tools Used
Python

Pandas

NumPy

Matplotlib

Seaborn

SciPy

✅ Project Steps
1️⃣ Basic EDA
Loaded the dataset

Displayed basic info and summary statistics

Checked for null values

Derived new columns (e.g., price_per_sqft)

Cleaned size to extract numerical BHK values

2️⃣ Outlier Detection & Removal
Outliers in price_per_sqft were handled using the following methods:

a) Mean & Standard Deviation
Outliers = values beyond mean ± 2*std

b) Percentile Method
Trimmed data below 5th percentile and above 95th percentile

c) IQR Method
Removed values outside Q1 - 1.5*IQR and Q3 + 1.5*IQR

d) Z-Score Method
Used zscore() from scipy.stats

Dropped rows where Z > 3 or Z < -3

✅ Each method was followed by a box plot to visualize effectiveness.

3️⃣ Visualizations
📦 Box Plots
To visually assess the effectiveness of outlier handling for each method

📊 Histogram & Distribution Plots
Used sns.histplot() before and after transformation

Applied log transformation if data was highly skewed

Compared skewness and kurtosis before and after transformation

4️⃣ Correlation Analysis
🔥 Heatmap
Created heatmap using sns.heatmap() to show correlation between numerical features

🔍 Scatter Plots
Compared price_per_sqft with:

size

total_sqft

bhk

bath

📉 Key Observations
Raw data had extreme outliers in price_per_sqft, especially from luxury listings

IQR method was most balanced for outlier removal based on visual inspection

Data was positively skewed; log transformation helped normalize the distribution

Strong correlation observed between total_sqft and price, but not perfect linearity due to price per area variation

Heatmaps and scatter plots helped highlight meaningful relationships between variables

📦 Final Output
A cleaned dataset with significantly fewer outliers

Better distribution of price_per_sqft for downstream tasks like ML modeling

Visualizations for comparison between raw and processed data
