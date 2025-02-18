
# Data Files

This project relies on several datasets collected for sentiment analysis and Bitcoin price prediction. Below is a description of each data file and its contents:

### 1. `bitcoin_data_5_years.csv`

- **Description:** Contains the historical price data for Bitcoin from Yahoo Finance.
- **Columns:**
  - **Date**: The date of the recorded Bitcoin price (format: YYYY-MM-DD).
  - **Open**: The opening price of Bitcoin on that date.
  - **High**: The highest price reached by Bitcoin on that date.
  - **Low**: The lowest price of Bitcoin on that date.
  - **Close**: The closing price of Bitcoin on that date.
  - **Volume**: The total trading volume of Bitcoin on that date.
- **Source:** Yahoo Finance API (via `yfinance`).

### 2. `bitcoin_articles.csv`

- **Description:** Contains news articles related to Bitcoin, scraped from various online sources.
- **Columns:**
  - **Title**: The title of the article.
  - **URL**: The URL of the article.
  - **Snippet**: A short snippet or summary from the article.
  - **Date**: The publication date of the article (format: YYYY-MM-DD).
- **Source:** Articles scraped using SerpApi API.

### 3. `wikipedia_edits.csv` (Not yet added)

- **Description:** Contains the sentiment data derived from Wikipedia revisions related to Bitcoin.
- **Columns:**
  - **Timestamp**: The timestamp when the Wikipedia revision occurred (format: YYYY-MM-DD HH:MM:SS).
  - **Comment**: The revision comment made by users, which will be used for sentiment analysis.
  - **Sentiment**: The sentiment score calculated based on the revision comment (ranging from -1 for negative to +1 for positive).
- **Source:** Wikipedia API (via custom data scraping tool or Wikipedia dump files).

---

### How to Use These Files

1. **Data Collection**: 
   - Both `bitcoin_data_5_years.csv` and `bitcoin_articles.csv` are essential to the project. You’ll need to place them in the `data/` directory in the repository.
   - For Wikipedia data, once we include it in the project, you can download and use the `wikipedia_edits.csv` file to analyze sentiment from Wikipedia revisions.
   
2. **Integration**: These datasets are merged based on the `Date` column to combine Bitcoin price information with sentiment analysis data from the news articles and Wikipedia edits.

3. **Usage in Scripts**: The data files are read into the Python environment using `pandas`, where preprocessing and analysis are performed for machine learning model training and evaluation.

---
