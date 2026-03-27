**Demand Factors Analysis for Yulu (Industry: Micro-mobility)**
This project explores Yulu's shared electric cycle transaction data to analyze how external factors such as weather, season, and working days influence the demand for their service.

**Project Overview**
Yulu is a leading micro-mobility service provider in India that has recently experienced a decline in revenue. The company aims to understand the key factors influencing the demand for its shared electric cycles in the Indian market to optimize service delivery and drive growth.

**Problem Statement**
Yulu has contracted a consulting firm to identify which variables are significant in predicting the demand for their shared electric cycles. The objective is to analyze potential variables—such as location, weather, time of day, and socio-economic conditions—to determine their impact on usage patterns and understand how well these factors explain variations in cycle usage.

**Objectives**
 * Analyze various potential variables to determine their impact on usage patterns.
 * Determine which factors are most significant in predicting demand.
 * Perform Exploratory Data Analysis (EDA) to check the structure, characteristics, and missing values of the dataset.
 * Conduct hypothesis testing (2-sample t-test, ANOVA/Kruskal-Wallis, Chi-square) to evaluate the impact of working days, seasons, and weather on cycle rentals.

**Data Set**
 * datetime: datetime
 * season: season (1: spring, 2: summer, 3: fall, 4: winter)
 * holiday: whether day is a holiday or not
 * workingday: if day is neither weekend nor holiday is 1, otherwise is 0
 * weather: 1 (Clear/Partly cloudy), 2 (Mist + Cloudy), 3 (Light Snow/Rain), 4 (Heavy Rain/Ice Pallets)
 * temp: temperature in Celsius
 * atemp: feeling temperature in Celsius
 * humidity: humidity
 * windspeed: wind speed
 * casual: count of casual users
 * registered: count of registered users
 * count: count of total rental bikes including both casual and registered

**Milestones**
 * Import dataset and perform basic data analysis including checking data shape and descriptive statistics.
 * Perform missing value detection.
 * Conduct outlier detection using boxplots and the IQR method.
 * Explore correlations among continuous variables using a Spearman Correlation Heatmap.
 * Check test assumptions for ANOVA, including Normality via the Shapiro-Wilk test and Equal Variance via Levene's test.
 * Perform Hypothesis Testing (T-test, Kruskal-Wallis, Chi-square) to validate business dependencies.
 * Generate insights and actionable business recommendations.

**Findings**
 * The dataset contains 10886 rows and 12 columns, with zero missing values.
 * "Weather 4" has only 1 data point and should be removed.
 * Feeling temperature (atemp) and actual temperature (temp) are very highly correlated, as they are mostly almost the same.
 * The dependent variable count is highly correlated with casual and registered variables; subsequently, casual, registered, and atemp were dropped to avoid multicollinearity.
 * The distribution of "count" is right-skewed, which is expected since the rental count cannot be negative.
 * Any "count" greater than 647 is technically an outlier, but it is considered natural as per the current business scenario.
 * The "count" data does not follow a Gaussian (Normal) Distribution, leading to the failure of the Shapiro-Wilk test.
 * The variances across different weather conditions are not equal, leading to the failure of Levene's Test.
 * Based on a 2-Sample T-test, the mean demand for bikes on a working day is similar to or greater than that on a non-working day.
 * Based on the non-parametric Kruskal-Wallis Test, the median ride counts are significantly different across both different weather conditions and different seasons.
 * Based on the Chi-square test of independence, weather conditions are dependent on the season.
 * Demand for bikes peaks in Season 3 (fall) and shoots up in Weather 1 (sunny).
 * Demand for bikes is higher on working days and lower on non-working days.

**Recommendations**
 * Implement dynamic pricing based on demand and weather conditions.
     * Introduce surge pricing during high-demand periods.
     * Offer discounts during off-peak hours.
 * Strategize seasonal maintenance and fleet planning by scheduling primary maintenance during Season 1, when demand drops, to prepare for peak demand in Season 3.
 * Optimize the allocation of the fleet based on the time of day and specific locations.
 * Enhance user engagement on non-working days (when demand is lower) by introducing weekend offers or group rides.
 * Promote eco-friendly campaigns to boost general brand awareness and cycle usa

**Colab Link**
 * https://colab.research.google.com/drive/1viiv5B2wgTv4jfNBnBN1kJhtu3ramZc4
  
