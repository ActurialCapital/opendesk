---
icon: fontawesome/solid/temperature-arrow-down
---

# Short Interests Models

## Introduction

Short selling is a trading strategy that involves selling a security that the seller does not possess or has not yet delivered. The process typically involves borrowing the security from a lender, who typically charges a fee for the transaction. It is important to note that many academic studies rely on the assumption that short selling can be done at low cost and without any constraints. The ability to short sell securities is an essential factor in empirical asset pricing research.

### Securities lending factors and composite models

Several studies suggest that individuals who engage in short selling tend to possess significant market information. Consequently, these studies argue that short-interest data can be leveraged to predict the underperformance of stocks relative to the broader market. We have extended this approach by developing a set of signals that rely on securities lending data. Our analysis demonstrates that these signals are highly effective for selecting stocks across multiple markets. 

We have constructed two composite models that employ different techniques to weight the signals. The first model employs a simple, static schedule while the second model utilizes a dynamic machine learning algorithm. Both models generate consistent alpha, exhibit slow signal decay, and have low portfolio turnover across all markets.

### Traditional factors and cost of borrow

Based on our analysis, we have discovered that a significant number of conventional investment factors experience reduced performance owing to the elevated borrowing expenses related to heavily shorted stocks. We have demonstrated that a straightforward modification on the long side can alleviate much of this shortfall. Additionally, we have exhibited how our collection of security lending indicators can be utilized to amplify traditional factors, leading to improved performance and decreased risk.

## IHS Markit data

Our research introduces the Markit Securities Finance (MSF) database, which offers a broad scope of the global securities lending market. The vendor collects data directly from prominent market participants such as custodians, prime brokers, asset managers (e.g., hedge funds), and other financial intermediaries.

The MSF dataset encompasses over $16 trillion of global securities in lending programs across more than 20,000 institutional funds. It is worth highlighting that the securities lending market operates over-the-counter (OTC), hence the availability of information is limited and fragmented.

### Data 

!!! warning 
    It is important to acknowledge that the data presented poses a challenge in that historical quantities are not adjusted for corporate actions such as stock splits. As a result, there may be inconsistencies around corporate actions due to the data being sourced from thousands of institutions.

The MSF global equity data has a starting point of 2002, with data frequency being monthly during the early years and transitioning to daily from 2006 onwards. The coverage is comprehensive for most developed markets and moderate (with an improving trend) for emerging markets. In our research, the global all-cap research universe (Russell 3000 in the US, S&P/TSX composite in Canada, and S&P BMI in other regions) demonstrates close to 100% coverage in the US, Canada, UK, ANZ, and Japan, with more than 80% coverage in other regions. MSF data is collected daily and reports transactions two days after the settlement date, leading to a two-day lag in the data.

The MSF database provides data on both the value and quantity basis (e.g., the actual dollar value of short interest and the actual number of shares shorted). We predominantly use quantity-based factors as they tend to be more consistent across countries and over time.

### Factors

We create a comprehensive set of factors for stock selection on a global scale, which cover different aspects of the securities lending market. 

* Demand (e.g., Days to Cover): Conventionally, investors rely primarily on the demand side of the securities lending market, i.e., short interest. Because short sellers are more likely to be informed traders, stocks with high short interest (normalized by number of shares outstanding, float, or average daily trading volume) are expected to underperform the market
* Supply (e.g., Lendable Inventory): One of the drawbacks of using only the demand side is that it ignores the supply side of the securities lending market which can be captured by the available inventory of lendable stock. Not all outstanding shares are available for borrow. The lendable inventory is loosely related to institutional ownership, because institutional investors are more likely to lend securities for a fee as opposed to retail investors who tend to be averse to stock lending. If we assume institutional investors are more sophisticated and/or better informed, the supply side of the securities lending market may also have predictive power of future stock returns
* Supply-demand (e.g., Utilization): Obviously, we can combine the demand and supply sides to form a more complete picture of short sentiment. A natural measure for the supply side of the securities lending market is the utilization factor, which is simply the ratio of short interest and available inventory. Since the lendable inventory is collected from a large number of providers and consolidated by IHS Markit, the inventory data is not necessarily always up-to-date. IHS Markit makes adjustments for small or inactive positions to derive the so-called active inventory, which is further used to compute active utilization
* Cost (e.g., Cost-of-Borrow): Borrow cost (e.g., wholesale cost of borrow scores and value weighted average fees) reflects both demand and supply sides of the securities lending market. Stocks that are heavily shorted tend to have high borrow costs. Similarly, securities with limited supply (for lending) are also expected to be expensive to borrow. Although stocks with high short interest are more likely to underperform, it is expensive to short these firms which makes profiting from this information more complicated. This is the classic “limits to arbitrage” argument in the academic finance literature. One of the benefits of the borrow cost data is that it can be used to more accurately quantify the alpha/cost trade-off associated with short interest strategies. We can also take advantage of our factors even without shorting, by removing them from the long side, albeit significantly limited our ability to explore the short side
* Other categories of data: IHS Markit also provides other data that can be used to quantify other themes such as sentiment or risk. For example, changes in utilization can reflect stock level sentiment across short sellers

