# Documentation

This website is dedicated to providing documentation for a Python package that utilizes the "blocks" method for implementing financial strategies. This approach involves the sequential application of rule-based modular strategies that can be easily modified and added or removed from the sequence as needed. The method's effectiveness lies in its ability to generate a score for each block, enabling efficient testing and optimization, as well as facilitating research and machine learning integration. Furthermore, the method allows for the combination of various sources of alpha in a risk-efficient manner. 

The building blocks approach provides a comprehensive yet flexible means of financial strategy development and data analysis, making it an essential tool for professionals in the finance industry, whether experienced or novice.

***

<div class="result" markdown>

![Strategy](../assets/images/flaticon_6.png){ align=left width=80 }

[Strategy](./api/strategy/index.md) is the main implementation of the library for portfolio construction, which initializes the execution of the sequence of blocks and allows to compute tilts/exposures, create and backtest target portfolios.
</div>

***

<div class="result" markdown>

![Signals](../assets/images/flaticon_7.png){ align=left width=80 }

[Signals](./api/signals/index.md) constructs transfomed dataset, which are used to build strategies. Examples including High Frequency Indicators, Nowcasts/Forecasts or Alpha Signals.
</div>

***