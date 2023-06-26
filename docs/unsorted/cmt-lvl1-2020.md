---
createdAt: 2023-06-15T17:44:20+02:00
dg-publish: true
modifiedAt: 2023-06-26T04:16:36+02:00
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

Volume oscillator. Its use is to determine when volume is expanding or contracting.
- Expanding volume implies strength to the existing trend
- contracting volume implies weakness in the existing trend

Chaikin Accumulation Distribution (AD) index
- formula (p.225)
- basic idea: determines where the close prices each day occurs within the daily price range (high-low)
    - if the close occurs above its midpoint for the day, the result of formula will be a positive number, called `accumulation`
    - when the close is below its midpoint for the day, the result will be a negative number, called `distribution`
- each daily figure is then cumulated into an index similar to the OBV
- purpose: similar to the general rules of divergences as the OBV