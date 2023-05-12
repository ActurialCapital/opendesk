---
icon: fontawesome/solid/network-wired
---

# Network graph

## Defintion

The correlation structure of securities is a key quantity in describing and managing the risk properties of portfolios. Relatedly, and more recently, application of network theory within financial markets has begun to provide insight into the interconnected nature of securities.

By producing a network with nodes being stocks and edges corresponding to relationship (through a distance metric), we are able to model the interconnected structure of a universe of securities. This has been shown to provide a powerful framework to investigate individual company properties in the context of others. We investigated how filtered networks (namely Minimum Spanning Trees (MST) and Planar Maximally Filtered Graphs (PMFG)) can be used to explore the diversification properties of securities. The elegance of this method is such that the networks efficiently encode complex dependency structures whilst remaining computationally tractable. We then use this to construct portfolios based on subsets of stocks with different network properties. Using similar modelling techniques, we are able to explore the network topology for our stock properties within the portfolio. These properties may be exploited in order to enhance portfolio construction methods which may be particularly useful for managed volatility strategies.

## Diversification

Risk is not uniformly spread across financial markets and this fact can be exploited to reduce investment risk within a given portfolio. By extracting the dependency structure of financial equities, a network approach can be used to build a well-diversified portfolio that effectively reduces investment risk. 

As widely accepted since Markowitz seminal work, an efficient diversification should aim to select stocks as anti-correlated as possible and remaining consistently anti-correlated over time. Identifying, from the study of historical behavior prior to the investment, baskets of stocks with a good likelihood to remain well-diversified over the future investment period is very challenging. Indeed, the structure of correlations between stocks is evolving over time and changes markedly during crises. For this reason the Markowitz approach is normally applied to a selection of stocks identified by using different criteria including the industrial sector and other macro- or micro-economic considerations. In this way, a relatively small set of stocks (typically 10 to 50) is individuated and on such 'basket' the Markowitz optimal portfolio is determined.

### Invest in Peripheral stocks? 

We hypothesise that investments in stocks that occupy peripheral, poorly connected regions in financial filtered networks are most successful in diversifying portfolios.

### Neutralize to correlation cluster? 

An industry classification is based on a similarity criterion: stocks' membership in "groups" or "clusters" such as sectors, industries, sub-industries, etc. - the nomenclature varies from one industry classification scheme to another. Commonly used industry classifications such as GICS, BICS, ICB, NAICS, SIC, etc., are based on fundamental/economic data (such as companies' products and services and more generally their revenue sources, suppliers, competitors, partners, etc.). Such industry classifications are essentially independent of the pricing data and, if well-built, tend to be rather stable out-of-sample as companies seldom jump industries. 

## The graphical lasso algorithm

### Definition

The Least Absolute Shrinkage and Selection Operator (LASSO) is a linear regression method used for both variable selection and regularization in statistical modeling and machine learning. It was introduced by Robert Tibshirani in 1996.

In linear regression, the goal is to find a linear relationship between a set of predictor variables and a response variable. However, when there are many predictor variables, some of them may be irrelevant or redundant, leading to overfitting and reduced model interpretability. The LASSO addresses this problem by imposing a penalty on the absolute values of the regression coefficients.

The key idea behind LASSO is to add a term to the ordinary least squares (OLS) objective function, which minimizes the sum of the squared differences between the predicted and actual response values. The added term, called the L1 penalty, is proportional to the sum of the absolute values of the regression coefficients multiplied by a tuning parameter (often denoted as λ).

By tuning the $\alpha$ parameter, the LASSO can shrink the coefficients of less important predictors towards zero, effectively performing variable selection. The higher the value of $\alpha$, the more coefficients are shrunk to zero, resulting in a sparser model with fewer predictors. This property makes LASSO useful in situations where feature selection or identifying the most relevant predictors is important.

Compared to other variable selection techniques, such as stepwise regression or ridge regression, LASSO has the advantage of producing sparse solutions and providing a continuous range of solutions controlled by $\alpha$. It is particularly valuable when dealing with high-dimensional datasets with many predictors and with working with network graph, which aims to differentiate connected and unconnected nodes.

