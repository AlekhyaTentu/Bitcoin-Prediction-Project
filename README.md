Bitcoin Price Prediction Using Multi-Source Sentiment Analysis and Machine Learning Techniques

Overview

This project aims to predict Bitcoin price trends by analyzing the sentiment of various data sources, including news articles, Wikipedia edits, and historical Bitcoin price data. The project uses a combination of advanced machine learning techniques such as sentiment analysis, historical price forecasting, and backtracking for prediction accuracy. The goal is to build a model that forecasts Bitcoin price fluctuations using sentiment-driven insights.

Table of Contents

Project Description
Datasets
Methodology
Implementation
Modeling
Evaluation
Getting Started
Contributing
Project Description

Bitcoin is highly volatile, and predicting its price fluctuations has been a significant challenge for financial analysts and enthusiasts alike. In this project, we leverage sentiment data derived from multiple sources—news articles, Wikipedia edits, and historical Bitcoin data—to build a model that predicts price trends.

The key components of this project include:

Sentiment Analysis: Using VADER, BERT, and FinBERT models to extract sentiment from various textual data sources.
Price Prediction: Using historical price data and the sentiment analysis results to predict future Bitcoin prices.
Backtracking & Model Evaluation: Implementing a backtracking strategy to evaluate the model and improve accuracy through iterative corrections.
Datasets

The following datasets are used in the project:

Bitcoin Historical Data: Bitcoin price data (open, close, high, low, and volume) collected via Yahoo Finance (yfinance).
Wikipedia Edits: Extracted Wikipedia edits for Bitcoin, used to analyze how public sentiment changes over time.
News Articles: A collection of articles related to Bitcoin, scraped using APIs such as SerpApi, for sentiment analysis.
Methodology

Sentiment Extraction
VADER Sentiment Analysis:
Purpose: Used for rapid sentiment analysis based on predefined lexicons and rules. VADER is particularly well-suited for social media and short texts like headlines and news snippets.
Application: Extracts an initial sentiment score (positive, negative, or neutral) from the text.
BERT (Bidirectional Encoder Representations from Transformers):
Purpose: Fine-tuned to extract nuanced sentiment from longer texts. BERT captures contextual meaning by processing both sides of the text, unlike traditional models that only analyze text from left to right or vice versa.
Application: Used for a deeper analysis of articles, Wikipedia revisions, and other long-form content.
FinBERT (Optional):
Purpose: A specialized version of BERT, trained specifically for financial data. It focuses on the sentiment found in financial documents, including investment articles and financial news.
Application: Used to fine-tune sentiment extraction on financial news articles and Bitcoin-related financial content.
Price Prediction
Historical Price Data:
We train the model using Bitcoin’s historical price data, which includes features like Open, High, Low, Close, and Volume.
Time Series Modeling: We explore algorithms like Linear Regression and LSTM (Long Short-Term Memory) networks for making predictions on future prices.
Sentiment-Driven Models:
The sentiment scores derived from VADER, BERT, and FinBERT are used as additional features in the prediction model.
Modeling Approach: We explore machine learning algorithms (Linear Regression, Random Forest, LSTM) for time series forecasting.
Backtracking and Evaluation
Backtracking:
We implement backtracking to iteratively refine our model by correcting previous predictions using updated data.
The backtracking strategy helps in fine-tuning the model and ensuring accurate predictions over time.
Model Evaluation:
We evaluate the model's performance using metrics such as Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and R² score to assess prediction accuracy.
Cross-Validation: We perform cross-validation to ensure the robustness of our model.
Implementation

The implementation involves the following steps:

Data Collection:
Historical Bitcoin price data is fetched using the yfinance package.
Sentiment data is scraped using APIs like SerpApi and processed for analysis.
Data Preprocessing:
Sentiment scores are calculated for each data point.
The data is cleaned and preprocessed to merge Bitcoin price data with sentiment scores.
Model Training:
We use different machine learning algorithms to train the model on historical data and sentiment scores.
Various techniques are tested to ensure the best model selection.
Prediction:
The trained model is used to predict future Bitcoin price trends based on the input features.
Modeling

We experiment with several machine learning models:

Linear Regression: For a basic prediction model.
Random Forest: For a non-linear model that can handle complex relationships.
LSTM: For sequential data modeling and time-series forecasting, considering the nature of Bitcoin price fluctuations.
Evaluation

Metrics: We evaluate the model using Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and R² score.
Model Tuning: The models are fine-tuned using cross-validation and hyperparameter optimization to enhance prediction accuracy.
Getting Started

To run the project locally, follow these steps:

Prerequisites
Python 3.x
Install the required libraries:
pip install pandas numpy matplotlib scikit-learn transformers yfinance vaderSentiment
Steps to Run the Code
Clone the repository:
git clone https://github.com/yourusername/bitcoin-price-prediction.git
cd bitcoin-price-prediction
Run the Jupyter notebook or Python scripts in the notebooks/ folder to begin exploring the dataset and building models.
The bitcoin_data_5_years.csv file must be placed in the data/ folder.
Run Sentiment Analysis and Prediction Models
Sentiment Analysis: Run the sentiment extraction scripts to get sentiment scores for the news articles and Wikipedia edits.
Prediction Model: Use the provided scripts to train and evaluate the Bitcoin price prediction models using the sentiment scores.
Contributing

We welcome contributions to the project! If you'd like to improve the model, add new features, or fix any issues, feel free to fork the repository and submit a pull request.

Fork the repository
Create your feature branch (git checkout -b feature/new-feature)
Commit your changes (git commit -am 'Add new feature')
Push to the branch (git push origin feature/new-feature)
Open a pull request
Acknowledgements

VADER Sentiment Analysis
HuggingFace Transformers
FinBERT
Yahoo Finance API (yfinance)
