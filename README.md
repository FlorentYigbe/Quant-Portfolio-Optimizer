# Quant Portfolio Optimizer

A quantitative portfolio optimizer built in Python, applied to a diversified universe of 10 global assets across equities, fixed income, and commodities.

## Method

Monte Carlo simulation (10,000 portfolios) maps the efficient frontier and identifies the **Max Sharpe** and **Min Variance** allocations. Risk is evaluated through historical VaR/CVaR (95% and 99%) and maximum drawdown. To avoid look-ahead bias, optimization is performed exclusively on the training window (2016–2022); weights are then frozen and evaluated out-of-sample (2023–2026).

## Results

| Metric | In-sample | Out-of-sample | Equal-weight (OOS) |
|--------|-----------|---------------|--------------------|
| Ann. Return | 25.61% | 33.01% | 25.39% |
| Ann. Volatility | 19.24% | 16.69% | 13.52% |
| Sharpe Ratio | 1.12 | 1.74 | 1.58 |
| Max Drawdown | −27.29% | −16.40% | −13.75% |

## Stack

Python · NumPy · pandas · yfinance · matplotlib · seaborn

## Structure

| Notebook section | Description |
|-----------------|-------------|
| Data collection | 10 years of adjusted prices via yfinance |
| Asset metrics | Annualized return, volatility, correlation heatmap |
| Monte Carlo | 10,000 random portfolios, efficient frontier |
| Portfolio metrics | Max Sharpe vs Min Variance vs Equal-Weight |
| VaR & CVaR | Historical simulation at 95% and 99% |
| Max drawdown | Peak-to-trough loss, Calmar ratio |
| Train / test split | Out-of-sample validation (2023–2026) |

---
*Academic project — BSc Wirtschaftsmathematik, Universität Mannheim, 2026.  
Results are historical backtests and do not constitute investment advice.*
