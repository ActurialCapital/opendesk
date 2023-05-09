---
icon: fontawesome/solid/charging-station
---

# Regime Switching

!!! info
    Financial markets change their behavior over time, which can create periods of persistent market conditions. Time-series Classification is a general task that can be useful to identify these regime changes, using labeled training data.

Multi-label classification is a process of categorizing a given set of time interval data into multiple classes. It requires the machine to learn how to assign a class label to examples from the problem domain.

Multi-label classification is a supervised machine learning module that is used for classifying time interval data into groups. The goal is to predict the categorical class labels. A vast body of research could be implemented, on top of pre-processing features that prepare the data for modeling. In python, we implemented over 18 ready-to-use algorithms and several plots to analyze the performance of trained models (e.g. ROC curve, confusion matrix).

Regime identification can be accomplished by using either subjective knowledge and experience or a data-driven approach:

1. One method is to classify market regimes based on observable features such as volatility levels, shifts in monetary policy, and changes in investor sentiment
2. In contrast, a data-driven approach involves utilizing historical data to identify market regimes automatically, ie [the unsupervised learning page](https://www.ibm.com/topics/unsupervised-learning)

## Macro Methods


## Quantitative Methods

### Gaussian Mixture

Clustering is an unsupervised learning task that aims to identify groups of data points in a dataset that share similar characteristics. Gaussian Mixture Models (GMM) extend this approach by introducing the concept of probability, which associates a data point with a cluster in a probabilistic manner (soft clustering), unlike K-means, which uses a deterministic approach to assign data points to a single cluster (hard clustering).

GMM applies multiple Gaussian distributions to model different segments of the data. For example, financial asset returns are known to have non-normal distributions. Therefore, a GMM would fit various Gaussian distributions to capture different portions of the asset's return distribution. Each distribution would have its own attributes, such as means and volatilities, allowing the GMM to model both the center and the tails of the asset's distribution using a combination of normal distributions. This approach is particularly useful for modeling financial assets, as their return distributions often exhibit significant skewness with a meaningful number of observations in the tails.

!!! tips "Hyperparameters?"
    The only hyperparameter in the GMM is the number of clusters, which can be selected using a cross-validation approach. The log-likelihood criterion is typically used to measure the goodness-of-fit, although other criteria such as AIC and p-value can also be used. The results obtained using these alternative criteria are generally similar to those obtained using log-likelihood (McAssey, 2013).

Each period in the dataset is assumed to be independent and identically distributed. The GMM is used to identify periods where market conditions exhibit some persistence, although it has been shown that it is uncommon for one market condition to persist for extended periods without interruption from another. Short-term transient themes can emerge, and market conditions can change abruptly (as seen during the COVID market crisis in early 2020). The GMM is reactive to these changes, resulting in sudden market condition switches.

### Markov Switching Dyamic Regression

The Markov Switching Dynamic Regression model is a type of Hidden Markov Model that can be used to represent phenomena in which some portion of the phenomenon is directly observed while the rest of it is hidden. The hidden part is derived using a Markov model, while the visible portion is inferred using a suitable time series regression model in such a way that, the mean and variance of the time series regression model change depending on which state the hidden Markov model is in. This replicates Hamilton’s (1989) seminal paper introducing Markov-switching models. The model is an autoregressive model of order 4 in which the mean of the process switches between two regimes. It can be written:

### Continuous Wavelet Transform

!!! info
    Analyse the underlying process both in:

    * Time -> frequency domain
    * Scale -> Time evolution and distribution of variance

    Investigating localized intermittent oscillations in a time series.



### Band Pass Filters

### State Space Models and the Kalman Filter
