# Backtesting & Statistical Testing on Cryptocurrencies

## Overview
This project explores **backtesting and statistical validation of trading strategies on cryptocurrencies**.  
The notebook implements, tests, and analyzes several rule-based trading algorithms using historical data, with the goal of identifying profitable short-term trading cycles.

## Key Features
- **Trading Strategies**  
  - A total of **five different strategies** were tested, each based on distinct selection criteria.  
  - Strategies involve:  
    - Buying with fixed capital allocation.  
    - Selling either on daily opens, intraday highs, or conditional thresholds.  
    - Different rules for selecting which ticker to trade, based on statistical indicators.  
  - Every trade is logged (date, ticker, action, price, P&L).  
  - Cumulative P&L is tracked across strategies.  

- **Selection Criteria**  
  - Cryptocurrencies are chosen according to different filters, such as:  
    - Median %daily-gap/high.  
    - Variance minimization.  
    - High-volatility filters and dynamic thresholds.  

- **Backtesting Results**  
  - Example returns across different strategies:  
    - +22% over 8 months  
    - +83% over 20 months  
    - +123% over 3 months (with optimized selection criteria)  
    - Up to **+397% in 3 months**, compared to +30% (BTC) and +163% (ETH)  

- **Parameter Optimization**  
  - Grid search for optimal thresholds (e.g., `Q1_selection ≈ 0.06`, `intraday_threshold ≈ 0.07`).  
  - Parameter tuning on shorter periods (quarterly analysis).  

- **Statistical Validation**  
  - Bootstrap simulations for robust statistics.  
  - Confidence intervals on performance metrics.  
  - Hypothesis testing:  
    - p-value < 5% (rejecting the null hypothesis).  
    - 95% CI entirely positive.  
    - **Average gain per trade: +1.67%**.  

## Structure
1. **Data Preparation** – Load and filter cryptocurrency price data.  
2. **Trading Strategies** – Implement five different rule-based strategies.  
3. **Backtesting Engine** – Simulate trades and compute cumulative returns.  
4. **Selection Criteria** – Choose tickers based on statistical features.  
5. **Performance Evaluation** – Analyze results by period (quarterly, full history).  
6. **Statistical Testing** – Bootstrap analysis, hypothesis testing, and confidence intervals.  

## Results & Insights
- The strategies strongly outperformed BTC and ETH in specific periods.  
- In May–August testing:  
  - BTC: +30%  
  - ETH: +163%  
  - **Algorithm: +397%**  
- Statistical tests confirm significance (p-value < 5%, CI > 0).  
- Performance consistency depends on volatility regimes.  
- ⚠️ Transaction costs and spreads are **not included** in these results.  

## Requirements
- Python 3.x  
- Typical data analysis stack:  
  - `pandas`  
  - `numpy`  
  - `matplotlib` / `seaborn`  
  - `scipy`  

## Usage
1. Clone the repository or download the notebook.  
2. Install dependencies.  
3. Open the Jupyter notebook and run the cells step by step.  
4. Adjust strategy parameters (e.g., thresholds) and re-run the backtests.  
