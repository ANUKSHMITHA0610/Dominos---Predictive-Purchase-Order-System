<div align="center">

# 🍕 Dominos - Predictive Purchase Order System

</div>

<div align="center">

[![](https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=darkgreen)](https://www.python.org)
[![](https://img.shields.io/badge/scikit_learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/stable/)
[![](https://img.shields.io/badge/Numpy-777BB4?style=for-the-badge&logo=numpy&logoColor=white)](https://numpy.org)
[![](https://img.shields.io/badge/Pandas-2C2D72?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org)
[![](https://img.shields.io/badge/Plotly-239120?style=for-the-badge&logo=plotly&logoColor=white)](https://plotly.com)
[![](https://img.shields.io/badge/Machine%20Learning-FF6F00?style=for-the-badge&logo=google-cloud&logoColor=white)](https://www.google.com/)

</div>

<div align="center">
  
  <img src="https://github.com/user-attachments/assets/9bbc3acc-86f2-4e9e-9dbd-d5399264440e" width="800"/>
  
</div>

## 📈 Problem Statement

This project focuses on optimizing Domino's inventory management by building a predictive system that forecasts pizza sales and generates purchase orders for ingredients. By leveraging historical sales data, the goal is to develop a model that accurately predicts future sales, allowing Domino's to order the right amount of ingredients, minimizing waste, and preventing stockouts.

---

## 🎯 Objective:
- Develop a predictive model to forecast pizza sales.
- Create a purchase order system that calculates the required quantities of ingredients based on the sales forecast.
  
---

## 🔍 Dataset Overview

The project consists of two datasets pizza_sales and pizza ingredients .

**i) Pizza Sales Dataset**

The **Pizza Sales dataset** contains 48,620 entries, capturing data on individual pizza sales. Each row records a sale, including details such as the `pizza_id`, which uniquely identifies the sale, the `order_id` linking it to a specific order, the `pizza_name_id`, and the `quantity` of pizzas sold. It also provides information on the `order_date` and `order_time`, as well as the `unit_price` and `total_price` for each pizza. The dataset further includes the `pizza_size`, `pizza_category` (which classifies pizzas into categories like Classic or Veggie), and the list of `pizza_ingredients`. There are some missing values, particularly in the `pizza_category`, `pizza_name_id`, and `pizza_ingredients` columns. This dataset offers a detailed view of pizza sales, encompassing pricing, order timing, and the characteristics of each pizza sold.

**ii)Pizza Ingredients Dataset**

The **Pizza Ingredients dataset** consists of 518 entries that provide information about various pizzas, including the `pizza_name_id`, which uniquely identifies each pizza, the `pizza_name`, the list of `pizza_ingredients`, and the `Items_Qty_In_Grams`, which indicates the quantity of each ingredient in grams. While the majority of the entries have complete data, there are a few missing values in the `Items_Qty_In_Grams` column. This dataset essentially details the composition of each pizza, giving insight into the ingredients and their respective quantities.

---

## 📊 Metrics

- [__Mean Absolute Percentage Error__](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.mean_absolute_percentage_error.html): Used to evaluate the accuracy of forecasting models. It measures the average absolute percentage error between the predicted values and the actual values. 

---

## 💡 Business Use Cases

-  **Inventory Management**: Ensuring optimal stock levels to meet future demand without overstocking.
-  **Cost Reduction**: Minimizing waste and reducing costs associated with expired or excess inventory.
-  **Sales Forecasting**: Accurately predicting sales trends to inform business strategies and promotions.
-  **Supply Chain Optimization**: Streamlining the ordering process to align with predicted sales and avoid disruptions.

---

## 🛠️ Approach

### I.  Data Preprocessing 

**Data Cleaning** ensures the dataset's accuracy and consistency through:

- **Handling Missing Data**:
  - Detected missing values.
  - Replaced missing values using mean, median, mode, or placeholders.
  - Removed columns or rows with excessive missing data if necessary.

- **Removing Inconsistent Data**:
  - Checked for format consistency and valid ranges.
  - Fixed inconsistencies, such as standardizing text and correcting typos.

- **Handling Outliers**:
  - Identified outliers using statistical methods or visualizations.
  - Removed, transform, or categorize outliers based on their impact.

### II.  Exploratory Data Analysis (EDA)

**Exploratory Data Analysis (EDA)** discoverS patterns, relationships, and anomalies in the data.



### III. Sales Prediction

Sales Prediction involves **Time Series Forecasting** , A technique used to predict future values based on historical data collected over time. The process includes the following steps:

**Feature Engineering**

Created new variables from the raw sales data to improve the model’s performance like:

- **Day of the Week**: Extracted the day of the week from the sales date to capture weekly variations.
- **Month**: Extracted the month from the sales date to account for monthly trends and seasonal patterns.
- **Holiday Effects**: Identified and included features for holidays or special events that can impact sales patterns.

**Model Selection**

Model Selection involves choosing the most suitable forecasting model for your sales data:

- **ARIMA (AutoRegressive Integrated Moving Average)**: Captures trends and autocorrelations in non-seasonal data.
- **SARIMA (Seasonal ARIMA)**: Extends ARIMA to handle seasonality.
- **Prophet**: Designed for handling missing data, outliers, and multiple seasonalities.
- **LSTM (Long Short-Term Memory)**: A type of recurrent neural network for capturing long-term dependencies in complex data.
- **Regression Model**: Useful when data has significant explanatory variables affecting sales.

**Model Training**

Model Training involves fitting the chosen model to historical sales data:

- Splited the data into training and test sets to evaluate model performance. 
- Trained the model on the training set by adjusting parameters to minimize prediction errors.
- Optimized model performance by tuning hyperparameters using techniques like cross-validation or grid search.

**Model Evaluation**

Model Evaluation assesses the accuracy and performance of the trained model using:

- **Mean Absolute Percentage Error (MAPE)**:
  - **Definition**: Measures forecast accuracy by calculating the average absolute percentage error between predicted and actual values.
  - **Formula**:
    ```text
    MAPE = (1/n) * Σ |(A_i - F_i) / A_i| * 100
    ```
    - `A_i` = Actual value
    - `F_i` = Forecasted value
    - `n` = Number of observations
  - **Interpretation**: A lower MAPE value indicates better model accuracy, providing a percentage error to understand the accuracy in the context of the data.

Evaluating the model using MAPE helps determine its performance and whether it meets the accuracy requirements for predicting future sales.


### IV.  Purchase Order Generation

- **Sales Forecasting**: Predict pizza sales for the next week using the trained model.
- **Ingredient Calculation**: Calculate the required quantities of each ingredient based on the predicted sales and the ingredient dataset.
- **Purchase Order Creation**: Generate a detailed purchase order listing the quantities of each ingredient needed for the predicted sales period.

---
