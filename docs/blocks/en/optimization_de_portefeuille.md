---
icon: fontawesome/solid/chart-area
---

# Portfolio Optimization

## Introduction

Portfolio optimization is a method that allows investors to select assets to include in their portfolio in order to maximize their return while minimizing their risk. This approach is based on the assumption that investors are rational and seek to maximize their utility, that is, their satisfaction or profit, by making investment decisions.

There are several advanced techniques for portfolio optimization that take into account different factors such as risk, correlation between assets, liquidity, regulatory, tax or ethical constraints. Here are some of the most commonly used techniques:

* **Markowitz portfolio optimization**: This approach, proposed by Harry Markowitz in 1952, uses the efficient frontier theory to determine the optimal portfolio that offers the best expected return for a given level of risk.
* **Conditional variance portfolio optimization**: This approach allows for changes in volatility and correlation between assets over time to adjust the portfolio accordingly.
* Multi-objective optimization**: This approach considers multiple objectives, such as return, risk, and liquidity, and finds a compromise between these objectives to obtain an optimal portfolio that meets multiple criteria.
* **Robust optimization**: This approach aims to find an optimal portfolio that is resistant to disturbances and uncertainties by considering different possible scenarios.
* **AI-based portfolio optimization**: This approach uses machine learning algorithms to analyze historical financial market data and predict future trends, in order to construct an optimal portfolio that maximizes return while minimizing risk.
  
These different portfolio optimization techniques all have their advantages and limitations, and their choice depends on the specific goals and constraints of each investor.

## Mean-Variance Optimisation

* `min_volatility` optimises for minimum volatility
* `max_sharpe` optimises for maximal Sharpe ratio (a.k.a the tangency portfolio)
* `max_quadratic_utility` maximises the quadratic utility, given some risk aversion
* `efficient_risk` maximises return for a given target risk
* `efficient_return` minimises risk for a given target return

## General Efficient Frontier

### Efficient Semi-variance

* `min_semivarianc`e minimises the portfolio semi-variance (downside deviation)
* `max_quadratic_utility` maximises the "downside quadratic utility", given some risk aversion.
* `efficient_risk` maximises return for a given target semi-deviation
* `efficient_return` minimises semi-deviation for a given target return

### Efficient CVaR (The Conditional Value-at-Risk - Expected Shortfall)

* `min_cvar` minimises the CVaR
* `efficient_risk` maximises return for a given CVaR
* `efficient_return` minimises CVaR for a given target return

### Efficient CDaR (Conditional Drawdown-at-Risk)

* `min_cdar` minimises the CDaR
* `efficient_risk` maximises return for a given CDaR
* `efficient_return` minimises CDaR for a given target return

## Kelly criterion

In probability theory, the Kelly criterion is a formula that determines the optimal theoretical size for a bet. It is valid when the expected returns are known. The Kelly bet size is found by maximizing the expected value of the logarithm of wealth, which is equivalent to maximizing the expected geometric growth rate, J. L. Kelly Jr (1956). The criterion is also known as the scientific gambling method, as it leads to higher wealth compared to any other strategy in the long run (i.e. the theoretical maximum return as the number of bets goes to infinity).

## Hierarchical Risk Parity

### Definition

Portfolio construction is perhaps the most recurrent financial problem. On a daily basis, investment managers must build portfolios that incorporate their views and forecasts on risks and returns. This is the primordial question that a 24 years old Harry Markowitz attempted to answer more than 6 decades ago. His monumental insight was to recognize that various levels of risk are associated with different optimal portfolios in terms of risk-adjusted returns, hence the notion of “efficient frontier” (Markowitz, 1952). One implication was that it is rarely optimal to allocate all assets to the investments with highest expected returns. Instead, we should take into account the correlations across alternative investments in order to build a diversified portfolio. 

