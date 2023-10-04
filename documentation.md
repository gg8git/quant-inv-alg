# Project Ideation

## Overview

We can think about quantitative trading as a method of maximizing or optimizing expected return while maintaining a certain level of volatility or variability within our portfolio. 

As a result, our overarching strategy will be to determine the optimal allocation of investments using analysis of historical data as well as a strategy centered around the Kelly Fraction and the Sharpe Ratio. This will be used as a baseline to be compared to more flexible trading models.

Finally, to get introduced to quantitative trading, we will reduce volatility by investing in stock indexes rather than individual investments. These include international indexes, national indexes, and industry-specific indexes.


### Technical & Strategical Details

Our baseline model will be centered around a fixed portfolio oriented around the optimal portfolio allocated determined by the Kelly Fraction.

The rest of the models will abide by a fixed volatility, determined by the portfolio volatility equation (square root of portfolio variance), and then use various machine learning models to optimize returns.

The machine learning models are as follows:
1. Mean Reversion Trading - changing allocation to sell stock when price is above historical average and buy stock when price is under historical average
1. Moving Average Trading - changing portfolio allocations based on patterns discovered within short-term changes in average closing price
2. Cross-Sectional Momentum Trading - changing portfolio allocations by selling negative-trending stocks and buying positive-trending stocks based on their relative performance to other investments
3. Time-Series Momentum Trading - changing portfolio allocations by selling negative-trending stocks and buying positive-trending stocks based on their absolute performance
4. Pairs Trading - taking long and short positions in highly correlated stocks, in such a way that maintains volatility but increases returns based on recent trends
5. Semantic News Trading - changing portfolio allocations based on the valence of news surrounding different companies
6. General ML Trading Models - feeding arbitrary historical data into ml models to see what they learn

Backtesting and validation to compare the efficacy of different models will be done by using walk-forward-optimization over the past 7 years, with each optimization phase being 24 months and each validation phase being 6 months. During each validation phase, models will be assessed by vectorbt's total_return function. Details for how this should be done can be found in https://github.com/polakowo/vectorbt/blob/master/examples/WalkForwardOptimization.ipynb. More information on the theoretical logic behind walk-forward optimization can be found in https://www.youtube.com/watch?v=WBZ_Vv-iMv4. 


### Indexes to Observe

(* Fill this in next week. Gautam can take some notes? *)


### Semester-End Evaluation

At the end of the semester, models will be evaluated based on their week-on-week performance. The most important judging criteria will be the variance of each model's performance, and the next will be the overall returns.


## Leo Random Notes on Quants
1. Recognize what is a risk-premium strategy vs. a risk-neutral strategy. This is important at the initial modeling/researching stage of the ML.
2. Sharpe ratio of a portfolio is a good indicator, but always keep in mind CAGR is the main value that drives growth. And in most cases, a max-sharpe portfolio != max-CAGR portfolio
3. In-sample vs Out-of-Sample data. Can we always trust the data? Where do we receive the data from? All pretty important question to keep in mind
4. Static vs. Dynamic portfolio. Obviously we are doing a dynamic portfolio with rebalancing. Thus frequency will be the key to determine: how often do we want the system to recheck for rebalancing? What is the threshold for trade initiation? (e.g. when expected return > expected trading cost, or to adjust certain correlation breaks)
5. Portfolio construction thought process. This doesn't just apply to quant but portfolio management in general. Start by establish our policies and asset classes (in this case, mostly US/non-US ETFs/Indices). Then we can do the selection process (which is similar to the experience at fusion). And then it's the signaling production (modeling/researching) phase of quant. And then lastly is portfolio rebalancing alongside with continuous research (in case we want to add/remove assets in the portfolio)
6. By momentum trading I'm always a bit doubtful...but I think we can/have to extent our time series to a longer time frame (e.g. at least 2 weeks-1 months trailing) or else we don't have enough accurate data at the second/minute level (and it's mad expensive to get those data)
7. I gotta catch a flight nowwwww but I'll add more!


## Organization

### Libraries to Use

install libraries in miniconda virtual environment
1. OpenBB SDK - api accessing general-purpose terminal for financial data (look at https://docs.openbb.co/sdk/usage/basics)
2. ta-lib - library of technical indicators
3. VectorBT - library to backtest and train solutions (look at https://vectorbt.dev/api/ and https://www.youtube.com/watch?v=GowmmrSMw9I)
4. alpaca-trade-api - api to trade with alpaca broker (currently being deprecated and transferred to alpaca-py? must think about this)

### Files

(not updates: will come back and change when everything is done)

1. data.py - getting and formatting historical data from yfinance library
2. tests.py - getting current data in order to test different models
3. trading.py - running all the trading models
4. reversion-trading.py - trading model based on mean reversion strategy
5. average-trading.py - trading model based on moving average strategy
6. xs-momentum-trading.py - trading model based on cross-sectional momentum strategy
7. ts-momentum-trading.py - trading model based on time-series momentum strategy
8. pairs-trading.py - trading model based on pairs trading strategy
9. semantic-trading.py - trading model based on semantic news trading strategy
10. combination-trading.py - trading model based on a combination of models 4-8
11. ml-trading.py - trading models based on other miscellaneous ml data models
12. free-trading.py - trading models based on other miscellaneous ml data models free of volatility constraints
