---
createdAt: 2023-06-15T17:44:20+02:00
dg-publish: true
modifiedAt: 2023-07-01T04:03:46+02:00
title: "CMT Level 1 2020"
---
# CMT Level 1 2020

## Book info

Title: CMT Level 1 - An introduction to Technical Analysis (2020)
Search keyword in my Calibre library: `uuid:"=0149229f-8146-4466-aef9-09076b093d79"`

## Notes

### Chapter 1

The basic principle of Technical Analysis - The trend.

a trend is a directional movement of prices that remains in effect long enough to be identified and still be profitable. (p.18)

one way to determine a trend in a data set is to run a [linear least-squares regression](https://www.mathsisfun.com/data/least-squares-regression.html). (p.19)

the technical analyst believes it is futile to analyze the components of supply and demand except through the prices it creates. (p.21)

The trend length of interest is determined solely by the investor/trader's period of interest.

one of the factors that determine supply and demand is buyer and seller expectations. You do not buy a stock unless you expect it to rise in price. (p.23)

technical analysis assumes that
- history will repeat itself and that humans will behave similarly to the way the have in the past in similar circumstances. (p.24)
- prices are non-random
- price discounts everything (p.23)
- emotions are affected by earlier emotions through emotional feedback. i.e. if I buy a stock today and its price rises, I am happy and tell others to buy the stock, others see its price rising and also buy it, thus causing the price to rise further

### Chapter 2

Dow theory.

prices become more random and unpredictable as the time horizon shrinks.

on the logarithmic scale, the vertical distance represents the same percentage in price. (p.55)

The rule of thum for when to use an arithmetic or logarithmic scale is that when the security's price range over the period being investigated is greater than 20%, a logarithmic scale is more accurate and useful.

### Chapter 4

Trading ranges (or sideways trends) occur when peaks and troughs appear at similar levels (p.65)

![trading-range](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2023-06-16_190625_R6U2_LexG.jpg?updatedAt=1686935254768)

When prices have been rising and then reverse downward, the highest point in the rise is referred to as a resistance point, a level at which the advance has met with selling "resistance". It is the level at which sellers (supply) are as aggressive as the buyes (demand) and halt the advance. (p.66)

At the support point, buyers become as aggressive as the sellers and halt a price decline.

The presumed psychology behind a support/resistance level (p.68)
- a resistance zone will likely exists at $134 because sellers want to sell at that price: sellers who missed $134 before, sellers who bought at $134 and want their money back, and sellers who want to short the stock at $134 where it halted earlier
- Assumed that none of these players is using a fundamental or other informational reason for selling the stock at $134. The reasons are purely psychological

![support-resistance-zones](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2023-06-16_191618_Df2GfsjQJ.jpg?updatedAt=1686935819593)

A breakout is a powerful signal. It indicates that the balance between demand and supply has been settled and is an inidication of the initiation/continuation of a directional trend. (p.74)

### Chapter 5

A stop order is an order to buy/sell once a specific price has been surpassed.

The need to know what is wrong is unnecessary because the stock price action itself is suggesting that something is wrong. (p.98)

risk/return ratio
- return: difference b/w the entry price and the price objective
- risk: the amount the price must go against the entry price before exited on a stop
- reward/risk ratio minimum is 3:1. This give the investor the odds of making money even 2 out of 3 trades fail, assuming the 3rd action provides a 3:1 gain.

### Chapter 6

Moving Averages

The principal reason that moving averages (MA) are used is to smooth out shorter fluctuations and focus on the trend that fits with the investor's time horizon. (p.110)

e.g., a 20-day MA is one number that represents all the prices for the past 20 days. It filters out each one of the prices during the past 20 days and tells us how the group of 20 days (rather than its separate parts) is behaving

Most MA of prices are based on closing prices, but they can be calculated on highs, lows, daily means or any other value as long as the price type is consistent throughout the calculations

Table 6.1 Price data and MA calculations for Walmart Daily Price Close (p.110)

These popular periods (200, 60, 50, 30, 20, 10 days) are arbitrary and were chosen in the days before computers when the calculations had to be done by hand. (p.113)

The daily fluctuations are smoothed by the MA so that the analyst can see the underlying trend without being distracted by the small daily movements.

MA is the lagging indicator. It helps us discern a trend, but so after the trend has begun.

the longer MA is slower to pick up trend changes, but less likely to falsely indicate a trend change

a moving average requires a trend for a crossover to be profitable (p.116)

linearly weighted moving average (LWMA) gives more importance to the most recent price data, because we choose the larger weight on the most recent price.

to address the issue of drop-off effect (earliest price being omitted) that occurs with a simple moving average (SMA), analysts use the exponential moving average (EMA) (p.118)

explanation of the general formula to calculate EMA (p.118)

The reason for the use of an EMA is that it weighs more strongly the prices that are more recent (but not ignore the earliest prices). EMA is also called an exponential weighted moving average.

Welles Wilder (1978) used another formula to calculate a MA that weights the most recent prices more heavily.
- formula (p.120)
- Wilder's method of calculating MA is usually used in the average true range (ATR), the relative strength index (RSI), and the directional movement indicator (DMI)

[Average true range (ATR)](https://www.investopedia.com/terms/a/atr.asp) measures market volatility. It shows investors the average range prices swing for an investment over a specified period.
- example:  if the ATR for an asset is $1.18, its price has an average range of movement of $1.18 per trading day.

Strategies using MA
- Determining trend
    - example: if the stock is above its 200-day MA, the trend is considered upward
    - this is the most sensible use of MA
- the MA acts as support and resistance
- Determining price extremes
    - assumption: the MA is a mean, any reversion to the mean will tend to approach the MA. Or price has a tendency to return to the mean
    - a deviation from the MA is a measure of how much prices have changed ahead of their usual central tendency
    - "deviation-from-trend" strategy using ratio of current price to MA, figure 6.6 (p.123)

Only during a trending market, MA signals are profitable. A sideways market is costly in almost all cases. The deviation-from-trend is the only MA method that can profit in a flat trend.

Directional Movement
- developed by Welles Wilder
- compared a stock's trading range for one day with the trading range on the previous day to measure trend
- positive directional movement (+DM) occurred when the high for a day exceeded the high of the previous day
- negative directional movement (-DM) occurred if the low for the day is less than the previous day's low
- only a +DM or -DM can be recorded for a particular day
- directional index (DX) is used to create the average DX (ADX line). The DX is always positive and represents the tendency of the market to trend because it measures the DIs against each other. When one DI is large compared to the other DI, the market is moving strongly in one direction and the value of the DX will be large (p.127)
- the ADX indicator is valuable in determining when to apply a MA trend-following system. A rising ADX indicates an increasing tendency to trend in the corresponding prices. A low ADX (or declining) indicates a flat trend (losing momentum).

There are 2 principal ways to measure price volatility
- standard deviation about a mean (or MA)
- average true range (ATR)

The price movement is centered on the MA but falls within a band or envelope around the MA. The analyst expects that the price tends to fluctuate within the band.

Bands are envelopes around a MA, but rather than being fixed in size, are calculated to adjust for the price volatility around the MA (p.130). They shrink when prices become calm and expand when prices become volatile

The most widely used band is the Bollinger band
- Bollinger uses the simple moving average (SMA)
- upper band: 2 standard deviations are added to the SMA
- lower band: 2 standard deviations are subtracted from the SMA
- why 2 standard deviations? (p.130)
    - by statistical theory, the plus or minus 2 standard deviations should account for approximately 95% of all the price action about the MA
    - although this is not quite true because price action is nonstationary and nonrandom, it gives the analyst a rough estimate of the majority of price action

Bands have become methods of determining the beginnings of trends and are not generally used for range trading. (p.132)
- when the outer edge of a band is broken, empirical evidence suggests that the entry should be in the direction of the breakout
- a breakout from a band that contains roughly 90% of previous price action, suggests that the general trend of the previous price action has changed in the direction of the breakout.

The most profitable trend-following systems are long-term.

Bands are more successful in trending markets. Therefore bands are more suitable for commodities markets than the stock market.

### Chapter 7

Bar chart patterns

In the usage of technical analysis, the terms "pattern" and "formation" are used interchangeably.

A pattern is a configuration of price action that is bounded, above and below by some form of either a line or a curve.

[Bulkowski's ThePatternSite.com](https://thepatternsite.com/) is a website that explains in significant detail all the patterns discussed in this chapter.

If prices do have patterns, what causes them? (p.141)

Chart patterns have not been proven to exist or to be profitable (p.141)
- The chart pattern and trend reader should look for failure rather than believe in the constancy of previous patterns
- Schwager (1996) suggests that profitability from failed patterns is often greater than from correct patterns

Once a pattern is widely recognized and acted upon, its effectiveness diminishes. (p.143)

The head-and-shoulders pattern is probably the most famous technical pattern. Its profitability is high (relative to other patterns). It is also one of the few that have been studied had statistical significance (p.162)

### Chapter 8

Short-term patterns.

Table 8.1 Bulkowski's ranking of candlestick Patterns - Ten Best (p.210)

I hate this chapter so much. Lack of evidence and sounds like superstitious.

### Chapter 9

Confirmation.

On-balance-volume (OBV) index. The idea behind this index is that high volume in one direction and low volume in the opposite direction should confirm the price trend.
- For example, in a trending market, when prices reach a new high, confirmation of the price strength comes when the OBV also reaches new high
- if the OBV does not reach a new high to confirm price strength, a negative divergence may occurs. It's an early warning that the price advance may soon reverse downward. A negative divergence suggests that volume is not expanding with the price rise. (p.222)

Price-volume-trend index.
- calculation: determine daily percentage price change (up/down), multiplied by the total volume for the day
- this index is more heavily impacted when large percentage price changes occur on heavy volume

Chaikin's Accumulation Distribution (AD) index
- formula (p.225)
- basic idea: determines where the close prices each day occurs within the daily price range (high-low)
    - if the close occurs above its midpoint for the day, the result of formula will be a positive number, called `accumulation`
    - when the close is below its midpoint for the day, the result will be a negative number, called `distribution`
- each daily figure is then multiplied by daily volume and cumulated into an index similar to the OBV
- purpose: similar to the general rules of divergences as the OBV

Williams Accumulation Distribution (WAD)
- this indicator use the concept of True Range
- The True Range use the previous day's close as a benchmark and avoids the problems that arise when a price gaps between days
    - The True Range high is either the current day's high or the previous day's close, whichever is higher
    - The True Range low is either the current day's low or the previous day's close, whichever is lower
    - read: [Average true range (ATR)](https://www.investopedia.com/terms/a/atr.asp)
- in the WAD
    - Accumulation occurs on days in which the close is greater than the previous day's close. The price move on these days is the difference between the current day close and the True Range low
    - Distribution occurs on days when the close is less than the previous day's close. The price move is the difference between the current day close and the True Range high, which is a negative number
    - Each price move is multiplied by the volume for the respective day, and the resulting figures are cumulated into the WAD index

Volume oscillator. Its use is to determine when volume is expanding or contracting.
- Expanding volume implies strength to the existing trend
- contracting volume implies weakness in the existing trend

Chaikin Money Flow (p.227)
- is an oscillator that is the Chaikin's AD calculation.
- It is calculated by summing the ADs over the past 21 days and dividing that sum by the total volume over the past 21 days.
- This produces an oscillator that rises above 0 when an upward trend begins and declines below 0 when the trend turns downward
- as an oscillator, this tool is used for confirmation, not signal generation

Money Flow Index (MFI)
- a method of measuring money flow into and out of a stock
- it considers "up" days and "down" days to determine the flow of money into and out of an equity
- the money flow on any particular day is the day's typical (average) price multiplied by the daily volume
- if a day's average price is higher than the previous day's average price, there is positive money flow (PMF). Conversely for negative money flow (NMF)
- the MFI is an oscillator in range of 0 to 100. When PMF is relatively high, the oscillator approaches 100. When negative money flow is relatively high, MFI approaches 0
- a level above 80 is often considered overbought and below 20 oversold

In the future market, the number of outstanding futures contracts is called `open interest`.
- At the expiration of the specific futures market delivery month, the number of contracts reduces to 0
- Total open interest (OI) is the number of contracts outstanding in all delivery months
- OI is a tool in estimating the liquidity of most contracts

Confirmation is concerned with determining whether a price trend is continuing or coming to an end.

Momentum deals with the rate at which prices are changing.
- Momentum measures how quickly the prices are rising or how steeply the trend line is sloping
- Remind high school calculus: the slope of a line is the first derivative, the change in that slope is the second derivative
- Hence, momentum is the second derivative of price action over some period.

When momentum is confirming the price trend, a convergence (or confirmation) occurs, when momentum is failing to confirm the price trend slope, a divergence occurs.

Prices never follow a trend in an absolute straight line. Prices oscillate about a central trend, deviating above and below the trend.

Profits are made from anticipating and riding the trend. Indicators and oscillators should only be used as secondary evidence to confirm the trend.

Momentum indexes and oscillators are based on price data, they do not add new information to the analysis. They are simply manipulations of the same data. They are less informative than other indicators such as volume that provide new and different information.

Most common and popular momentum oscillators:

Moving Average Convergence-Divergence (MACD)
- a variation of the moving average crossover
- MACD is calculated using the difference between 2 exponential moving averages (EMA). Commonly, 26-period EMA is subtracted from a 12-period EMA
- A positive MACD indicates that the average price during the past 12 periods exceeds the average price over the past 26 periods
- The signal line is an EMA of the MACD. A 9-period EMA is the most common
- A histogram of the difference between the MACD and the signal line over the same period
- Example: when the MACD is above zero, suggesting an upward trend, buy signals occur when the MACD crosses from below to above the signal line. Downward crossings are not reliable while the trend is upward.

Relative Strength Index (RSI)
- introduced by Wilder in 1978
- RSI measures the strength of an issue against its own history of price change by comparing "up" days to "down" days
- formula (p.242)
- RIS ranges from a low of 0 (indicating no up days) to a high of 100
- 14-day period is the most commonly used

Stochastic Oscillator
- It looks at the most recent close price as a percentage of the price change (high to low) over a specified past window of time. This makes it sensitive to recent action
- Analyst use the stochastic for trading when the most recent close is the most important price
- the name of his oscillator has nothing to do with the scientific term stochastic, which means random or nondeterministic.
- formula (p.242)
- As in most oscillators, the stochastic works better in trading range market. In a trending market, divergences, trend line breaks generate better signals.

Commodity Channel Index (CCI)
- developed by Donald Lambert in 1980
- don't be fooled by the name, this indicator can be used in any market, not just commodity markets
- the CCI measures the deviations of a security's price from a moving average.
- CCI is similar to the Stochastic. Using both would be a duplication of effort and liable to create false confidence.

Similarities between Oscillators
- It is redundant and nonproductive to use many oscillators that essentially tell the same story

Combinations - determining Trend and Trading Range: The ADX and its component parts, the DMI+ and DMI-.
- A peak in the ADX almost invariably occurs at a trend peak up or down. It is thus useful as an indicator to close a position established during a trend
- A trough in the ADX occurs when a trend has begun and is beginning to accelerate.
- The period between a trough and a peak is a period of generally trending prices (p.249)
- The period between a peak and a trough is a period of decelerating trend that might be trading in a range
- It seems to be true that very low levels of ADX are periods of no trend and a high possibility of whipsaws

### Chapter 10

Candlestick Charting Essentials.

Though the fundamentals are important, the shorter the timeframe, the more important the psychological component of the market becomes. A way to measure the emotional aspect of the markets is through technical analysis.