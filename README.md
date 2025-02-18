
# Bitcoin Price Prediction Using Multi-Source Sentiment Analysis and Machine Learning Techniques

## Overview

This project aims to predict Bitcoin price trends by analyzing the sentiment of various data sources, including news articles, Wikipedia edits, and historical Bitcoin price data. The project employs a combination of machine learning techniques such as sentiment analysis, time series forecasting, and backtracking to ensure prediction accuracy. The goal is to build a robust model that forecasts Bitcoin price fluctuations using sentiment-driven insights.

## Table of Contents

- [Project Description](#project-description)
- [Datasets](#datasets)
- [Methodology](#methodology)
- [Implementation](#implementation)
- [Modeling](#modeling)
- [Evaluation](#evaluation)
- [Getting Started](#getting-started)
- [Contributing](#contributing)
- [Acknowledgements](#acknowledgements)

## Project Description

Bitcoin is a highly volatile digital asset, and predicting its price fluctuations has been a significant challenge for analysts, investors, and traders alike. This project leverages sentiment data derived from multiple sources—news articles, Wikipedia edits, and historical Bitcoin data—to predict future price trends of Bitcoin. By analyzing the sentiment around Bitcoin and combining it with historical price data, this project builds a predictive model aimed at capturing price movements in a timely and accurate manner.

### Key Components:
1. **Sentiment Analysis**: 
   - We use VADER, BERT, and FinBERT models to extract sentiment from various textual data sources.
2. **Price Prediction**:
   - Historical price data of Bitcoin, combined with sentiment scores, is used to forecast future price trends.
3. **Backtracking & Model Evaluation**:
   - Implementing backtracking techniques to refine predictions and improve accuracy iteratively.
   
## Datasets

The following datasets are used in the project:
1. **Bitcoin Historical Data**: 
   - Bitcoin price data (Open, High, Low, Close, Volume) collected from Yahoo Finance using the `yfinance` API.
2. **Wikipedia Edits**: 
   - Extracted Wikipedia edits related to Bitcoin, used for analyzing how public sentiment changes over time.
3. **News Articles**:
   - A collection of news articles related to Bitcoin, scraped using APIs such as SerpApi, for sentiment analysis.

## Methodology

### Sentiment Extraction

1. **VADER Sentiment Analysis**:
   - **Purpose**: Used for rapid sentiment estimation based on predefined lexicons and rules. VADER is particularly suited for short texts such as headlines and social media posts.
   - **Application**: Extracts sentiment scores (positive, negative, or neutral) from news snippets and article headlines.

2. **BERT (Bidirectional Encoder Representations from Transformers)**:
   - **Purpose**: Fine-tuned for extracting nuanced sentiment from longer texts. BERT captures the context by processing text bidirectionally (both left-to-right and right-to-left).
   - **Application**: Used for analyzing long-form content such as full news articles and Wikipedia edits.

3. **FinBERT** (Optional):
   - **Purpose**: A specialized version of BERT trained specifically for financial data. FinBERT is used to analyze financial news articles.
   - **Application**: Fine-tuned to perform sentiment extraction on financial documents, providing more relevant insights for Bitcoin's market sentiment.

### Price Prediction

1. **Historical Price Data**: 
   - Bitcoin’s historical price data is used to train the model. The dataset includes features such as Open, High, Low, Close, and Volume.
   
2. **Time Series Modeling**:
   - We explore machine learning algorithms such as Linear Regression and Long Short-Term Memory (LSTM) networks, which are suitable for time series forecasting.
   
3. **Sentiment-Driven Models**:
   - The sentiment scores derived from VADER, BERT, and FinBERT are incorporated into the model as additional features. These sentiment scores help the model learn how public sentiment influences Bitcoin price movements.

### Backtracking and Evaluation

1. **Backtracking**:
   - A backtracking approach is implemented to iteratively refine our model by updating predictions as new data becomes available. This iterative approach helps in improving model accuracy over time.

2. **Model Evaluation**:
   - We evaluate model performance using key metrics such as Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and R² score.
   - **Cross-Validation**: Cross-validation techniques are employed to ensure model robustness and generalizability across different datasets.

## Implementation

The implementation follows these steps:

### Data Collection:
- Historical Bitcoin price data is fetched using the `yfinance` package.
- Sentiment data is scraped using APIs like SerpApi and processed for analysis.

### Data Preprocessing:
- Sentiment scores are extracted and cleaned.
- The data is preprocessed to merge Bitcoin price data with sentiment scores.

### Model Training:
- We experiment with various machine learning models such as Linear Regression, Random Forest, and LSTM networks to train our prediction model using both historical data and sentiment data.

### Prediction:
- The trained model is then used to predict future Bitcoin price trends, based on the input features and sentiment-driven insights.

## Modeling

The following machine learning models are explored:

- **Linear Regression**: A simple model used as a baseline for price prediction.
- **Random Forest**: A non-linear model capable of handling complex relationships between features.
- **LSTM (Long Short-Term Memory)**: A type of recurrent neural network (RNN) suited for sequential data like time series, which captures long-term dependencies.

## Evaluation

We evaluate our models using:

- **Mean Absolute Error (MAE)**
- **Root Mean Squared Error (RMSE)**
- **R² Score**

Models are further fine-tuned using cross-validation and hyperparameter optimization techniques.

## Getting Started

### Prerequisites

- Python 3.x
- Required libraries:
  ```bash
  pip install pandas numpy matplotlib scikit-learn transformers yfinance vaderSentiment
  ```

### Steps to Run the Code

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/bitcoin-price-prediction.git
   cd bitcoin-price-prediction
   ```

2. Run the Jupyter notebooks or Python scripts located in the `notebooks/` folder.

3. The `bitcoin_data_5_years.csv` file should be placed in the `data/` folder.

4. Run Sentiment Analysis and Prediction Models:
   - Execute the sentiment extraction scripts to get sentiment scores for news articles and Wikipedia edits.
   - Use the provided scripts to train and evaluate the Bitcoin price prediction models using sentiment data.

## Contributing

We welcome contributions to the project! Feel free to fork the repository and submit a pull request.

1. Fork the repository.
2. Create a new feature branch:
   ```bash
   git checkout -b feature/new-feature
   ```
3. Commit your changes:
   ```bash
   git commit -am 'Add new feature'
   ```
4. Push to your branch:
   ```bash
   git push origin feature/new-feature
   ```
5. Open a pull request.

## Acknowledgements

- [VADER Sentiment Analysis](https://github.com/cjhutto/vaderSentiment)
- [HuggingFace Transformers](https://huggingface.co/)
- [FinBERT](https://github.com/yiyanghkust/finbert)
- [Yahoo Finance API (yfinance)](https://pypi.org/project/yfinance/)

