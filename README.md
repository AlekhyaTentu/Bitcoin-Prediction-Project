# 📊 Forecasting Bitcoin Price Trends Using Sentiment & Machine Learning

## 👨‍💻 Team C Members
- Alekhya Tentu (XX77459)
- Vaishnavi Ratheesh Nair (MQ50131)
- Adarsh Rao Akula (Jq00578)

## 🔗 Dataset Links
- [Bitcoin Price (Yahoo Finance)](https://drive.google.com/file/d/1-1GriZRFxvyLVjKk-X0rlFz1jV3JkLkl/view?usp=drive_link)
- [Wikipedia Edits](https://drive.google.com/file/d/1sbacJS3elda251tpyiE0Hw3uSoZJVc_K/view?usp=drive_link)
- [The Guardian Articles](https://drive.google.com/file/d/1--FJI3F3keB8f0UvmB-YsGeFcLfH6ZeA/view?usp=drive_link)

## 📚 Project Overview
This project combines 5+ years of Bitcoin price data with multi-source sentiment analysis to predict daily price trends and forecast future values. We extract sentiment from Wikipedia edit logs and The Guardian news articles using VADER, BERT, and FinBERT, and combine them with traditional technical indicators to enhance machine learning-based price prediction.

## 🔍 Exploratory Data Analysis (EDA)
- Bitcoin closing price with 30-day SMA reveals key price cycles.
- Article frequency spikes correlate with price surges.
- Sentiment distribution from Wikipedia and news indicates stable tone over time.
- Key indicators: RSI, MACD, Bollinger Bands, Volume.

## ⚙️ Methodology
*Approach:*
- *Classification*: Predict price movement (⬆️ increase / ⬇️ decrease)
- *Regression*: Predict actual next-day price value

*Models Used:*
- *Classification*: Logistic Regression, Random Forest, XGBoost
- *Regression*: Linear Regression, LSTM

*Features:*
- Composite sentiment from VADER + BERT
- Technical indicators (RSI, MACD, Bollinger Bands, lag features)
- Rolling sentiment statistics and volatility

## 📈 Performance & Evaluation

| Model         | Accuracy | RMSE      | Precision (⬆️) | Recall (⬆️) | F1 Score (⬆️) |
|---------------|----------|-----------|----------------|-------------|---------------|
| XGBoost       | 62%      | N/A       | 0.44           | 0.67        | 0.53          |
| Random Forest | ~61%     | N/A       | 0.45           | 0.64        | 0.52          |
| LSTM          | N/A      | ~78,000   | N/A            | N/A         | N/A           |

- LSTM captured temporal trends but underperformed without more data.
- Sentiment-augmented features improved classification model recall.
- Lag features (price t-1) were most predictive.

## 🧪 Feature Engineering Summary
- sentiment_7day, sentiment_30day, sentiment_momentum
- price_change_pct, volatility_7day, rolling_avg, etc.
- Interaction terms (e.g., sentiment_7day_x_RSI_14)

## 🛠 Future Work
- Add real-time intraday sentiment (Twitter, Reddit)
- Integrate CoinDesk, on-chain metrics
- Apply SHAP for explainability
- Deploy AWS Lambda pipeline + Streamlit dashboard

## 📁 Project Files
- 📊 Final Presentation: [DS606_TeamC_P3Final.pptx](./DS606_TeamC_Akula_Tentu_Nair_BitcoinPrediction_P3.pptx)
- 📓 Notebooks: [notebooks/](./notebooks)
- 📈 Visualizations: [images/](./images)
- 📂 Datasets: [data/](./data)
- 🧠 Scripts: [src/](./src)

## 📚 References
- Htay, H. S. et al. (2025). Enhancing Bitcoin Price Prediction with Deep Learning. Applied Sciences, 15(3), 1554.
- Pant, D. R. et al. (2018). RNN-based Bitcoin Price Prediction by Twitter Sentiment Analysis. IEEE ICCCS.
- Pano, T., & Kashef, R. (2020). VADER-based Sentiment Analysis of Bitcoin Tweets. Big Data and Cognitive Computing.

---

🔗 Visit our [GitHub Repo](https://github.com/AlekhyaTentu/Bitcoin-Prediction-Project) for full code, results, and visualizations.

