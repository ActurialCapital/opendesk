---
icon: fontawesome/solid/angles-down
---

# Nowcasting

## Introduction

!!! info
    Nowcasting involves predicting the current state of the economy, such as GDP, inflation, or OECD leading indicator, based on an estimation of the present and the immediate future.

Nowcasting utilizes statistical techniques to provide early and short-term predictions for key quarterly indicators such as GDP growth, CPI, and OECD leading indicators. These indicators are typically published with significant delay, making timely forecasting a crucial task. The models used for Nowcasting must be able to handle the mixed frequency of the available data, which includes both monthly and weekly measurements. For example, the first official publication of the eurozone's GDP estimate, known as the "flash estimate," is typically released six weeks after the end of the reference quarter.

Nowcasting is important for institutions such as central banks or portfolio managers as it enables them to make investment and economic policy decisions based on information that is available more quickly.

This approach also allows investors to make more accurate real-time evaluations of economic regimes and adjust their portfolios more swiftly in response to changing market conditions.

When it comes to real-time economic evaluation, direct measures are generally more reliable, as they are not contingent on lagging statistical relationships. Short-term forecasting techniques are also more accurate than long-term ones, as they facilitate a quicker adaptation to changing market conditions, prompt identification of inflection points, and hence play a crucial role in risk management.

## Models

!!! tip "Aggregated Predictions: Bridge Equations, Dynamic Factor Models and MIDAS"
    Targeted indicators are obtained by multiplying the output of the model with estimated coefficients. The aggregated forecasts are derived by either averaging individual predictions or by using weighting techniques to assign more weight to the most significant relationships.

### Bridge Equations

The "bridge equations" method can be implemented using various econometric techniques, including regression, principal component analysis (PCA), and time series modeling. It is widely used by central banks and economic research institutes to provide real-time forecasts and quick estimates of the state of the economy.

This method typically involves three main steps:

* **Selection of high-frequency economic indicators (HFI)**: HFI refers to economic data that are available in almost real-time, often with only a few days or weeks lag, such as retail sales, industrial orders, consumption data, or business confidence indicators. These indicators are used to capture real-time economic fluctuations and are considered leading indicators of future economic trends
* **Construction of statistical relationships**: The relationships between the target economic indicators (such as GDP, inflation, or retail sales) and HFI are established using econometric models such as regression or factor analysis. These models allow for the identification of statistical relationships between high-frequency economic indicators and target economic indicators with a time lag. The term "bridge" refers to the relationships that bridge the gap between the high-frequency indicators and target indicators
* **Aggregation of forecasts**: Statistically significant indicators are aggregated

The "bridge equations" method is considered particularly useful in periods of economic volatility or uncertainty, where traditional economic indicators may be insufficiently responsive or delayed relative to real-time economic developments.

### Dynamic Factor Models

!!! info
    Dynamic factor models postulate that a small number of unobserved "factors" can be used to explain a substantial portion of the variation and dynamics in a larger number of observed variables. 

    A "large" model typically incorporates hundreds of observed variables. Estimating dynamic factors is similar to a dimension-reduction technique, producing estimates of the unobserved factors.

The "dynamic factor models" (DFM) framework for nowcasting is another widely-used econometric method for producing real-time estimates of economic indicators. The DFM approach is based on the use of large high-frequency economic databases and economic activity indicators summarized by dynamic factors.

The DFM method consists of several main steps:

* **Selection of economic variables**: The economic variables used for constructing factors are typically chosen based on their economic relevance and correlation with the target economic indicator. The economic variables used may include production, consumption, investment, employment, foreign trade, business and household confidence data, etc
* **Construction of dynamic factors**: Dynamic factors are constructed using statistical techniques, which allow the dimensionality of the data to be reduced by extracting the common information of a large number of economic variables into a few dynamic factors. Dynamic factors are thus synthetic variables that summarize the common movements of the economic variables
* **Estimation of regression equations**: Regression equations are used to link dynamic factors to target economic indicators. Regression equations can be estimated using various econometric techniques, such as linear regression or time series modeling
* **Production of forecasts**: Forecasts are produced by combining the forecasts of the factors with the estimated coefficients

