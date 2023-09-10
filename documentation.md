# Project Ideation

## Overview

We can think about quantitative trading as a method of maximizing or optimizing expected return while maintaining a certain level of volatility or variability within our portfolio. 

As a result, our overarching strategy will be to determine the optimal allocation of investments using analysis of historical data as well as a strategy centered around the Kelly Fraction and the Sharpe Ratio. This will be used as a baseline to be compared to more flexible trading models.

Finally, to get introduced to quantitative trading, we will reduce volatility by investing in stock indexes rather than individual investments. These include international indexes, national indexes, and industry-specific indexes.


### Technical & Strategical Details

Our baseline model will be centered around a fixed portfolio oriented around the optimal portfolio allocated determined by the Kelly Fraction.

The rest of the models will abide by a fixed volatility, determined by the portfolio volatility equation (square root of portfolio variance), and then use various machine learning models to optimize returns.

The machine learning models are as follows:
1. Moving Average Trading - changing portfolio allocations based on patterns discovered within short-term changes in average closing price
2. Cross-Sectional Momentum Trading - changing portfolio allocations by selling negative-trending stocks and buying positive-trending stocks based on their relative performance to other investments
3. Time-Series Momentum Trading - changing portfolio allocations by selling negative-trending stocks and buying positive-trending stocks based on their absolute performance
4. Pairs Trading - taking long and short positions in highly correlated stocks, in such a way that maintains volatility but increases returns based on recent trends
5. Semantic News Trading - changing portfolio allocations based on the valence of news surrounding different companies
6. General ML Trading Models - feeding arbitrary historical data into ml models to see what they learn

### Indexes to Observe

(* Fill this in next week. Gautam can take some notes? *)


### Semester-End Evaluation

At the end of the semester, models will be evaluated based on their week-on-week performance. The most important judging criteria will be the variance of each model's performance, and the next will be the overall returns.


## Organization

### Files

1. data.py - getting and formatting historical data from yfinance library
2. tests.py - getting current data in order to test different models
3. trading.py - running all the trading models
4. baseline-trading.py - trading model based on kelly fraction strategy
5. average-trading.py - trading model based on moving average strategy
6. xs-momentum-trading.py - trading model based on cross-sectional momentum strategy
7. ts-momentum-trading.py - trading model based on time-series momentum strategy
8. pairs-trading.py - trading model based on pairs trading strategy
9. semantic-trading.py - trading model based on semantic news trading strategy
10. combination-trading.py - trading model based on a combination of models 4-8
11. ml-trading.py - trading models based on other miscellaneous ml data models
12. free-trading.py - trading models based on other miscellaneous ml data models free of volatility constraints