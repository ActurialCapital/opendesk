---
icon: fontawesome/solid/plug
---

# Volatility Targeting

Volatility targeting is a popular technique employed by portfolio managers to manage risk by adjusting the portfolio exposure to maintain a desired level of volatility. The objective is to keep the portfolio's volatility as close as possible to the target value while ensuring that the amount of risk in dollar amount remains the same. This technique involves increasing or decreasing the amount of leverage depending on the portfolio's predefined volatility level.

Research conducted by Harvey et al.[^1] (2019) has shown that volatility targeting can improve portfolio performance, especially for riskier assets like equities and credit.

## Methods of Volatility Targeting: A Step-by-Step Introduction

To implement a volatility targeting strategy, the following steps are usually followed:

### Step 1: Capture Volatility

#### Simple Volatility

Simple volatility weights periodic returns equally, which means that simple volatility is equal to the square root of the variance, which is equivalent to the arithmetic mean of returns squared. However, the most significant disadvantage of this approach is that recent returns have the same impact on the calculated volatility level as past returns.

#### EWMA

The Equally-Weighted Moving Average (EWMA) method addresses the disadvantage of equal weighting of the Simple method by giving more weight to recent returns and less weight to past returns. The smoothing parameter $\lambda$ is introduced and adjust the decay in the series. Under this condition, instead of using equal weights, each squared return is weighted by a multiplier.

#### GARCH

The Generalized Autoregressive Conditional Heteroskedasticity (GARCH) method is autoregressive and assumes conditional heteroscedasticity. This is particularly useful as volatility tends to vary over time and depends on past variance, making a homoskedastic model suboptimal. The GARCH process depends on past squared returns and past variances to model the current variance. This model is recommended if there are repeated periods of unexplained high volatility.

### Step 2: Dynamic Volatility Scaling

To enhance the accuracy of portfolio volatility targeting, portfolio managers can use long-term data and respective long-term correlation estimates to compute volatility. This technique mainly relies on the stablility of risk contribution of each asset over time, assuming that risk estimation derived from historical data is indicative of future risk. PMs can modify exposure to each instrument in the portfolio alongside changes in volatility. However, this technique suffers from delayed reaction, and premature response could result in downside losses and additional transaction costs.

### Step 3: Volatility Switching

To address the issue in targeting portfolio volatility, volatility switching introduces a faster measure that is not implemented unless market conditions experience significant changes.

### Step 4: Momentum Filtering

!!! question "Momentum Filter"
    The momentum filter is employed to mitigate losses and reduce risk levels in unfavorable markets. This technique depends on additional observation of market return persistence, where decreasing (increasing) prices have been more likely to continue. Hence, this technique involves reducing the exposure of the portfolio in bear markets while increasing exposure in bull markets.

After scaling volatility, the momentum filter is employed to further reduce exposure in declining markets to reach a risk level lower than the target, as long as prices continue to fall. This may result in a loss of some positive returns when markets switch from a negative trend to a positive trend or vice versa. However, research suggests that it is better to miss these turning points and reduce exposure to declining markets rather than endure turbulence.

[^1]: Harvey, C. R., Hoyle, J. B., Korgaonkar, S., Rattray, S., Sargaison, M., & Van Hemert, O. (2019). The impact of volatility targeting. Journal of Portfolio Management, 45(6), 71-88.

## :material-lock: Learn More...

Should you be interested in our approach and latest research on quantitative analysis, please feel free to contact us to obtain more detailed information about the PRO version of the package via **LinkedIn**.

[LinkedIn](https://www.linkedin.com/in/j-mr/ ){ .md-button .md-button--primary target="_blank" }