The DFM method allows for the significant reduction of data dimensionality by using synthetic dynamic factors that summarize the common movements of numerous economic variables. This approach is also useful for forecasting, as it enables the capture of complex economic relationships that may exist between various indicators.

### MIDAS

The "Mixed Data Sampling" (MIDAS) model for nowcasting is another widely used econometric method for producing near-real-time estimates of economic indicators by using economic data of different frequencies, such as monthly, quarterly, and annual data.

The MIDAS method involves several key steps:

* **Selection of economic variables**: Economic variables to be used in the MIDAS model construction are typically selected based on their economic relevance and correlation with the target economic indicator. The economic variables used can include production, consumption, investment, employment, foreign trade, business and household confidence data, etc
* **Specification of the MIDAS model**: The MIDAS model is specified using transfer functions that combine economic information at different frequencies. These transfer functions describe how economic data at different frequencies are related to the target economic indicator
* **Estimation of model parameters**: The parameters of the MIDAS model are estimated using econometric techniques such as linear regression or time series modeling. The estimated coefficients in the model are used to produce forecasts for the target economic indicator
* **Production of forecasts**: Forecasts are produced using the estimated coefficients in the MIDAS model and economic data available at different frequency levels
  
The MIDAS method allows for the exploitation of information available at different frequencies to produce timely forecasts for an economic indicator.

### SVAR

The Structural VAR (SVAR) model is an econometric analysis method used for causal analysis and macroeconomic forecasting. The SVAR model uses a system of simultaneous linear equations to model causal relationships between multiple economic variables.

The SVAR method consists of several key steps:

* **Model Specification**: The SVAR model is specified by identifying relevant economic variables and constructing a system of simultaneous equations to model their causal relationships. Economic variables can include indicators such as GDP, inflation, unemployment rate, interest rates, etc.
* **Estimation of Model Parameters**: The parameters of the SVAR model are estimated using econometric techniques such as the generalized method of moments or maximum likelihood method. The estimated coefficients in the model are used to produce forecasts for economic variables.
* **Causality Analysis**: The SVAR model allows for the analysis of causality between economic variables using structural shocks. Structural shocks are exogenous events that affect a particular economic variable. Using the estimated coefficients in the model, it is possible to analyze the impact of these shocks on other economic variables in the model.
* **Forecast Production**: Forecasts are produced using the estimated coefficients in the SVAR model and available economic data. Forecasts can be adjusted using techniques such as smoothing or filtering to produce more accurate forecasts.
  
The SVAR method allows for the modeling of complex causal relationships between economic variables. The method is also useful for policy analysis as it allows for the analysis of the impact of policy changes on the economy as a whole.

## Conclusion

Each nowcasting model has its own set of strengths and weaknesses:

* Bridge equations models are useful for their flexibility and ability to model nonlinear relationships.
* Dynamic factor models are often used for their ability to capture real-time information on financial markets and economic indicators. However, they can be sensitive to changes in the relationships between economic variables and prone to larger errors during extreme variability (as evidenced by the Federal Reserve Bank of Atlanta's "GDPNow" indicator, which experienced significant forecasting errors during the COVID-19 period).
* MIDAS models have the advantage of being able to use high-frequency data to produce more accurate forecasts. However, their complexity can make them more challenging to use.
* SVAR models are often used for their ability to model complex causal relationships between economic variables. But, their use of structural shocks can make their forecasts more sensitive to changes in initial assumptions.

We have developed several econometric methods that aim to produce quasi-real-time estimates of economic indicators. We believe that multiple methods are necessary to meet the constraints of each client, obtain a more comprehensive picture of the current and future economic situation, and to reduce model risk.