A correlation matrix is a linear algebra object that measures the cosines of the angles between any two vectors in the vector space formed by the returns series (see Calkin and López de Prado [2014a, 2015b]). One reason for the instability of quadratic optimizers is that the vector space is modelled as a complete (fully connected) graph, where every node is a potential candidate to substitute another. In algorithmic terms, inverting the matrix means evaluating the partial correlations across the complete graph.

Hierarchical Risk Parity[^1] (HRP) is a novel portfolio optimization method. HPR  applies modern mathematics (graph theory and machine learning techniques) to build a diversified portfolio based on the information contained in the covariance matrix. However, unlike quadratic optimizers, HRP does not require the invertibility of the covariance matrix. In fact, HRP can compute a portfolio on an ill-degenerated or even a singular covariance matrix, an impossible feat for quadratic optimizers Monte Carlo experiments show that HRP delivers lower out-of-sample variance than CLA, even though minimum-variance is CLA’s optimization objective. HRP also produces less risky portfolios out-of-sample compared to traditional risk parity methods

### Method

The HRP method consists of several key steps:

1. From a universe of assets, form a distance matrix based on the correlation of the assets
2. Using this distance matrix, cluster the assets into a tree via hierarchical clustering
3. Within each branch of the tree, form the minimum variance portfolio (normally between just two assets)
4. Iterate over each level, optimally combining the mini-portfolios at each node

The advantages of this are that it does not require the inversion of the covariance matrix as with traditional mean-variance optimization, and seems to produce diverse portfolios that perform well out of sample.

## Black-Litterman allocation

The Black-Litterman (BL) model takes a Bayesian approach to asset allocation. Specifically, it combines a prior estimate of returns with views on certain assets, to produce a posterior estimate of expected returns. It then optimises weights following a set of objectives (e.g. maximising Sharpe) and constraints.
Effective portfolio construction is the ability to transfer investment skill efficiently into positions. 

### From signals to returns: How to make signals into forecast views?

In the BL model, users can either provide absolute or relative views:

* Absolute views are statements: "asset 1 indicates a return of 10%" or "asset 2 indicates a drop of 40%"
* Relative views, on the other hand, are statements: "asset 2 indicates it will outperform asset 1 by 3%"

These views need to be provided to the model in the form of a return estimate. These estimates can be provided for either all or any subset of investables used by the model. The process of converting asset views to returns is necessary in order to be used in an optimiser.

### Confidence

The BL formula simply represents a weighted average between the prior estimate of returns and the views, where the weighting is determined by the confidence in the views

* Confidence is extracted from factor scores themselves
* Factor scores range from -1 to 1, with a score of 0 being the average or neutral value
* In a long/short strategy, 1 would be the highest confidence from the long leg and -1 would also be the highest confidence from the short leg. The closer a score is to the mean, the smaller the confidence in that score

## Black-Litterman Entropy Pooling

Additionaly, this extended version of the BL method is particularly useful when managing a top-down strategy. It consists of several key steps::

1. The Black-Litterman model is a mathematical framework for combining subjective views or forecasts with objective market data in order to generate improved portfolio weight estimates
2. The entropy pooling approach is a specific method within the Black-Litterman framework for combining multiple views, where each view is represented as a ranking of assets rather than as a specific weighting
3. In the entropy pooling approach, the subjective views are transformed into probability distributions over the set of assets, with the probability of each asset being proportional to its rank in the view
4. These probability distributions are then combined using a process called entropy pooling, which involves taking the weighted average of the individual probability distributions while minimizing the amount of uncertainty or "entropy" in the resulting combined distribution
5. The resulting combined probability distribution can then be used to generate improved portfolio weight estimates by solving a optimization problem that takes into account both the market data and the subjective views. The optimization problem can be formulated as a quadratic programming problem and solved using standard optimization techniques


[^1]: Marco Lopez de Prado, Building Diversified Portfolios that Outperform Out-of-Sample, Journal of Portfolio Management, 2016