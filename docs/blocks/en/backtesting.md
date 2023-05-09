---
icon: fontawesome/solid/bolt-lightning
---

# Backtesting

Backtesting is a complex process that requires a deep understanding of investment concepts and programming. It involves testing a trading strategy using historical data to simulate transactions and evaluate the strategy's performance. 

Building a trading backtester involves gathering historical market data, defining trading rules, creating algorithms to execute these rules, avoiding data leaks, and generating performance results that take into account transaction costs.

## Algorithmic Trading

Our trading algorithms, which execute trading rules, are developed in Python. Defining the trading rules is a key element in setting up a trading backtester. The rules can also include macro or fundamental events such as earnings announcements, interest rate changes, or changes in economic policy.

## Performance Measurement

!!! question "Path-Dependent Backtesting"
    Path-dependent portfolio rebalancing refers to a portfolio rebalancing strategy in which the decision to rebalance the portfolio is dependent on the historical path of the portfolio's performance. Instead of rebalancing the portfolio at fixed intervals or based on predefined rules, the rebalancing decision is based on the path the portfolio has taken in the past. This approach takes into account the dynamic nature of financial markets and the nonlinearities in portfolio returns, and aims to improve the portfolio's risk-return tradeoff by adjusting the portfolio allocation in response to market conditions. In backtesting, it can be simulated by using historical data to test the performance of different rebalancing strategies based on the portfolio's path.

Commonly used performance measures include return rate, Sharpe ratio, and maximum drawdown, among others. These measures allow for the evaluation of trading strategy performance and path-dependent optimization based on generated performance.
