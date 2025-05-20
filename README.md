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
| `src/`            | Python scripts (optional modular components)    |
| `Visualization/`  | Uploaded charts and key visuals used in README  |

---

## 🔗 Data Sources

- 📈 **Bitcoin OHLCV Data** – Yahoo Finance (2019–2024)
- 📰 **Guardian Articles** – ~250 scraped using The Guardian Open API
- 📝 **Wikipedia Edits** – ~1200 records from Bitcoin-related pages

All data was cleaned, merged by date, and forward-filled to account for non-trading days in sentiment streams.

---

## 🔄 Process Flow

### 1️⃣ Data Cleaning & Preprocessing
- Filled missing timestamps, removed duplicates.
- Forward-filled sentiment gaps for non-trading days (weekends/holidays).

### 2️⃣ Exploratory Data Analysis (EDA)

#### 📉 Bitcoin Price + 30-Day SMA
![SMA](Visualization/btc_closing_price_sma.png)

#### 📊 Daily Returns Distribution
![Returns](Visualization/daily_return_plot.png)

#### 🔥 Feature Correlation
![Heatmap](Visualization/correlation_heatmap.png)

*Key Insight*: Lagged price (`Close_t-1`) had ~0.99 correlation with `tomorrow_price`, supporting its inclusion as a strong predictor.

---

### 3️⃣ Sentiment Analysis

- VADER applied to short Wikipedia edit comments.
- BERT used for full-length Guardian articles.
- Daily sentiment scores were averaged and converted to rolling 7-day and 30-day signals.

#### 💬 Sentiment Feature Distributions
![Sentiment](Visualization/sentiment_distributions.png)

*Insight*: Rolling sentiment scores had a **higher correlation (~0.60)** with price movement than raw daily sentiment.

---

### 4️⃣ Feature Engineering

- **Lag Features**: `Close_t-1`, `Close_t-7`
- **Technical Indicators**: RSI, MACD, Bollinger Bands
- **Sentiment**: 7-day, 30-day averages, momentum (`s7 - s30`)
- **Interaction Terms**: `sentiment_7day × RSI_14`

#### ⭐ XGBoost Feature Importance
![Importance](Visualization/feature_importance.png)

---

### 5️⃣ Modeling Approach

| Model        | Task                   | Output             |
|--------------|------------------------|--------------------|
| XGBoost      | Classification (⬆️/⬇️) | Price Direction    |
| LSTM         | Regression              | Next-Day Price     |

- Applied **SMOTE** to balance classes for XGBoost.
- Used **80/20 train-test split** and **5-fold CV** for validation.

---

## 📈 Model Evaluation

### ✅ XGBoost Classifier
- Accuracy: **62%**
- Recall (UP): **0.67**
- F1 Score (UP): **0.53**

### 📉 LSTM Regressor
- RMSE: **~78,000**
- Captured price momentum but underperformed due to volatility.

#### 🎯 Actual vs Predicted Price
![Prediction](Visualization/actual_vs_predicted.png)

---

## 🚀 How to Run the Project

```bash
# Clone the repository
git clone https://github.com/AlekhyaTentu/Bitcoin-Prediction-Project.git
cd Bitcoin-Prediction-Project

# Install required packages
pip install -r requirements.txt

# Launch the final notebook
jupyter notebook notebooks/final_model_pipeline.ipynb
