# 📊 Bitcoin Price Prediction Using Sentiment & Machine Learning

## 👥 Team Members
- Alekhya Tentu
- Vaishnavi Ratheesh Nair
- Adarsh Rao Akula

---

## 📘 Project Overview

This project aims to predict Bitcoin's **daily price direction (⬆️/⬇️)** and **next-day value** by integrating traditional **technical indicators** with **sentiment signals** extracted from Wikipedia edits and Guardian news articles.  
We use machine learning models such as **XGBoost** and **LSTM** in a hybrid setup to improve forecast accuracy in volatile cryptocurrency markets.

---

## 📂 Project Structure

| Folder            | Description                                     |
|-------------------|-------------------------------------------------|
| `notebooks/`      | Jupyter notebook for EDA and modeling           |
| `data/`           | Cleaned and merged datasets                     |
| `src/`            | Scripts for EDA, modeling, and utility functions|
| `Visualization/`  | Uploaded charts and key visuals used in README  |

---

## 🔗 Data Sources

- 📈 **Bitcoin OHLCV Data** – Yahoo Finance (2019–2024)
- 📰 **Guardian Articles** – ~250 articles via Guardian Open API
- 📝 **Wikipedia Edits** – ~1200 records scraped using the MediaWiki API

All datasets were time-aligned by date and forward-filled to account for weekends and missing values.

---

## 🔄 Process Flow

### 1️⃣ Data Cleaning & Preprocessing
- Filled gaps and forward-filled missing dates
- Removed outliers and cleaned sentiment text
- Merged all datasets on a common date index

### 2️⃣ Exploratory Data Analysis (EDA)

#### 📉 Bitcoin Price + 30-Day SMA
![SMA](Visualization/btc_closing_price_sma.png)

#### 📊 Daily Returns Distribution
![Returns](Visualization/daily_return_plot.png)

#### 🔥 Feature Correlation
![Heatmap](Visualization/correlation_heatmap.png)

*Lag features and rolling averages were highly correlated with target price direction.*

---

### 3️⃣ Sentiment Analysis

- Used **VADER** for short-form Wikipedia edits
- Applied **BERT** for Guardian article sentiment
- Engineered rolling 7-day and 30-day sentiment features

#### 💬 Sentiment Feature Distributions
![Sentiment](Visualization/sentiment_distributions.png)

*Composite rolling sentiment showed stronger correlation (≈0.60) with future prices than daily scores.*

---

### 4️⃣ Feature Engineering

- Lag Features: `Close_t-1`, `Close_t-7`
- Technical Indicators: RSI, MACD, Bollinger Bands
- Sentiment Features: Rolling scores, momentum
- Interaction Terms: `sentiment_7day × RSI_14`

#### ⭐ XGBoost Feature Importance
![Importance](Visualization/feature_importance.png)

---

### 5️⃣ Modeling

| Model        | Task                   | Output             |
|--------------|------------------------|--------------------|
| XGBoost      | Classification (⬆️/⬇️) | Direction          |
| LSTM         | Regression              | Next-Day Price     |

- Addressed class imbalance using **SMOTE**
- Used **80/20 train-test split** and **5-fold CV**
- Applied MinMax scaling for LSTM input

---

## 📈 Model Evaluation

### ✅ XGBoost Classifier
- Accuracy: **62%**
- Recall (UP): **0.67**
- F1 Score (UP): **0.53**

### 📉 LSTM Regressor
- RMSE: **~78,000**
- Performed well on capturing trend momentum

#### 🎯 Actual vs Predicted Price
![Prediction](Visualization/actual_vs_predicted.png)

---

## 🚀 How to Run the Project

```bash
# Clone the repository
git clone https://github.com/AlekhyaTentu/Bitcoin-Prediction-Project.git
cd Bitcoin-Prediction-Project

# Install required libraries
pip install -r requirements.txt

# Launch notebook
jupyter notebook notebooks/final_model_pipeline.ipynb
