# 📊 Forecasting Bitcoin Price Trends Using Sentiment & Machine Learning

> *DS606 Final Project – Team C*

---

## 👨‍💻 Team Members
- **Alekhya Tentu** (XX77459)  
- **Vaishnavi Ratheesh Nair** (MQ50131)  
- **Adarsh Rao Akula** (Jq00578)

---

## 🔗 Dataset Sources
- 📈 [Bitcoin Price (Yahoo Finance)](https://drive.google.com/file/d/1-1GriZRFxvyLVjKk-X0rlFz1jV3JkLkl/view?usp=drive_link)
- 📝 [Wikipedia Edit Logs](https://drive.google.com/file/d/1sbacJS3elda251tpyiE0Hw3uSoZJVc_K/view?usp=drive_link)
- 🗞️ [The Guardian News Articles](https://drive.google.com/file/d/1--FJI3F3keB8f0UvmB-YsGeFcLfH6ZeA/view?usp=drive_link)

---

## 📚 Project Overview

We explore whether **public sentiment**, extracted from Wikipedia and news, can improve predictions of **Bitcoin price movements**.

Our pipeline includes:
- 5+ years of historical Bitcoin price data
- Sentiment scoring using **VADER**, **BERT**, and **FinBERT**
- Technical indicators: RSI, MACD, Bollinger Bands
- Classification & Regression modeling: **XGBoost**, **Random Forest**, **LSTM**

---

## 🔍 Exploratory Data Analysis (EDA)

- 📉 30-day SMA reveals key price cycles  
- 📰 News & Wikipedia article frequency spikes align with volatility  
- 😐 Sentiment distributions remain stable but shift near price shocks  
- 📈 Key indicators: RSI, MACD, Bollinger Bands, Volume  

> 🔎 See outputs in: [📂 Visualization Folder](./Visualization)

---

## ⚙️ Methodology

### 🧭 Approach
- **Classification** → Will the price go ⬆️ or ⬇️ tomorrow?
- **Regression** → Predict the actual next-day price value

### 🧠 Models Used
- **Classification**: Logistic Regression, Random Forest, XGBoost  
- **Regression**: Linear Regression, LSTM

### 📊 Features
- Composite sentiment (VADER + BERT)
- Technical indicators: RSI, MACD, Bollinger Bands, price lags
- Rolling sentiment stats: 7-day, 30-day, momentum
- Interaction terms: e.g., `sentiment_7day × RSI_14`

---

## 📈 Performance & Results

| Model         | Accuracy | RMSE      | Precision (⬆️) | Recall (⬆️) | F1 Score (⬆️) |
|---------------|----------|-----------|----------------|-------------|---------------|
| **XGBoost**       | 62%      | N/A       | 0.44           | 0.67        | 0.53          |
| **Random Forest** | ~61%     | N/A       | 0.45           | 0.64        | 0.52          |
| **LSTM**          | N/A      | ~78,000   | N/A            | N/A         | N/A           |

✅ Sentiment-augmented features increased **recall and trend detection**  
⚠️ LSTM captured patterns but underperformed without sufficient data  
📌 Lag features (e.g., price_t-1) were top predictors

---

## 🧪 Feature Engineering Summary

- `sentiment_7day`, `sentiment_30day`, `sentiment_momentum`  
- `price_change_pct`, `volatility_7day`, `rolling_avg`  
- Interaction terms: `sentiment_7day × RSI_14`, `MACD × price_lag_1`  

---

## 🚀 Future Work

- Integrate **real-time intraday sentiment** (Twitter, Reddit)
- Add **CoinDesk** headlines & **on-chain metrics** (e.g., hash rate)
- Use **SHAP** for interpretability of news impact
- Deploy with **AWS Lambda** & **Streamlit** dashboard

---

## 📁 Project Files

| Type             | File/Folder                                                                 |
|------------------|------------------------------------------------------------------------------|
| 📊 Presentation  | [DS606_TeamC_P3Final.pdf](./Presentation%20files/DS606_TeamC_Akula_Tentu_Nair_BitcoinPrediction_P3.pdf) |
| 📓 Code Notebook | [final_code_file - google_Colab.pdf](./Code/final_code_file%20-%20google_Colab.pdf) |
| 📂 Visualizations | [Visualization/](./Visualization)                                           |
| 📂 Datasets      | [data/](./data)                                                              |

---

## 📚 References

- **Htay, H. S. et al.** (2025). *Enhancing Bitcoin Price Prediction with Deep Learning.* Applied Sciences, 15(3), 1554.  
- **Pant, D. R. et al.** (2018). *RNN-based Bitcoin Price Prediction by Twitter Sentiment Analysis.* IEEE ICCCS.  
- **Pano, T., & Kashef, R.** (2020). *Sentiment Analysis of Bitcoin Tweets.* Big Data and Cognitive Computing.

---

## 🔗 GitHub Repository

> Visit the full project here:  
👉 [github.com/AlekhyaTentu/Bitcoin-Prediction-Project](https://github.com/AlekhyaTentu/Bitcoin-Prediction-Project)
