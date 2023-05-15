# opendesk

## Getting Started

This Get Started guide explains how `opendesk` works, how to install `opendesk` on your preferred operating system, and how to create your first `opendesk` strategy! 

[Getting Started](./getting_started/index.md){ .md-button .md-button--primary }

***

<div class="result" markdown>

![Main concepts](./assets/images/flaticon_2.png){ align=left width=80 }

[Main concepts](./getting_started/main_concepts.md) introduces you to `opendesk`'s base model and development flow. You'll learn what makes `opendesk` the most powerful way to build systematic strategies, including the ability to customize existing setup. 

</div>

***

<div class="result" markdown>

![Create Blocks](./assets/images/flaticon_3.png){ align=left width=80 }

[Create Blocks](./getting_started/create_blocks.md) following the three-step process outlined in `opendesk`'s core guidelines: process raw data, rank and compare these results, create and map a sequence of scores.

</div>

***

<div class="result" markdown>

![Optimize Blocks](./assets/images/flaticon_4.png){ align=left width=80 }

[Optimize Blocks](./getting_started/optimize_blocks.md), which is the process of selecting the optimal mix of assets in a portfolio, with respect to the alpha scores, in order to maximize returns while minimizing risk. This method has been implemented to streamline the process of optimization and facilitate the integration of backtesting.
</div>

***

<div class="result" markdown>

![Backtest Blocks](./assets/images/flaticon_5.png){ align=left width=80 }

[Backtest Blocks](./getting_started/backtest_blocks.md) through the `opendesk` API. It enables the systematic evaluation of one or multiple strategies simultaneously. It provides access to a comprehensive range of features, thereby affording users the ability to leverage its full functionality and holds significant potential for success within the financial markets.
</div>

***

<div class="result" markdown>

![Installation](./assets/images/flaticon_1.png){ align=left width=80 }

[Installation](./getting_started/installation.md) helps you set up your virtual environment and walks you through installing `opendesk` on Windows, macOS, and Linux. Regardless of which package management tool and OS you're using, we recommend running the commands on this page in a virtual environment.

</div>

***

## Documentation

This website is dedicated to providing documentation for a Python package that utilizes the "blocks" method for implementing financial strategies. This approach involves the sequential application of rule-based modular strategies that can be easily modified and added or removed from the sequence as needed. The method's effectiveness lies in its ability to generate a score for each block, enabling efficient testing and optimization, as well as facilitating research and machine learning integration. Furthermore, the method allows for the combination of various sources of alpha in a risk-efficient manner. 

The building blocks approach provides a comprehensive yet flexible means of financial strategy development and data analysis, making it an essential tool for professionals in the finance industry, whether experienced or novice.

[Documentation](./documentation/index.md){ .md-button .md-button--primary }

***

<div class="result" markdown>

![Strategy](./assets/images/flaticon_6.png){ align=left width=80 }

[Strategy](./documentation/api/strategy/index.md) is the main implementation of the library for portfolio construction, which initializes the execution of the sequence of blocks and allows to compute tilts/exposures, create and backtest target portfolios.
</div>

***

<div class="result" markdown>

![Signals](./assets/images/padlock.png){ align=left width=80 }

[Signals](./api/signals/index.md) constructs transfomed dataset, which are used to build strategies. Examples including High Frequency Indicators, Nowcasts/Forecasts or Alpha Signals.
</div>

***

<div class="result" markdown>

![Workflow](./assets/images/padlock.png){ align=left width=80 }

[Workflow](./api/workflow/index.md/) eliminates the need for manual resource creation and configuration, and also helps to manage the dependencies between resources. As a result, you can focus more on developing your applications that run on AWS, rather than spending time on resource management.
</div>

***