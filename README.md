# Bitcoin Trader Performance vs Fear-Greed Sentiment

This project analyzes the relationship between **Bitcoin trader performance** and **market sentiment** (Fear-Greed Index). It merges trade history data from **Hyperliquid** with a daily sentiment index to uncover patterns that can inform better trading strategies.

## 📂 Datasets

### 1. Fear & Greed Index Dataset
- **Columns:** `timestamp`, `value`, `classification`, `date`
- Example classifications: `Fear`, `Greed`, `Neutral`

### 2. Historical Trader Data
- **Columns:** `Account`, `Coin`, `Execution Price`, `Size Tokens`, `Size USD`, `Side`, `Timestamp IST`, `Start Position`, `Direction`, `Closed PnL`, `Transaction Hash`, `Order ID`, `Crossed`, `Fee`, `Trade ID`, `Timestamp`
- Contains detailed trade executions and performance metrics.

## 🚀 Features
- Cleans and standardizes datasets.
- Merges trade data with daily sentiment.
- Computes aggregated performance metrics (PnL, volume, leverage).
- Visualizes relationships between sentiment and trader activity.
- Performs rolling correlation analysis between PnL and sentiment.
- Runs statistical tests to check significance between Fear and Greed performance.

## 📊 Output Files
All results are saved in the `outputs/` folder:
- **`merged_data.csv`** – Trade-level dataset with sentiment info.
- **`summary_metrics.csv`** – Aggregated performance metrics by sentiment.
- **`direction_counts.csv`** – Counts of long vs short positions by sentiment.
- **`daily_aggregates.csv`** – Daily aggregated PnL and sentiment.
- **Charts:**
  - `pnl_by_sentiment.png`
  - `volume_by_sentiment.png`
  - `leverage_by_sentiment.png`
  - `direction_by_sentiment.png`
  - `rolling_corr.png`

## 📦 Installation
```bash
# Clone this repository
git clone https://github.com/AgarwalBhavya/bitcoin_trade_sentiment_analysis.git
cd bitcoin_trade_sentiment_analysis

# (Optional) Create a virtual environment
python -m venv venv
source venv/bin/activate  # On Windows use venv\Scripts\activate

```

## 🛠 Usage
1. Place your CSV files in the project root:
   - `fear_greed.csv`
   - `historical_trader.csv`
2. Run the script:
```bash
python bitcoin_trader_sentiment_analysis.py
```
3. Check the `outputs/` folder for CSVs and PNG charts.

You can also provide custom file paths:
```bash
python bitcoin_trader_sentiment_analysis.py path/to/fear_greed.csv path/to/historical_trader.csv
```

## 📈 Example Insights
- Do traders earn more in **Fear** or **Greed** markets?
- Does leverage usage change based on sentiment?
- Are traders more likely to go long or short in different sentiment conditions?
- How correlated is average sentiment to rolling PnL over time?

## 🧪 Statistical Testing
The script performs a **two-sample t-test** comparing PnL during Fear vs Greed days to assess if differences are statistically significant.

## 📜 License
MIT License — feel free to use and adapt.

## 🤝 Contributing
Pull requests are welcome! If you find a bug or want to improve the analysis, open an issue or submit a PR.
