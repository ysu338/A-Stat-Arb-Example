![](/Cum_Ret.png)

### The Universe:
- Constituents within Russell 3000 with customized liquidity filters (minimum price, minimum ADV, etc.),
  leading to approx.2000 eligible stocks for every month.
- The eligible stocks are updated monthly.
- The universe is ***point-in-time*** and free of ***survivorship bias***

### Signal Constructions:


### Risk Model:
- The risk of the stocks in the tradable universe is modeled by a factor model
- The model is based on principal components extracted using a short lookback of daily returns
- It combines information in industry classification at different granularity

### Portfolio Optimization:
- Simulated long-short portfolios with weights derived from ***single-period*** optimization in maximizing Sharpe ratio
- The optimization is constrained quadratic programming with inputs from signal constructions and the risk model
- The constraints include:
  * Dollar neutrality
  * Long/short matching on sector weights 
  * Long/short matching on weights based on size buckets
  * Factor loading (derived from the risk model) matching
  * Weight range ( -1.5% to +1.5%)
  * liquidity constraints (turnover, maximum average daily dollar volume percentage .etc) are not included
