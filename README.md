# A Comparative Study of Big Data and Machine Learning Models for Assessing the Impact of Climate Change on Sea-Level Rise in Fiji

This repository contains the research and implementation of a scalable framework for forecasting sea-level rise in Fiji using big data technologies and machine learning. The study compares the performance of various time-series models to provide accurate projections for climate change impact analysis.

## Project Overview

Fiji, a small island nation in the South Pacific, faces a significant existential threat from rising sea levels and frequent flooding due to climate change. Conventional forecasting methods are often inadequate for handling the complexity and scale of modern environmental datasets. This project addresses this challenge by developing a scalable framework that leverages big data tools and advanced machine learning models to accurately predict sea-level fluctuations. By analyzing 20 years of historical data, this work aims to provide a reliable foundation for policymakers and coastal managers to develop effective climate adaptation strategies, protecting infrastructure, communities, and biodiversity.

## Key Features

*   **Comparative Model Analysis:** In-depth evaluation and comparison of Long Short-Term Memory (LSTM), Random Forest (RF), and Gradient Boosting Regressor (GBR) models.
*   **High-Accuracy Forecasting:** The Gradient Boosting model achieved the highest accuracy, providing a reliable tool for future sea-level predictions.
*   **Big Data Integration:** Utilizes Apache Spark and Hadoop HDFS for distributed processing and management of a large-scale, 20-year hourly dataset.
*   **Comprehensive Data Pipeline:** Includes robust data cleaning, exploratory data analysis (EDA), and time-series feature engineering to enhance model performance.
*   **Real-World Impact:** The findings provide a strong foundation for data-driven policy-making for coastal planning and climate resilience.

## Methodology & Technologies

### 1. Datasets

The study utilizes two primary data sources spanning a 20-year period (2001-2021):

*   **Historical Climate Data:** Sourced from **NASA's POWER database**, including parameters like temperature, humidity, wind speed, and precipitation.
*   **Sea-Level Measurements:** Acquired from the **University of Hawaii Sea Level Center**, providing hourly sea-level records.

### 2. Data Processing & Feature Engineering

A multi-step preprocessing pipeline was implemented to ensure data quality:

*   **Data Cleaning:** Handled missing values using matrix/heatmap visualization and substituted invalid placeholders (e.g., 999, 32767) with null values, which were then handled via linear interpolation.
*   **Feature Engineering:**
    *   Created a unified `Datetime` column from YEAR, MO, and DY for time-series indexing.
    *   Extracted time-based features such as `Month`, `Day`, and `DayOfWeek` to capture temporal patterns.
    *   Removed rows with any remaining `NaN` values after feature creation to ensure a complete dataset for modeling.

### 3. Modeling & Evaluation

The study compared several models to identify the most effective for sea-level forecasting:

*   **Models:** Long Short-Term Memory (LSTM), Random Forest (RF), and Gradient Boosting Regressor (GBR).
*   **Evaluation Metrics:** Model performance was assessed using Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE).

### 4. Tools & Technologies

*   **Big Data:** Apache Spark, Hadoop HDFS
*   **Development Environment:** Docker, Databricks
*   **Data Analysis & ML:** Python, Pandas, Scikit-learn
*   **Deep Learning:** TensorFlow (for LSTM)

## Results & Key Findings

The results demonstrated that ensemble machine learning models significantly outperformed the deep learning model in this forecasting task. The Gradient Boosting Regressor (GBR) emerged as the best-performing model.

**Model Performance Comparison:**

| Model               | MAE    | RMSE   |
| ------------------- | ------ | ------ |
| LSTM                | 36.56  | 51.47  |
| Random Forest       | 0.02   | 0.029  |
| **Gradient Boosting** | **0.02**   | **0.027**  |
| GRU                 | 32.45  | 42.89  |

*Note: Table is based on Table I in the source paper. The GBR model shows the lowest error rates.*

**Key Implications:**

*   **Certainty for Coastal Planners:** The high accuracy of the GBR model provides a reliable tool for making informed decisions on infrastructure, flood management, and climate adaptation.
*   **Importance of Model Selection:** The study highlights the effectiveness of ensemble methods like GBR for this type of time-series data, particularly for their ability to capture complex patterns without the extensive tuning required by deep learning models.
*   **Resource Efficiency:** Utilizing the optimal model (GBR) saves time and computational resources that might otherwise be spent on less effective approaches.

## Future Work

*   Integrate additional environmental variables to enhance model accuracy.
*   Develop generalized space-time prediction models.
*   Analyze combined hybrid model approaches for potential performance improvements.
