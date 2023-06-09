---
icon: fontawesome/solid/charging-station
---

# Regime Switching

## Definition

!!! info
    Financial markets change their behavior over time, which can create periods of persistent market conditions. Time-series Classification is a general task that can be useful to identify these regime changes, using labeled training data.

Multi-label classification is a process of categorizing a given set of time interval data into multiple classes. It requires the machine to learn how to assign a class label to examples from the problem domain.

Multi-label classification is a supervised machine learning module that is used for classifying time interval data into groups. The goal is to predict the categorical class labels. A vast body of research could be implemented, on top of pre-processing features that prepare the data for modeling. In python, we implemented over 18 ready-to-use algorithms and several plots to analyze the performance of trained models (e.g. ROC curve, confusion matrix).

Regime identification can be accomplished by using either subjective knowledge and experience or a data-driven approach:

1. One method is to classify market regimes based on observable features such as volatility levels, shifts in monetary policy, and changes in investor sentiment
2. In contrast, a data-driven approach involves utilizing historical data to identify market regimes automatically and probabilistically, ie the [unsupervised learning page](https://www.ibm.com/topics/unsupervised-learning)

This article focuses a the latter.

## Probabilistic Methods

### Classification: Gaussian Mixture Models

Clustering is an unsupervised learning task that aims to identify groups of data points in a dataset that share similar characteristics. Gaussian Mixture Models (GMM) extend this approach by introducing the concept of probability, which associates a data point with a cluster in a probabilistic manner (soft clustering), unlike K-means, which uses a deterministic approach to assign data points to a single cluster (hard clustering).

GMM applies multiple Gaussian distributions to model different segments of the data. For example, financial asset returns are known to have non-normal distributions. Therefore, a GMM would fit various Gaussian distributions to capture different portions of the asset's return distribution. Each distribution would have its own attributes, such as means and volatilities, allowing the GMM to model both the center and the tails of the asset's distribution using a combination of normal distributions. This approach is particularly useful for modeling financial assets, as their return distributions often exhibit significant skewness with a meaningful number of observations in the tails.

!!! tips "Hyperparameters?"
    The only hyperparameter in the GMM is the number of clusters, which can be selected using a cross-validation approach. The log-likelihood criterion is typically used to measure the goodness-of-fit, although other criteria such as AIC and p-value can also be used. The results obtained using these alternative criteria are generally similar to those obtained using log-likelihood (McAssey, 2013).

Each period in the dataset is assumed to be independent and identically distributed. The GMM is used to identify periods where market conditions exhibit some persistence, although it has been shown that it is uncommon for one market condition to persist for extended periods without interruption from another. Short-term transient themes can emerge, and market conditions can change abruptly (as seen during the COVID market crisis in early 2020). The GMM is reactive to these changes, resulting in sudden market condition switches.

A Gaussian Mixture is a function that is comprised of several Gaussians, each identified by $k ∈ {1,…, K}$, where $K$ is the number of clusters of our dataset. Each Gaussian  in the mixture is comprised of the following parameters:

* A mean $\mu$ that defines its centre
* A covariance $\sum$ that defines its width. This would be equivalent to the dimensions of an ellipsoid in a multivariate scenario
* A mixing probability $\pi$ that defines how large the Gaussian function is

For instance, in a three Gaussian functions, $K=3$, each Gaussian explains the data contained in each of the three clusters available. The mixing coefficients are themselves probabilities and equates to 1, such as 

$$
\sum_{k=1}^{K} \pi_k = 1
$$

To optimize these parameters, each Gaussian fits the data points belonging to each cluster through maximum of likelihood.

!!! tips
    GMM model answers the question: “Given a data point $x$, what is the probability it came from Gaussian $k$?”

The Expectation — Maximization (EM)  is widely used for optimization problems where the objective function has complexities in the derivation process.

Let the parameters of our model be $\theta = \{\pi, \mu, \sum\}$

1. Initialise $\theta$: For instance, we can use the results obtained by a previous K-Means run as a good starting point for our algorithm
2. Expectation step: Evaluate the probability the data point come from Gaussian $k$ by maximum of likelihood, which is the result of calculating the joint probability of all observations and latent variables and is an extension of our initial derivations for $p(x)$
3. Maximization step: Find the revised parameters in order to fin a local maximum

### Regression: Markov Switching Models

The Markov Switching Dynamic Regression model is a type of Hidden Markov Model that can be used to represent phenomena in which some portion of the phenomenon is directly observed while the rest of it is hidden. The hidden part is derived using a Markov model, while the visible portion is inferred using a suitable time series regression model in such a way that, the mean and variance of the time series regression model change depending on which state the hidden Markov model is in. 

This replicates Hamilton’s (1989) seminal paper introducing Markov-switching models. The model is an autoregressive model of order 4 in which the mean of the process switches between two regimes. It can be written such as:

$y_t = \mu_{S_t} + \phi_1 (y_{t-1} - \mu_{S_{t-1}}) + \phi_2 (y_{t-2} - \mu_{S_{t-2}}) + \phi_3 (y_{t-3} - \mu_{S_{t-3}}) + \phi_4 (y_{t-4} - \mu_{S_{t-4}}) + \varepsilon_t$

Each period, the regime transitions according to the following matrix of transition probabilities:

$$
\begin{split} P(S_t = s_t | S_{t-1} = s_{t-1}) =
\begin{bmatrix}
p_{00} & p_{10} \\
p_{01} & p_{11}
\end{bmatrix}\end{split}
$$

where $p_{ij}$ is the probability of transitioning from regime $i$, to regime $j$.

We will look at a general specification of the model consisting of a time indexed dependent variable $y$, a matrix of regression variables $X$, a fitted vector of coefficients $\hat{\beta}$ and residual errors $\epsilon$:

* Dependent variable $y$: Let $y$ be a $[n x 1]$ vector of $n$ time-indexed observations 
* Regression variable matrix $X$: Let $X$ be an $[n x (m+1)]$ matrix of regression variables
  * The first column is for the intercept
  * $x_t$ is one row of this matrix
* Fitted regression coefficients $\hat{\beta}$: Let $\hat{\beta}$ be an $[(m+1) x 1]$ vector of regression coefficients. $\hat{\beta}$ indicates that it is the fitted value of the coefficient produced from training the model

We now consider the following general specification of a time series model containing an additive error component:

$$
y_t=\hat{\mu}_t + \epsilon_t
$$

In the above model, the observed value $y_t$ is the sum of the predicted value $\hat{\mu}_t$ and the residual error $\epsilon_t$. We further assume that $\epsilon_t \sim N(0, σ^2)$ is a homoskedastic (constant variance) normally distributed random variable with a zero mean.

Training of the MSDR model involves estimating the coefficients matrix $\hat{\beta}_s$, the transition matrix $P$ and the variance $\sigma^2$ of the dependent variable $y$. The estimation procedure is usually Maximum Likelihood Estimation (MLE) or Expectation Maximization. Please see [state space models and the Kalman filter](./state_space_models_and_the_kalman_filter.md) on the MLE algorithm.

We’ll illustrate MLE which finds the values of $P$, $\hat{\beta}_s$ and $\sigma^2$ that would maximize the joint probability density of observing the entire training data set $y$. In other words, we would want to maximize the following product:

$$
L(\hat{\beta}_s; \sigma^2 P | y) = \prod_{t=1}^{n} f(y=y_t)
$$

## Application to Financial Decision

These data-driven approaches propose a learning technique that employs a significant volume of historical data to identify and determine regimes. The resulting model output encompasses four clusters, or market conditions, which have been labeled as:

1. Crisis
2. Steady State
3. Inflation
4. Walking on Ice (WOI) 

Based on their respective characteristics.
In order to identify periods of persistent market conditions, an analysis of their behavior throughout history was conducted. We found multiple potential applications for allocators:

* **Risk management** stands as one such application, as allocators can enhance their portfolio scenario analysis by sampling from the distributions of these identified market conditions, thereby subjecting their portfolios to stress tests
* Another application is related to **asset allocation decisions**. Predicting market returns over extended periods of time proves challenging, even in stable market conditions. The findings presented provide evidence of rapidly changing market conditions, thereby making it even more difficult to rely on long-term forecasts. Consequently, allocators may need to design portfolios capable of withstanding market condition volatility in the long run, while also considering opportunities for tactical shifts on shorter time horizons.

## :material-lock: Learn More...

Should you be interested in our approach and latest research on quantitative analysis, please feel free to contact us to obtain more detailed information about the PRO version of the package via **LinkedIn**.

[LinkedIn](https://www.linkedin.com/in/j-mr/ ){ .md-button .md-button--primary target="_blank" }

