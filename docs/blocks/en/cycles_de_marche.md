---
icon: fontawesome/solid/arrows-up-down-left-right
---

# Market Cycle

Our objective is to determine and characterize different stages of market activity. Gaining insight into the analysis of market cycles, both within a given dataset and beyond, may assist in formulating optimal investment strategies.

## Introduction

While academics have focused on type I (false positive) and type II errors (false negative) for investment strategy development, they have failed to analyse changing market conditions. Investors are interested less in knowing the statistical significance of their strategies, than in knowing whether their strategy will work in the future. Whether it will work in the future is dependent on the durability of market conditions which existed while developing it. 

Phase identification enables investors to more accurately assess economic regimes through time, beyond the ongoing switch between market risk-on and off. It makes the point of new paradigm for both quant and fundamental PMs, in order to identify a cause-effect mechanism to develop a thematic and capturing asymmetrical distribution:

* Avoid all-regime strategies (Marcos Lopez de Prado, 2019)
* Allow regime-specific mean and standard deviation estimates

Maximising returns means applying the below dynamic investment approach associated with a cycle:

* **Contrarian**: When the rate of change is null (peak/trough)
    * Long risky assets as they fall
    * Short risky assets as they rise
* **Trend-following** otherwise (momentum - crowded investment styles)
    * Long risky assets as they rise
    * Short risky assets as they fall

Understanding the balance between the size of the two groups is essential for market behaviour:

* When contrarian strategies succeed for a while, they attract followers and markets may become too stable (slow to adjust to economic developments)
* Conversely, when momentum strategies succeed for a while, they attract new followers and markets may become too volatile (as such overreacting to news flows)

Excess popularity of one approach eventually results in excess gains for the opposite style, a process which over time should drive toward a balance. Therefore, long term returns should be positive (negative) only if the overall average cycle trend is upward (downward) sloping. We call this phenomenon Growth or wealth creation (destruction).

## Primer on Economic Cycles

In order to guide asset allocation decisions and allocate to industries at the optimal time, we believe the emerging markets growth cycle plays an important role. We combine top-down insights and expert bottom-up fundamental analysis to understand the dynamics and drivers that determine industry performance within the cycle. In addition, the duration of a traditional growth cycle is considered in terms of years and is often referenced in relation to the progression of credit growth and capital expenditure in a particular economy

### Business Cycle

>Business cycles are a type of fluctuation found in the aggregate economic activity of nations that organize their work mainly in business enterprises: a cycle consists of expansions occurring at about the same time in many economic activities, followed by similarly general recessions, contractions, and revivals which merge into the expansion phase of the next cycle. Burns and Mitchell (1946)

The business cycle is meant to reproduce the cycle of the global level of activity of a country. The turning points of that cycle:

* Peak “B”
* Trough “C”

are separate periods of recessions from periods of expansions.

``` mermaid
flowchart LR
  B --> C;
  C --> B;
```

Burns and Mitchell (1946) point out two main stylised facts of the economic cycle:

* Correlation among individual economic variables: Most of macroeconomic time series evolve together along the cycle
* Non-linearity: The effect of a shock depends on the rest of the economic environment. In other words, economic dynamics during economically stressful times are potentially different from normal times. For instance, small shock, such as a decrease in housing prices, can sometimes have large effects, such as recessions.

### Growth Cycle

Definition introduced by Mintz (1974):

* Fluctuations of the GDP around its long-term trend
* Absolute prolonged declines in the level of economic activity tend to be rare events, so that in practice many economies do not very often exhibit recessions in classical terms

Growth cycle turning points have a clear meaning: 

* Peak “A” is reached when the growth rate decreases below the trend growth rate 
* Trough “D” is reached when the growth rate overpasses it again

``` mermaid
flowchart LR
  A --> D;
  D --> A;
```

Those downward and upward phases are respectively named slowdown and acceleration.

!!! tips
    If the long-term trend is considered as the estimated potential level (the potential output is the maximum amount of goods and services an economy can turn out at full capacity), then the growth cycle equals the output gap.

A turning point of the output gap occurs when the current growth rate of the activity is above or below the potential growth rate, thereby signalling increasing or decreasing inflation pressures.

### ABCD approach

!!! info
    This framework improves thus the classical analysis of economic cycles by allowing sometimes two distinct phases, if the slowdown is not severe enough to become a recession, and sometimes four distinct phases, if the growth rate of the economy becomes negative enough to provoke a recession. In other words, all recessions involve slowdowns, but not all slowdowns involve recessions.

Traditional growth cycle models tend to assume a linear progression through four discrete phases within the growth cycle: 

* Recovery
* Expansion
* Slowdown
* Contraction

The ABCD approach, Anas and Ferrara (2004), refines the description of different economic phases by jointly considering the classical business cycle and the growth cycle:

* Let us suppose that the current growth rate of the activity is above the trend growth rate (acceleration phase)
* Point “A”: The downward movement will first materialize when the growth rate will decrease below the trend growth rate
* Point “B”: If the slowdown gains in intensity, the growth rate could become negative enough to provoke a recession
* Point “C”: Eventually, the economy should start to recover and exits from the recession
* Point “D”: As the recovery strengthens, the growth rate should overpass its trend. However, a slowdown will not automatically translate into a recession: if the slowdown is not severe enough to become a recession, then Point “A” will not be followed by Point “B”, but by Point “D”.

``` mermaid
flowchart LR
  A --- B & D --- C;
```

### Non-linear approach

We believe in an alternative construct, where a growth cycle consists of six phases and progresses in a non-linear fashion, with each phase playing out over approximately four-to-six months. A six-phase model can, in our view, better explain the growth narrative as well as offer a consistent framework to understanding industry returns across emerging markets equities. Our six-phase growth model — constructed using a large set of high frequency macroeconomic indicators from different emerging economies — tracks the transition across the stages of the cycle in a more consistent manner when compared to traditional models, in our view. For example, our growth model can depict the transition from the recovery phase to the expansion phase of the cycle, while also accounting for the alternative scenario that can occur when a recovery fails to take hold — as it repeatedly did in emerging markets between 2011 and 2015. Similarly, a slowdown phase does not always transition into a contraction phase per the traditional model. Our growth model accounts for periods when a slowdown is followed by a re-acceleration in growth before slowing again, as emerging markets experienced between 2004 and 2007.

``` mermaid
flowchart LR
  AD -.-> A --- B & D --- C;
  C -.-> BC;
  BC -.-> C;
  A -.-> AD;
```