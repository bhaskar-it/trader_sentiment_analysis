# Trader Sentiment Analysis – Hyperliquid x Bitcoin Fear/Greed Index

This project is part of a Data Science assignment to explore the relationship between market sentiment and trader behavior using real trading data from Hyperliquid and the Bitcoin Fear & Greed Index.<br>

---

## Objective

To analyze whether market sentiment (Fear or Greed) has an influence on trading behavior and profitability.  
The project aims to:<br>

- Merge and analyze two datasets: trader logs and sentiment index
- Engineer meaningful features like profit ratios and flags
- Discover patterns across sentiments and symbols
- Generate actionable insights to guide smarter trading strategies
- (Optional) Build a predictive model for trade success

---

## Datasets Used

### 1. `historical_data.csv` (From Hyperliquid)
- `Account`, `Symbol`, `Execution Price`, `Size USD`, `Side`, `Timestamp IST`
- `Start Position`, `Event`, `Closed PnL`, `Leverage`, etc.

### 2. `fear_greed_index.csv` (Bitcoin Market Sentiment)
- `Date`, `Classification` (values: Extreme Fear, Fear, Neutral, Greed, Extreme Greed)

---

##  Key Steps

### 🔹 Data Preprocessing
- Converted timestamp to `datetime`
- Cleaned and typed financial metrics (`Size USD`, `Closed PnL`)
- Merged both datasets using `date` field

### 🔹 Feature Engineering
- `pnl_per_usd`: Profit per dollar invested
- `is_profitable`: Boolean flag whether a trade earned profit
- One-hot encoded or grouped sentiment if needed for modeling

### 🔹 Exploratory Analysis
- Trader performance grouped by sentiment type
- Symbol-wise PnL across sentiment classes
- Visual insights using bar plots and heatmaps

### 🔹 Insights Export
- Summarized statistics to CSV files (`sentiment_summary.csv`, etc.)
- Cleaned merged dataset for further modeling or reporting<br>

---

## Visual Insights

Here are a few highlights from the analysis:
|-----------------------------------------------------|---------------------------------------------------------------------|<br>
|                       Insight                       | Description                                                         |<br>
|-----------------------------------------------------|---------------------------------------------------------------------|<br>
|  Greed correlates with higher profitability         | Average `Closed PnL` is noticeably higher on `Greed` days           |<br>
|  Profitability rate varies with sentiment           | Proportion of winning trades is higher during `Neutral` and `Greed` |<br>
|  Symbol performance differs per sentiment           | Certain coins (symbols) perform better under specific market moods  |<br>
|  Low correlation between trade size and success     | Bigger trades do not necessarily lead to higher returns             |<br>
|-----------------------------------------------------|---------------------------------------------------------------------|<br>
---

## (Optional) Predictive Modeling

A Logistic Regression model can be added to predict `is_profitable` based on:
- `Size USD`
- `Leverage`
- `Sentiment (encoded)`
- `Coin/Symbol`

Metrics to include:
- Accuracy
- Confusion Matrix
- Feature Importance

Let me know if you want to include this!

---

## Technologies Used

|-------------------------|------------------------------|<br>
|          Tool           |         Purpose              |<br>
|-------------------------|------------------------------|<br>
| `Python`                | Programming Language         |<br>
| `Pandas`                | Data manipulation            |<br>
| `Matplotlib`, `Seaborn` | Visualizations               |<br>
| `Jupyter Notebook`      | Interactive coding           |<br>
| `Git & GitHub`          | Version control & submission |<br>
|-------------------------|------------------------------|<br>
---

## How to Run

```bash
# 1. Clone the repo or download files
git clone https://github.com/bhaskar-it/trader_sentiment_analysis.git

# 2. Install dependencies
pip install -r requirements.txt

# 3. Launch Jupyter Notebook
jupyter notebook trader_sentiment_analysis.ipynb
