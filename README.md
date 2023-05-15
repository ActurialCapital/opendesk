<p align="right">
    <img src="https://github.com/ActurialCapital/opendesk/blob/main/docs/assets/images/opendesk-logo.png" width="30%" height="30%">
</p>


# Getting Started

This Get Started guide explains how `opendesk` works, how to install `opendesk` on your preferred operating system, and how to create your first `opendesk` strategy! 

* [Main concepts](https://acturialcapital.github.io/opendesk/getting_started/main_concepts/) introduces you to `opendesk`'s base model and development flow. You'll learn what makes `opendesk` the most powerful way to build systematic strategies, including the ability to customize existing setup. 
* [Create Blocks](https://acturialcapital.github.io/opendesk/getting_started/create_blocks/) following the three-step process outlined in `opendesk`'s core guidelines: process raw data, rank and compare these results, create and map a sequence of scores.
* [Optimize Blocks](https://acturialcapital.github.io/opendesk/getting_started/optimize_blocks/), which is the process of selecting the optimal mix of assets in a portfolio, with respect to the alpha scores, in order to maximize returns while minimizing risk. This method has been implemented to streamline the process of optimization and facilitate the integration of backtesting.
* [Backtest Blocks](https://acturialcapital.github.io/opendesk/getting_started/backtest_blocks/) through the `opendesk` API. It enables the systematic evaluation of one or multiple strategies simultaneously. It provides access to a comprehensive range of features, thereby affording users the ability to leverage its full functionality and holds significant potential for success within the financial markets.

# Documentation

This website is dedicated to providing documentation for a Python package that utilizes the "blocks" method for implementing financial strategies. This approach involves the sequential application of rule-based modular strategies that can be easily modified and added or removed from the sequence as needed. The method's effectiveness lies in its ability to generate a score for each block, enabling efficient testing and optimization, as well as facilitating research and machine learning integration. Furthermore, the method allows for the combination of various sources of alpha in a risk-efficient manner. 

The building blocks approach provides a comprehensive yet flexible means of financial strategy development and data analysis, making it an essential tool for professionals in the finance industry, whether experienced or novice.

* [Strategy](https://acturialcapital.github.io/opendesk/documentation/api/strategy/) is the main implementation of the library for portfolio construction, which initializes the execution of the sequence of blocks and allows to compute tilts/exposures, create and backtest target portfolios.
* [Signals](https://acturialcapital.github.io/opendesk/documentation/api/signals/) constructs transfomed dataset, which are used to build strategies. Examples including High Frequency Indicators, Nowcasts/Forecasts or Alpha Signals.
* [Workflow](https://acturialcapital.github.io/opendesk/documentation/api/workflow/) eliminates the need for manual resource creation and configuration, and also helps to manage the dependencies between resources. As a result, you can focus more on developing your applications that run on AWS, rather than spending time on resource management.
* [Contributing](https://acturialcapital.github.io/opendesk/documentation/api/contributing/) shows the rearch philosophy and developement guildeline.

# Installation

## Prerequisites

Before you get started, you're going to need a few things:

* Your favorite IDE or text editor
* [Python 3.10](https://www.python.org/downloads/)
* [PIP](https://pip.pypa.io/en/stable/installation/)
* Install C++:
    * **MacOS**: You need to [install XCode Command Line Tools](https://osxdaily.com/2014/02/12/install-command-line-tools-mac-os-x/). They are required to compile some of Opendesk's Python dependencies during installation.
    * **Windows**: For Windows users, [download Visual Studio](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16), with [additional instructions](https://docs.google.com/presentation/d/0B4GsMXCRaSSIOWpYQkstajlYZ0tPVkNQSElmTWh1dXFaYkJr/edit?usp=sharing&ouid=117107708911390632479&resourcekey=0-HEezB2NFstz1GjKDkroJSQ&rtpof=true&sd=true).

Opendesk is built on Python. Other dependencies, such as C++, are employed to improve the speed at which the program runs.

## Set up your virtual environment

Regardless of which package management tool you're using, we recommend running the commands on this page in a virtual environment. This ensures that the dependencies pulled in for Opendesk don't impact any other Python projects you're working on.

Below are a few tools you can use for environment management:

* [pipenv](https://pipenv-fork.readthedocs.io/en/latest/)
* [poetry](https://python-poetry.org/)
* [venv](https://docs.python.org/3/library/venv.html)
* [virtualenv](https://virtualenv.pypa.io/en/latest/)
* [conda](https://www.anaconda.com/distribution/)

## Install Opendesk

!!! note "Troubleshooting"
    If any of these methods don’t work, please [raise an issue](https://github.com/ActurialCapital/opendesk/issues) with the ‘packaging’ label on GitHub.

prior to using the below commands, you may need to follow the installation instructions for [cvxopt](https://cvxopt.org/install/index.html#) and [cvxpy](https://www.cvxpy.org/install/)).

### With Pip

Installation can be done via pip:

```console
$ pip install opendesk
```

### With Poetry

[Poetry](https://python-poetry.org/) is a relatively new kid on the block but has gained traction due to its ease of use and how it resolves several issues over Conda.

Poetry will set up your virtual environment and install all required packages with one command `poetry install`. In addition, it can build installable packages with `poetry build`, which can be installed by pip. It uses the [PEP Standard pyproject.toml](https://www.python.org/dev/peps/pep-0518/) file to define dependencies and build options for other tools (e.g. pytest arguments).

It respects `.python_version` files, uses a lock file to define specific versions of packages and pip to install them - thus, you have reproducible environments installed quickly.

The only downside is the slight learning curve in changing your workflow.

```shell
$ poetry add opendesk
```

### With Conda

If you don't have Anaconda install yet, follow the steps provided on the [Anaconda installation page](https://docs.anaconda.com/anaconda/install/windows/).

```shell
$ conda install opendesk
```


### With Git 

The alternative is to clone the project:

```shell
$ git clone https://github.com/ActurialCapital/opendesk.git
$ cd myproject
$ python setup.py install
```

# Contact

Should you be interested in our approach and latest research on quantitative analysis, please feel free to contact us to obtain more detailed information about the PRO version of the package via [LinkedIn](https://www.linkedin.com/in/j-mr/).
