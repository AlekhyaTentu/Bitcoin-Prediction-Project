# 📊 Bitcoin Price Prediction Using Sentiment Analysis and Machine Learning

## 👨‍💻 Team Members
- Alekhya Tentu
- Vaishnavi Ratheesh Nair
- Adarsh Rao Akula

---

## 📘 Project Overview

This project aims to forecast Bitcoin's daily price *direction and value* using a hybrid machine learning approach. We combine *market-based technical indicators* and *public sentiment* from news articles and Wikipedia edits to improve prediction accuracy.

---

## 📂 Project Structure

| Folder        | Description                             |
|---------------|-----------------------------------------|
| notebooks/  | Jupyter notebooks with EDA and models   |
| images/     | Graphs and visualizations               |
| data/       | Cleaned and merged datasets             |
| src/        | Python scripts for modeling and EDA     |

---

## 🔗 Data Sources

- *Bitcoin Price*: Yahoo Finance (5 years of OHLCV data)
- *Wikipedia Edits*: Extracted using Wikipedia API
- *The Guardian Articles*: Collected via Guardian Open API

Each dataset was aligned by date, cleaned, and merged for sentiment scoring and model input.

---

## 🧪 Exploratory Data Analysis (EDA)

We started with 5 years of daily Bitcoin price data and explored volatility and sentiment.

### 📈 Bitcoin Price with 30-Day SMA  
![Bitcoin Price SMA](images/page_8_img_1.png)

### 📉 Daily Returns  
![Daily Returns](images/page_9_img_1.png)

### 🔥 Feature Correlation Heatmap  
![Heatmap](images/page_10_img_1.png)

These graphs revealed strong autocorrelation in price and motivated inclusion of *RSI, **MACD, and **Bollinger Bands*.

---

## 💬 Sentiment Analysis

We analyzed textual sentiment using:
- *VADER* for short Wikipedia edit comments
- *BERT* for full Guardian article text

We computed daily *composite sentiment scores* and created *rolling 7-day and 30-day averages*.

### 🧠 Sample Sentiment Distributions  
![Sentiment Features](images/page_21_img_1.png)

Rolling sentiment had *0.60 correlation* with next-day price, significantly improving model features.

---

## ⚙️ Feature Engineering

We created:
- Lagged closing prices (e.g., Close_t-1, Close_t-7)
- Technical indicators: RSI, MACD, Bollinger Bands
- Sentiment features: 7-day, 30-day, momentum
- Interaction terms: sentiment_7day × RSI_14

### 🔍 Feature Importance (XGBoost)  
![Feature Importance](images/page_136_img_1.png)

---

## 🤖 Models Used

| Model        | Task               | Type         |
|--------------|--------------------|--------------|
| XGBoost      | Direction Prediction (⬆️ / ⬇️) | Classification |
| LSTM         | Price Forecasting   | Regression   |

---

## 📈 Model Results

### ✅ XGBoost Classification
- Accuracy: *62%*
- Precision (UP): 0.44
- Recall (UP): 0.67
- F1 Score (UP): 0.53

### 📉 LSTM Regression
- RMSE: ~78,000

---

### 📊 Actual vs Predicted Price  
![Actual vs Predicted](images/page_124_img_1.png)

XGBoost outperformed in directional accuracy, while LSTM captured broader momentum.

---

## 🔮 Future Improvements

- Add *real-time sentiment* (Twitter, Reddit)
- Use *on-chain metrics* (e.g., exchange inflow/outflow)
- Apply *SHAP* for explainability
- Build a *stacked ensemble* (LSTM + XGBoost)
- Deploy using *AWS Lambda + Streamlit*

---

## 🚀 How to Run

```bash
# Clone the repo
git clone https://github.com/AlekhyaTentu/Bitcoin-Prediction-Project.git
cd Bitcoin-Prediction-Project

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter
jupyter notebook notebooks/final_model_pipeline.ipynb