In a nutshell, LASSO is a trade off between overly simplistic model and overfitting:

* Absolute Shrinkage: 
    * Performs L1 regularization, i.e. adds a factor equivalent to the sum of absolute value of the magnitude of coefficients
    * Agnostic to feature definition: Choose minimum magnitude = minimum sum of squared value among all models 
    * Minimization objective: , where  refers to the residual sum of squares, i.e. the linear regression objective without regularization, and   the actual regularization coefficient
    * Optimized: The data reconstruction error is balanced with the regularization penalty
    * Coordinate descent (derivative-free optimization algorithm) is used to find a local minimum 
* Selection: 
    * It shrinks coefficients to exactly zero and act as a feature selector within independent variable (as it uses the absolute value – Ridge regression for instance, uses squared value, which push all values to be different than 0) 
    * Regularization:  provides a trade-off between balancing residual sum of squares and magnitude of coefficients:
        * $\alpha = 0$: Same coefficients as simple linear regression 
        * $\alpha = \inf$: All coefficients are zero 
        * $0 < \alpha < \inf$: coefficients between 0 and that of simple linear regression

### Why LASSO?

| Method                                                       | Financial Market characteristics                                |
|--------------------------------------------------------------|-----------------------------------------------------------------|
| Efficient with high multicollinearity                        | High variance                                                   |
| Efficient with large number of features                      | High Correlation                                                |
| Identify independent variables                               | High Collinearity (independent variables are highly correlated) |
| Minimize the error between predicted and actual observations | Need to identify idiosyncratic risk, factor risk                |


## Fast Unfolding of Communities in Large Networks

!!! warning 
    The quality of the partitions resulting from these methods is often measured by the so-called modularity of the partition. The modularity of a partition is a scalar value between -1 and 1 that measures the density of links inside communities as compared to links between communities. 

Social, technological and information systems can often be described in terms of complex networks that have a topology of interconnected nodes combining organization and randomness. The typical size of large networks such as social network services, mobile phone networks or the web now counts in millions when not billions of nodes and these scales demand new methods to retrieve comprehensive information from their structure. A promising approach consists in decomposing the networks into sub-units or communities, which are sets of highly inter-connected nodes. 

The identification of these communities is of crucial importance as they may help to uncover a-priori unknown functional modules such as topics in information networks or cyber-communities in social networks. Moreover, the resulting meta-network, whose nodes are the communities, may then be used to visualize the original network structure.

The problem of community detection requires the partition of a network into communities of densely connected nodes, with the nodes belonging to different communities being only sparsely connected. Precise formulations of this optimization problem are known to be computationally intractable. 

Several algorithms have therefore been proposed to find reasonably good partitions in a reasonably fast way. This search for fast algorithms has attracted much interest in recent years due to the increasing availability of large network data sets and the impact of networks on every day life. One can distinguish several types of community detection algorithms: 

* Divisive algorithms detect inter-community links and remove them from the network
* Agglomerative algorithms merge similar nodes/communities recursively
* Optimization methods are based on the maximisation of an objective function

## Other Application

| Network theory                                                               | financial markets                                       |
|------------------------------------------------------------------------------|---------------------------------------------------------|
| Degree distribution                                                          | How information spreads                                 |
| Propagation, contagion, disease                                              | Stress tests                                            |
| Weighted degree, Intensity                                                   | Direct relationship(s) from an asset to another         |
| Paths, diameter: Geodesic distance, weighted degree proportion, transitivity | Indirect relationship(s) from an asset to another       |
| Centrality measures: Eigen, Betweeness                                       | Drivers, correlation/idiosyncratic risk                 |
| Clustering methods, community structure                                      | Classifications/attribution/similarities between assets |
| Random network formation                                                     | Change in market behavior                               |

## :material-lock: Learn More...

Should you be interested in our approach and latest research on quantitative analysis, please feel free to contact us to obtain more detailed information about the PRO version of the package via **LinkedIn**.

[LinkedIn](https://www.linkedin.com/in/j-mr/ ){ .md-button .md-button--primary target="_blank" }

