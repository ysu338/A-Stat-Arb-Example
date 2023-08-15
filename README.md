# A Stat-Arb Example

### Tradable Universe:
- Constituents in Russell 3000 with customized liquidity filters, leading to approx. 2000 stocks every month
- The tradable universe is ***Point-in-time*** and ***survivorship bias - free***

### Signal Constructions:



### Risk Model:
- For a total of $N$ stocks, the risks are modeled by a factor model (# of factors = $K$):\
  $ V = D + F\PhiF^T $ \
  where $V$ is a $N$ X $N$ modeled variance-covariance matrix,\
  $D$ is a diagonal matrix that contains idiosyncratic risks,\
  $F$ is a $N$ X $K$ factor loading matrix,\
  and $\Phi$ is a $K$ X $K$ factor covariance matrix.
  
- that is based on principal components extracted using a short lookback of daily returns
- 

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
