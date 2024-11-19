# Short-Term Electricity Demand Forecasting

This repository provides a comprehensive machine learning solution for short-term electricity demand forecasting aimed at improving power grid management, preventing blackouts, and minimizing wastage. The project compares the performance of several machine learning models, including XGBoost, RNN, LSTM, GRU, Transformer, and variants, on PJM energy data. The goal is to identify the most accurate model for predicting electricity demand, taking into account various time-related factors and the intricacies of the energy consumption patterns.

## Table of Contents
1. [Introduction](#introduction)
2. [Previous Work](#previous-work)
3. [Data Collection](#data-collection)
4. [Data Preprocessing](#data-preprocessing)
5. [Model Selection](#model-selection)
6. [Model Training and Hyperparameter Tuning](#model-training-and-hyperparameter-tuning)
7. [Model Evaluation](#model-evaluation)
8. [Comparison Across Models](#comparison-across-models)
9. [Error Analysis](#error-analysis)
10. [Contributors](#contributors)


## Introduction

Accurate short-term electricity demand forecasting is crucial for effective grid management, enabling utilities to balance supply and demand efficiently. By predicting electricity demand in the near future, this model helps utilities avoid blackouts and reduce wastage by adjusting generation or distribution strategies in real-time.

## Previous Work

The previous study compared several machine learning models, such as Stacked LSTM, XGBoost, and Deep RNN, for short-term electricity demand forecasting using PJM energy data. The model performance was evaluated using the following metrics:
- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R² score

The focus of the study was to evaluate how internal architecture and hyperparameters impact the forecasting accuracy. The results suggested that LSTM-based models outperform XGBoost and RNN models in terms of prediction accuracy.

## Data Collection

The dataset used in this project is the PJM energy data, which includes historical electricity demand patterns. This data serves as the foundation for training and testing the machine learning models. The data includes time-stamped records of electricity consumption, which are key for training time-series forecasting models.

## Data Preprocessing

Data preprocessing is an essential step to ensure the quality of input data before feeding it into machine learning models. The following steps were performed:

- **Handling Missing Data:** Missing or incomplete records were handled through imputation or removal strategies.
- **Rolling Statistics:** Time-based features such as moving averages were computed to capture trends and seasonal effects.
- **Time-related Features:** Features such as the hour of the day, day of the week, and seasonality indicators were extracted to help the model capture temporal patterns.
- **Normalization/Standardization:** Input features were scaled to a common range using normalization or standardization techniques to improve model training efficiency and convergence.

## Model Selection

The following machine learning models were considered for forecasting electricity demand:

1. **XGBoost (Extreme Gradient Boosting):** A powerful ensemble method that combines multiple weak learners (decision trees) to form a strong learner.
2. **Recurrent Neural Networks (RNN):** A type of neural network designed for sequence prediction problems.
3. **Long Short-Term Memory (LSTM):** A variant of RNN that helps address the vanishing gradient problem and captures long-range dependencies.
4. **Gated Recurrent Unit (GRU):** A simpler variant of LSTM that uses fewer parameters but still performs well on time-series tasks.
5. **Transformer Model:** A state-of-the-art model based on self-attention mechanisms, typically used for sequence-to-sequence tasks.

## Model Training and Hyperparameter Tuning

Each model was trained using the preprocessed data. The hyperparameters for each model were tuned through techniques like grid search or random search to optimize performance. This includes adjusting the number of layers, the number of units in each layer, the learning rate, batch size, and other relevant parameters.

## Model Evaluation

The performance of each model was evaluated using the following metrics:

- **R² Score:** Measures the proportion of variance in the dependent variable that is predictable from the independent variables.
- **Root Mean Squared Error (RMSE):** A metric that indicates the average magnitude of error in the model's predictions.
- **Mean Absolute Error (MAE):** Measures the average absolute difference between predicted and actual values.

## Comparison Across Models


| Model                        | MAE      | MSE              | R²     |
|------------------------------|----------|------------------|--------|
| **LSTM**                     | 2110.10  | 7.42e+06         | 0.9826 |
| **RNN**                       | 2503.22  | 1.02e+07         | 0.9761 |
| **GRU**                       | 2968.32  | 1.40e+07         | 0.9671 |
| **Bidirectional LSTM**        | 1792.30  | 5.76e+06         | 0.9865 |
| **LSTM with Attention**       | 2110.10  | 7.42e+06         | 0.9826 |
| **Stacked LSTM**              | 2042.55  | 6.92e+06         | 0.9838 |
| **Basic Transformer**         | 1393.69  | 3.91e+06         | 0.9908 |
| **Transformer with LSTM**     | 1310.49  | 3.22e+06         | 0.9924 |

The results show that the **Transformer with LSTM** model outperforms all other models, achieving the lowest MAE (1310.49), MSE (3.22e+06), and the highest R² score (0.9924).

## Error Analysis

Error analysis was performed to understand the types of errors each model makes. For instance:
- Some models may overestimate or underestimate electricity demand during peak hours or on weekends.
- The models may exhibit bias toward certain time periods due to the temporal nature of the data.

Understanding these errors allows for model improvements, such as adjusting the features or modifying model parameters.

## Contributors

- **Vissapragada Sandeep:** Data visualisation, Models Contributed - GRU, Transformer, and Bidirectional LSTM models.
- **Rohan Naskar:** Focused on Transformer model architecture and data preprocessing.
- **Saurabh Ramdas Nevase:** Worked on LSTM model and data preprocessing techniques.
- **Shrashank Maravi:** Contributed to the XGBoost model and Stacked LSTM model.
- **Sugandh Kumar:** Focused on RNN and LSTM models.


---

Feel free to clone this repository, run the models, and explore the code to improve and customize your own short-term electricity demand forecasting solutions!
