# Machine-Learning Equity Selection & Backtesting

Python 机器学习量化选股与回测项目。

## Workflow
- Download adjusted prices and volume through yfinance for 45 US stocks across 9 sectors.
- Clean missing observations, align weekly Friday timestamps, and construct 11 backward-looking features.
- Use chronological training, 26-week validation and 104-week out-of-sample test periods.
- Compare Logistic Regression (with StandardScaler in a Pipeline) and Random Forest.
- Refit monthly using an expanding window and rank next-week positive-return probabilities.
- Build equal-weight long top-20% / short bottom-20% portfolios; account for drifted turnover and transaction costs.
- Apply a 10% annualised volatility target; assess Sharpe Ratio, drawdown, cost sensitivity and benchmark performance.

## Results and limitations
The supplied report records 21,825 modelling observations. At the base 5 bps one-way cost, net annualised returns were -0.97% (Logistic Regression) and -12.41% (Random Forest); neither beat SPY or the equal-weight benchmark. The fixed current-constituent universe introduces survivorship bias. This is a research workflow, not a demonstrated profitable trading system.

## Run
Install Python dependencies: `pip install numpy pandas yfinance scikit-learn matplotlib ipython jupyterlab`.
Open `equity_backtesting.ipynb` in Jupyter and run sequentially. Internet access is required to download market data. The notebook creates tables and charts under `outputs/`.

Saved cell outputs and execution metadata were cleared for publication. Code syntax was checked, but the full market-data download and model/backtest pipeline were not rerun during publication. Data revisions and dependency versions may affect reproduced results.
