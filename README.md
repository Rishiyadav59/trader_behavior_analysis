# Trader Performance vs. Market Sentiment Analysis
**Data Science/Analytics Intern Assignment – Round-0**

## 📌 Project Overview
This project analyzes how Bitcoin market sentiment (Fear/Greed) influences trader behavior and profitability on the Hyperliquid exchange. The goal is to uncover behavioral patterns that can inform risk management and trading strategies.

## 🛠️ Setup & Reproducibility
1. **Repository Structure**:
   - `data/`: Contains the sentiment and trader datasets.
   - `trader_sentiment_analysis.ipynb`: The primary analysis notebook.
   - `README.md`: Project summary and insights.
2. **Installation**: Ensure you have `pandas`, `numpy`, `matplotlib`, and `seaborn` installed.
3. **Running the Code**: Open the `.ipynb` file and run all cells. The code is structured to look for data in the `/data` folder.

> **Note on Datasets**: Due to GitHub's 100MB file size limit, the `historical_data.csv` has been sampled to ensure the repository remains functional and reproducible.

## 📊 Methodology
* **Data Preparation**: Converted millisecond Unix timestamps to normalized daily dates to align high-frequency trade data with the daily Fear/Greed index.
* **Metric Engineering**: Calculated Daily PnL, Win Rates, and Trade Frequency per account.
* **Segmentation**: Classified traders into 'High Frequency' vs. 'Low Frequency' segments based on median daily trade counts to identify sentiment-driven behavior shifts.

## 💡 Key Insights
1. **Sentiment Impact on PnL**: Analysis shows that average Daily PnL and Win Rates fluctuate significantly based on classification. Traders often underperform during **Extreme Greed** due to over-leveraging and FOMO-driven entries.
2. **Behavioral Shifts**: Trade frequency tends to spike during **Fear** days, indicating potential "revenge trading" or panic-closing of positions, which negatively impacts overall win rates.
3. **Segment Performance**: High-frequency traders (Scalpers) show higher sensitivity to sentiment shifts, whereas low-frequency traders maintain more consistent PnL across different market cycles.

## 🚀 Actionable Strategy Recommendations
* **Rule 1 (Risk Management)**: During **Extreme Fear** (Index < 25), implement a mandatory 30% reduction in maximum allowable position size for high-frequency segments to prevent rapid capital erosion.
* **Rule 2 (Entry Filter)**: In **Extreme Greed** (Index > 75), restrict new long entries for accounts that have realized three consecutive losses, mitigating the impact of market "exhaustion" phases.

---
**Author**: [Your Name]
**Email**: [Your Email]
