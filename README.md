# House-Price-Prediction-Model
## Overview

This project aims to build a model to predict median house values in California using the provided dataset. The dataset consists of 10 types of metrics for each block group in California, such as population, median income, housing median age, total rooms, total bedrooms, population, households, median income, ocean proximity, and median house value. The objective is to train the model to learn from this data and predict the median housing price in any district, given all the other metrics.

**Domain:** Finance and Housing

## Dataset Description

The dataset contains the following features:

- **longitude:** Longitude value for the block.
- **latitude:** Latitude value for the block.
- **housing_median_age:** Median age of the house in the block.
- **total_rooms:** Count of the total number of rooms (excluding bedrooms) in all houses in the block.
- **total_bedrooms:** Count of the total number of bedrooms in all houses in the block.
- **population:** Count of the total number of population in the block.
- **households:** Count of the total number of households in the block.
- **median_income:** Median of the total household income of all the houses in the block.
- **ocean_proximity:** Type of the landscape of the block [Unique Values: 'NEAR BAY', '<1H OCEAN', 'INLAND', 'NEAR OCEAN', 'ISLAND'].
- **median_house_value:** Median of the household prices of all the houses in the block.

## Data Preprocessing

- The dataset contains only a small percentage of missing values, so we drop the rows with missing values.
- The data in some columns are skewed, and to obtain a Gaussian distribution, we apply a log transformation on 'total_rooms', 'total_bedrooms', 'population', and 'households'.
- We convert the categorical feature 'ocean_proximity' into numerical values using one-hot encoding.

## Exploratory Data Analysis

- We identify correlations between features and the target variable 'median_house_value'.
- We observe that 'median_house_value' is highly correlated with 'median_income', which suggests that higher income areas tend to have higher house values.
- 'median_house_value' is negatively correlated with 'INLAND', indicating that houses in inland areas are generally more affordable.
- The latitude and longitude are also negatively correlated with 'median_house_value', suggesting that houses in certain regions are priced differently.

## Feature Engineering

- We create a new feature 'bedroom_ratio', representing the ratio of total bedrooms to total rooms, which is found to be negatively correlated with 'median_house_value'.

## Model Selection

We evaluate various regression models to predict the median house values:

- **Linear Regression:** Performs moderately well but has room for improvement.
- **K Nearest Neighbors (KNN):** It shows a decent performance with a k value of 10.
- **Random Forest Regressor:** Performs well with some hyperparameter tuning.
- **Gradient Boosting Regressor:** Demonstrates good performance with 250 estimators.
- **XGBoost Regressor:** Shows better performance with some hyperparameter tuning.
- **Neural Networks:** We experimented with three neural network architectures - simple, medium, and large. The medium-sized network yields promising results.

## Conclusion

The project demonstrates the predictive power of machine learning models in estimating house prices based on various features. The best-performing model is the Gradient Boosting Regressor, followed by the XGBoost Regressor and Neural Networks. These models provide valuable insights into the factors influencing house prices and can be further fine-tuned to achieve even better results.

The project offers valuable tools for real estate professionals and homeowners in California to make informed decisions about housing investments and understand market dynamics. As a data scientist, I will continue to explore ways to improve the models and explore other advanced techniques for better predictions. The project code and models are available in the respective folders for reference and further development.

For more details, please refer to the project notebooks and explore the code. Feel free to reach out for any questions or suggestions. Thank you!

