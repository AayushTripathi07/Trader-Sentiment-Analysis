# Trader Performance vs Market Sentiment Analysis

## Objective

The objective of this project is to analyze how **market sentiment (Fear vs Greed)** influences trader behavior and profitability on the Hyperliquid trading platform. The goal is to identify behavioral patterns, evaluate trader performance under different sentiment conditions, and generate actionable strategy recommendations.

This project includes data cleaning, feature engineering, exploratory analysis, trader segmentation, and predictive modeling.

---

## Datasets Used

### 1. Bitcoin Market Sentiment Dataset
This dataset provides daily market sentiment classification.

**Columns:**
- date – Trading date
- classification – Market sentiment category (Fear, Greed, Neutral, Extreme Fear, Extreme Greed)
- value – Sentiment score

---

### 2. Hyperliquid Historical Trader Dataset
This dataset contains detailed trader-level transaction records.

**Columns include:**
- Account – Trader identifier
- Coin – Cryptocurrency traded
- Execution Price – Trade price
- Size USD – Trade size in USD
- Side – Buy or Sell
- Timestamp IST – Timestamp of trade
- Closed PnL – Profit or loss from trade
- Fee – Transaction fee
- Trade ID, Order ID, Transaction Hash – Identifiers

---

## Methodology

### Step 1: Data Cleaning and Preparation

- Removed duplicate records
- Checked and handled missing values
- Converted timestamp columns to proper datetime format
- Extracted daily trading data
- Merged trader data with sentiment data using date alignment

---

### Step 2: Feature Engineering

Created key performance and behavioral metrics:

- Daily PnL per trader
- Win rate per trader
- Trade frequency per day
- Average trade size
- Previous day PnL
- Rolling 3-day average PnL
- Rolling volatility
- Market sentiment encoding

These features help capture trader consistency, performance trends, and behavioral patterns.

---

### Step 3: Exploratory Data Analysis

Generated visualizations to understand behavior under different sentiment regimes:

- PnL Distribution vs Market Sentiment
- Trade Frequency vs Market Sentiment
- Trade Size vs Market Sentiment

These visualizations help identify how trader behavior changes during Fear and Greed periods.

---

### Step 4: Trader Segmentation

Traders were segmented into behavioral categories:

- Winners vs Losers (based on total profitability)
- Frequent vs Infrequent traders
- High vs Low activity traders

This helps identify profitable trader archetypes.

---

### Step 5: Predictive Modeling

Built a machine learning model to predict trader profitability using engineered features.

**Model Used:**
Gradient Boosting Classifier

**Features Used:**

- Previous day PnL
- Rolling average PnL
- Trade frequency
- Trade size
- Transaction fees
- Market sentiment

**Validation Method:**
Time-based split was used to avoid data leakage and simulate real-world trading prediction.

---

## Key Insights

- Trader profitability varies across sentiment regimes.
- Trading frequency increases during Fear and Extreme Fear periods.
- Trade size increases during strong sentiment conditions.
- Trader profitability shows temporal persistence — past performance is predictive of future performance.
- Market sentiment significantly influences trader behavior and activity levels.

---

## Strategy Recommendations

Based on analysis, the following strategies are recommended:

1. Reduce leverage and risk exposure during Fear periods due to increased volatility.
2. Use trend-following strategies during Greed periods where trends are stronger.
3. Follow historically profitable traders and avoid consistently losing traders.
4. Adjust trading frequency dynamically based on market sentiment.

---

## Model Performance

Model performance metrics are available in:

output/model_metrics.txt


The model uses historical performance and behavioral features along with sentiment to predict profitability.

---

## Project Structure

project/
│
├── trader_sentiment_analysis.py
├── README.md
│
├── output/
│ ├── charts/
│ │ ├── pnl_vs_sentiment.png
│ │ ├── trade_frequency_vs_sentiment.png
│ │ ├── trade_size_vs_sentiment.png
│ │
│ ├── daily_pnl.csv
│ ├── win_rate.csv
│ ├── trade_frequency.csv
│ ├── sentiment_summary.csv
│ ├── trader_segments.csv
│ ├── features.csv
│ ├── model_metrics.txt
│ ├── summary.txt


---

## How to Run

### Install dependencies

pip install pandas numpy matplotlib seaborn scikit-learn


### Run the script

python trader_sentiment_analysis.py


The output folder will be generated automatically with all results.

---

## Reproducibility

This project is fully reproducible. All data preprocessing, feature engineering, analysis, and modeling steps are included in the main script.

---

## Conclusion

This analysis demonstrates that market sentiment has a strong influence on trader behavior and profitability. Historical performance combined with sentiment and behavioral metrics can effectively predict trader outcomes and support better trading decisions.

---

## Author

Aayush Tripathi  
B.Tech Computer Science and Engineering  
Bennett University
