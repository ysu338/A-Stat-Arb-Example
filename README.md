![](/Cum_Ret.png)

The figure shows backtested results for a StatArb strategy. The return analytics are for 2-to-1 leverage (1 long and 1 short) portfolios.

### The Universe:
- The universe consists of constituents within the Russell 3000, carefully selected through customized liquidity filters,
  including criteria such as minimum price and minimum average daily volume (ADV). These filters result in approximately 2,000 eligible stocks every month.
- The list of eligible stocks is refreshed on a monthly basis.
- The universe is ***point-in-time*** and free of ***survivorship bias***.

### The Signals:
- Constructed multiple signals using historical prices and returns.
- Used time series and signal processing techniques to generate expected returns for each stock at each point in time.
- Employed a signal combination approach grounded in the principle of maximum entropy.
- The strategy leverages daily returns over various time periods.

### The Risk Model:
- Constructed a factor-based risk model for the tradable universe by extracting principal components from short-term daily returns.
- This model incorporates industry classifications at various levels of granularity.

### Portfolio Construction:
- Simulated long-short portfolios by driving weights using ***single-period*** optimizations to maximize Sharpe ratio.
- The number of stocks held in the backtest portfolios on either the long or short side is approx. 1000.
- It is a constrained optimization leveraging inputs from the constructed signal and the risk model.
- The constraints include:
  * Dollar neutrality
  * Long/short legs matching on sector weights 
  * Long/short legs matching on weights based on size buckets
  * Factor loading (derived from the risk model) matching
  * Position weights range ( -1.5% to +1.5%)
  * Liquidity constraints (turnover, maximum average daily dollar volume, etc.) are not included
- Note:
  * The illustration above does not include considerations on t-cost (not in obj. func nor constraints)
  * Real-world returns may vary depending on the execution quality
