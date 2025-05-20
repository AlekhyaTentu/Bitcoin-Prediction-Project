# 📊 Bitcoin Price Prediction Using Sentiment & Machine Learning

## 👥 Team Members
- Alekhya Tentu
- Vaishnavi Ratheesh Nair
- Adarsh Rao Akula

---

## 📘 Project Overview
This project aims to forecast Bitcoin's **daily price direction (⬆️/⬇️)** and **value** using a hybrid machine learning pipeline. We integrate traditional financial indicators with **multi-source sentiment analysis** to capture emotional trends that influence crypto markets.

---

## 📂 Project Structure

| Folder        | Description                             |
|---------------|-----------------------------------------|
| `notebooks/`  | Jupyter notebooks for EDA & modeling    |
| `images/`     | Visualizations for plots and charts     |
| `data/`       | Cleaned datasets                        |
| `src/`        | Scripts for training, EDA, preprocessing|
| `Visualization/` | Uploaded images for GitHub rendering |

---

## 🔗 Data Sources

- **Bitcoin Price Data**: Yahoo Finance (5 years of OHLCV data)
- **Wikipedia Edit Logs**: Extracted using MediaWiki API
- **The Guardian News Articles**: Scraped using Guardian Open API
- All data sources were merged on date and preprocessed for alignment

---

## 🔄 Process Flow (Pipeline)

### 1️⃣ Data Collection & Cleaning
- Collected 5 years of Bitcoin data, ~1200 Wikipedia edits, and ~250 Guardian articles
- Filled missing dates and handled weekend gaps using forward fill
- Cleaned text for sentiment analysis

### 2️⃣ Exploratory Data Analysis (EDA)
- Visualized closing price trends and daily returns  
- Analyzed correlation between price and features  
📌 *(Insert: SMA Chart, Daily Returns, Correlation Heatmap)*

### 3️⃣ Sentiment Analysis
- VADER for short texts (Wikipedia edit comments)
- BERT for full-length articles (Guardian)
- Created composite scores + 7-day and 30-day rolling sentiment averages  
📌 *(Insert: Sentiment Distribution Charts)*

### 4️⃣ Feature Engineering
- Lagged prices: `Close_t-1`, `Close_t-7`
- Technical indicators: RSI, MACD, Bollinger Bands
- Sentiment momentum: `sentiment_7day - sentiment_30day`
- Interaction terms: `sentiment_7day × RSI_14`  
📌 *(Insert: Feature Importance Plot)*

### 5️⃣ Modeling
- **XGBoost Classifier** for predicting direction (⬆️ or ⬇️)
- **LSTM Regressor** for forecasting exact price
- SMOTE used to address class imbalance
- Train/test split (80/20) with 5-fold cross-validation

### 6️⃣ Evaluation
**XGBoost Results:**
- Accuracy: 62%
- Recall (UP): 0.67
- F1 Score (UP): 0.53

**LSTM Results:**
- RMSE: ~78,000
📌 *(Insert: Actual vs Predicted Chart)*

---

## 📈 Key Visualizations
- 📉 Bitcoin closing price + SMA  
- 🔥 Daily return distribution  
- 📊 Correlation heatmap  
- 💬 Sentiment feature distributions  
- 🧠 XGBoost feature importance  
- 🎯 Actual vs. Predicted price comparison  

*(You can find all images in `Visualization/` folder)*

---

## 🚀 How to Run the Project

```bash
# Clone the repository
git clone https://github.com/AlekhyaTentu/Bitcoin-Prediction-Project.git
cd Bitcoin-Prediction-Project

# Install required libraries
pip install -r requirements.txt

# Launch notebook
Jupyter notebook notebooks/final_model_pipeline.ipynb
