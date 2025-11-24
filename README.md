1. Project Summary

This repository contains a fully reproducible data-analytics pipeline for processing, transforming, and analyzing FitBit Fitness Tracker Daily Activity Data.
The objective is to conduct high-resolution behavioral analytics, quantify activity intensities, explore caloric expenditure relationships, and validate correlations through statistically sound methodologies.

The analysis follows a structured approach integrating data engineering, feature construction, exploratory data analysis (EDA), and time-series granularity enhancement.

2. Dataset Description (https://www.kaggle.com/datasets/arashnic/fitbit?resource=download)

The dataset includes multiple CSV files capturing different aspects of user activity. Below is the description in text form:
dailyActivity_merged.csv — Contains aggregated daily user metrics such as total steps, distances, sedentary minutes, active minutes, calories burned.
dailyCalories_merged.csv — Stores day-wise calorie expenditure per user.
dailyIntensities_merged.csv — Provides intensity categorization of daily activity: sedentary, lightly active, fairly active, very active minutes.
dailySteps_merged.csv — Tracks total step count per day for each user.
dailySleep_merged.csv — Records sleep duration, sleep efficiency, total sleep time per user per day.
heartrate_seconds_merged.csv — Stores second-by-second heart-rate readings (high resolution).
weightLogInfo_merged.csv — Includes manually logged weight, BMI, and body fat percentage.
hourlyIntensities_merged.csv — Hour-wise activity intensity distribution.
hourlySteps_merged.csv — Hour-wise step count readings.
hourlyCalories_merged.csv — Hour-wise calorie burn distribution.
minuteCalories_merged.csv / minuteIntensity_merged.csv / minuteSteps_merged.csv — Minute-level activity trends.
minuteSleep_merged.csv — Minute-level sleep state tracking.

3. Data Preprocessing & Quality Engineering

The preprocessing pipeline includes:

a)Schema validation & structural sanity checks
b)Datetime standardization (tz normalization, timestamp parsing)
c)Deduplication across multi-granular logs
d)Outlier detection using IQR, z-score, quantile clipping
e)Handling missing values via interpolation & domain-aware imputation
f)Aggregation of minute-level and hourly-level features into daily summaries
g)Normalization and scaling for metric comparability
h)Creation of engineered features (activity ratios, slh)eep efficiency, MET-weighted intensity score)

4. Exploratory Data Analysis (EDA)

The EDA evaluates:
a)Activity-sleep correlations
b)Activity-calorie expenditure response curves
c)Temporal patterns (hourly, weekly, circadian trends)
d)Sedentary behavior clusters
e)Anomalies in heart-rate time series
f)User-level segmentation (K-means, hierarchical clustering)
g)Visualizations include:
h)Box plots, KDE distributions, histograms
i)Heatmaps for correlation profiling
j)Time-series line plots for movement and sleep cycles
k)Activity fragmentation graphs
l)Pairwise scatter-matrix for behavioral grouping

5. Statistical Modeling & Feature Computation

The analysis applies:
Pearson and Spearman correlation coefficients
Linear regression for calorie burn prediction
ANOVA tests for comparing user-type groups
Rolling averages and seasonal decomposition
Energy expenditure estimation based on MET scaling
Sleep efficiency scoring model
These statistical approaches allow reliable interpretation of fitness behavior vs. physiological response.

6. Predictive Modeling (Optional Extensions)

A lightweight predictive pipeline can be built using:
Random Forest Regressor for calorie prediction
XGBoost for activity-intensity classification
LSTM models for multi-step time-series forecasting (heart rate / steps)
Feature sets include engineered metrics such as:
MET-integrated active minutes
Sleep fragmentation index
Hourly variability score

7. Technologies & Libraries

Python
NumPy, Pandas
Matplotlib, Seaborn, Plotly
Scikit-learn
Statsmodels
SciPy
Jupyter / Google Colab