## Country aggregation

### Lendable inventory and short interest

The Active Beneficiary Owner (BO) Inventory is a measure of available inventory or supply of lendable shares that are active (i.e., not stale). The level of short interest is higher in the US, Canada, and UK, compared to emerging markets like LATAM and merging EMEA, where short selling is more restricted. The availability of inventory is an important factor to consider when analyzing factor efficacy in emerging markets such as LATAM, EMEA, and AxJ, where the stock lending market is less developed and short selling regulations are often more restrictive. In such markets, short interest may not accurately reflect true demand, due to limited supply and regulatory constraints. In many emerging markets, shorting is too expensive and/or limited in scale for arbitrageurs, and regulators may clamp down on short selling at the first sign of a market downturn.

### Cost of borrow

The DCBS score provided by IHS Markit serves as a proxy for the cost and difficulty to borrow a stock. It ranges from 1 (easy and cheap to borrow) to 10 (nearly impossible and very expensive to borrow). In the US, almost 90% of stocks have a DCBS score of one, which implies that those stocks are cheap and easy to borrow. In emerging markets such as LATAM, EMEA, and Asia ex Japan, the cost of borrow can be particularly high for a significant number of stocks. However, the number of easy-to-borrow stocks is trending higher across almost all markets. It's important to note that since the exact cost of borrow may not always be available or precise, the DCBS score is used as a proxy.

### Utilization

Utilization and active utilization are ratios that capture the demand for borrowing stocks. Utilization is the ratio of Short Interest and Beneficial Owner Inventory, while Active Utilization is based on Short Interest and Active Beneficial Owner Inventory. Utilization is a measure of the percentage of available inventory of a stock that is being borrowed by short sellers. Active utilization is similar, but it considers only active inventory, which is inventory that has been actively lent out or borrowed against.

The level of utilization can be influenced by both supply and demand factors. In developed markets, utilization levels can be associated with general market sentiment. For example, utilization levels rose globally during the lead-up and peak of the 2008 financial crisis and descended back towards more moderate levels as financial markets normalized. The observable spikes in European utilization after the financial crisis are related to episodic crises driven by a series of problems with peripheral countries within the union.

There are meaningful differences in utilization levels between developed and emerging markets. Data coverage for LATAM is poor, and utilization data does not become available until 2010 for AxJ and EMEA. In emerging markets, shorting is often too costly and/or too limited in scale for arbitrageurs, and regulators are more likely to restrict short selling at the first sign of market downturn. Thus, short interest may not represent true demand in these markets, and utilization may not be a reliable proxy for sentiment.

## Sector aggregation

During the 2008 financial crisis in the US, there was a significant rise in short interest across all sectors classified under the Global Industry Classification Standard (GICS). Consumer Discretionary, Financials, and Real Estate sectors experienced the most substantial increases in short interest, which was followed by sharp reversals. Similarly, during Q3 2014, the Energy sector witnessed a significant surge in short interest, primarily due to a decline in crude oil prices. Short interest also remained relatively high in the health care sector. Although the information technology sector had historically high valuation levels, its active utilization remained subdued. This pattern of short interest increase during market selloffs and decrease during market rallies was observed across various developed markets at the GICS sector level. Does this indicate that short sellers exacerbate a market selloff by opportunistically participating in a market crash?

## Market aggregation

!!! info
    The market-level short interest signal is strong at predicting market return at longer horizons of semi-annual and annual returns. Together these results suggest that short sellers, as a group, can be used as a signal to anticipate for macroeconomic changes and emerging trends in market directions. Short interest based variables also seem to perform better than other popular market timing predictors (Rapach, et al, 2014).

Given the ease of borrowing and shorting most stocks in the US, it is possible to use market-level short interest signals for market timing analysis. Contrary to patterns observed in the cross-sectional analysis, total short interest tends to move in a countercyclical manner. Although aggregated short selling is primarily a trend-following strategy, it has limited potential to stabilize the market. Aggregate short interest is positively associated with the prior month's declines, indicating that short sellers are trend-followers during market downturns. In contrast, during market rallies, short sellers tend to be less aggressive in selling. Our findings suggest that aggregated short interest (Active Utilization) at the market level can predict future market returns. The regression analysis shows that the T-statistics of the predictor variable (Active Utilization) are significant at -1.9, with a p-value of 5.7%. These statistics remain significant even after accounting for heteroscedasticity and autocorrelation using the Newey-West (1987) estimator.

## To Be Continued

Should you be interested in our approach and latest research on quantitative analysis, please feel free to contact us to obtain more detailed information about the PRO version of the package via **LinkedIn**.

[LinkedIn](https://www.linkedin.com/in/j-mr/ ){ .md-button .md-button--primary target="_blank" }

