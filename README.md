# Bike-Demand-Sharing

### Project Overview: Bike Sharing Demand Prediction

This project aims to predict bike-sharing demand using historical data. The dataset contains various features like temperature, humidity, weather conditions, and other temporal attributes. The goal is to create a model that can predict the total number of bikes rented (cnt) based on these features.

### Key Steps in the Project:

1. *Data Understanding and Exploration:*
   - The dataset, BoomBikes.csv, is loaded using pandas. It contains 730 rows and 16 columns, including features like season, temp, humidity, windspeed, casual, registered, and cnt (total count of rentals).
   - Data types are inspected, and descriptive statistics are generated for a better understanding of data distributions.
   
2. *Data Preprocessing:*
   - *Categorical Values*: Some columns like season and weathersit are mapped to human-readable string values. For example, seasons are mapped to spring, summer, fall, and winter.
   - *Feature Engineering*: Dummy variables are created for categorical columns such as season, month, and weekday. This is essential for feeding categorical data into the machine learning model.
   - Missing values are handled by converting dates to datetime format and dropping irrelevant columns like instant and dteday.

3. *Data Visualization:*
   - Distributions of key features like temperature, windspeed, and the target variable (cnt) are visualized using Seaborn.
   - Box plots show how various features like season, workingday, and holiday affect bike rental counts.
   - A heatmap shows the correlations between features, indicating strong relationships between temperature, season, and bike rentals.

4. *Model Building:*
   - The dataset is split into training (70%) and testing (30%) sets.
   - *Feature Scaling*: Numerical features such as temp, hum, and windspeed are scaled using the MinMaxScaler to normalize their values for better model performance.
   - *Model Training*: A linear regression model is used to predict the bike rental count. Initially, all features are used to train the model, and Recursive Feature Elimination (RFE) is applied to select the most important ones. This process narrows down the features to the most relevant ones like temp, yr, humidity, windspeed, and weather conditions.

5. *Model Evaluation:*
   - The model's performance is evaluated using the *R-squared* value. For the training set, the R-squared value is 0.85, indicating that 85% of the variance in bike rental counts can be explained by the model.
   - On the test set, the model achieves an R-squared value of approximately *0.805*, indicating good predictive performance.

6. *Conclusions:*
   - Key factors influencing bike rental demand include *temperature, **year, **humidity, **windspeed, and **weather conditions*.
   - The linear regression model with selected features performs well in predicting bike-sharing demand, providing insights into how environmental and temporal factors affect rentals.

This project demonstrates a systematic approach to data preprocessing, feature selection, and model building, leading to a high-performing predictive model for bike-sharing demand.
