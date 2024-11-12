# Stock Price Prediction Project

This project predicts future stock prices using historical data and an LSTM (Long Short-Term Memory) neural network. The project involves data collection, preprocessing, model building, training, and evaluation to assess prediction accuracy.

## Table of Contents

- Project Overview
- Data Processing
- Model Architecture
- Training and Evaluation
- Results
- Requirements

## Project Overview

The project uses an LSTM model, which is well-suited for time-series data like stock prices. The main goal is to predict the closing stock price based on historical daily stock data including Open, High, Low, Close, and Volume values.

## Data Processing

Data Collection: The historical stock price data is read from a CSV file, which includes columns such as Date, Open, High, Low, Close, Volume, and Turnover.

## Preprocessing:

Date Formatting: The Date column is converted to a DateTime format, setting it as the DataFrame index for easy time-series handling.
Sorting: The data is sorted chronologically to maintain the order.
Feature Scaling: The Close column, used as the target variable, is scaled between 0 and 1 using MinMaxScaler.
Sequence Generation: A sequence length of 60 days is used to create the input sequences for the LSTM model, where each input contains 60 days' worth of closing prices.

## Model Architecture

The model is built using an LSTM architecture in Keras:
- LSTM Layers: Extract temporal features from sequential data.
- Dropout Layers: Reduce overfitting by randomly deactivating neurons during training.
- Dense Layer: A fully connected layer with a single output to predict the closing price.

## Training and Evaluation

Training Setup:
- The dataset is split into training and validation sets.
- The model is compiled with mean_squared_error as the loss function and adam as the optimizer.
- Training involves feeding the LSTM model with the processed sequences over multiple epochs to minimize the prediction error.

## Evaluation:

Model predictions are scaled back to the original range using the inverse transform of MinMaxScaler.
The predictions are compared with actual values to calculate accuracy and visualize the model’s performance.

## Results

The model achieved a reasonable level of accuracy in predicting future stock prices, with performance evaluated using Mean Squared Error (MSE) on the validation set. The following plot shows the predicted versus actual closing prices, indicating the model’s effectiveness in capturing trends.

## Requirements
To run this project, install the following dependencies in requirements.txt:
```
  numpy
  pandas
  matplotlib
  tensorflow
  keras
  sklearn
```
