---
createdAt: 2023-03-16T01:43:53+01:00
dg-publish: true
modifiedAt: 2023-10-16T02:35:15+02:00
title: Trading Journal to Measure Stock Trading Performance With Google Sheets
---

# Trading Journal to Measure Stock Trading Performance With Google Sheets

I want to create a spreadsheet to monitor the performance of trading stocks in Vietnam market.

## Deliverables

- Click [here](https://docs.google.com/spreadsheets/d/1CMeBjHsBpL8_txMd6hhwQkfvEhAknmi-rNLycZaXszc/edit?usp=sharing) to access my sample spreadsheet, with sample data and user-defined functions included. The custom functions only work with the data structure presented in the sample spreadsheet.
- Or you can also review separately the code of user-defined functions at this [gist](https://gist.github.com/h7b/4fc057be0fff4a5db9fd207c7d156560).

## Project status

DONE

- Input manually each trade into `orderBook` sheet
- View recap of the portfolio with the automated sheet `pnl`, with the current value of the portfolio, realized/unrealized P/L
- View list of executed trades, sorted by ticker in the automated sheet `orderBook_sortedByTicker`
- Compute cost basis of stocks with FIFO method
- refactor the formula to calculate the average cost per share (take into account only the unsold shares in portfolio)

## Thoughts

From the article of [Tools to research Vietnam stock market for retail investor](vn-stock-market-research.md), I learned that there is no free API data feed for hobbyist to play with the end-of-day historical price data of Vietnam' securities. So I intend to crawl data from [investing.com](https://www.investing.com/) using [investiny](https://github.com/alvarobartt/investiny) package then import into Google Sheets.

2022-12-09 update: TIL

- I can simply use the [IMPORTXML](importxml.md) formula to import the historical data from [investing.com](https://www.investing.com/) into Google Sheets. [Click here](https://blog.coupler.io/googlefinance-function-advanced-tutorial/) to read the tutorial written by `coupler.io`. For this reason, the plan to practice python for web scraping is procrastinated again
- `IMPORTXML` refreshed automatically only if the document is opened, which is good enough for current usage [^1]
- Apply [Custom Formatting Numbers](custom-formatting-numbers.md) to indicate the `millions` by `M`, the `thousands` with a `k`.

2022-12-23 update: TIL

- need to refactor formula in `pnl` sheet since `orderBook` now has 3 types of transaction (buy, sell, stock dividend)
- add a new column for `income tax on selling securities`. Learn the calculation at [Tax Basics for Investors in Vietnam](tax-investors-vn.md)
- Calculate the column `rate of return (unrealized) (weighted by cost of purchasing)`
  - use [SUMPRODUCT](sumproduct.md) combined with [ABS](https://support.google.com/docs/answer/3093459?hl=en) formula to get the sum of absolute value of a mixture of positive and negative numbers
  - `SUMPRODUCT(ABS($E$2:$E))`
  - in [SUMPRODUCT](sumproduct.md) formula, when `array2` is omitted as above, the formula will calculate the sum of the products of the 2 arrays: `array1` and `{1,1,1,...}` with same length as `array1`.
  - Read more about [How To Get Absolute Value In Google Sheets](https://www.alphr.com/absolute-value-google-sheets/)

2022-12-24 update:

- refactor the formula to calculate `Realized Gain/Loss`, applying the accounting FIFO (first in, first out). It means that the shares I bought earliest will be the shares I sell first. I also wrote a note about [[fifo-cost-basis|how to compute the cost basis of stocks with FIFO method]]
- add a [dedicated note](data-structure.md) explaining how did I record transaction into `orderBook`.

2023-01-03 update:

- Add [[track-daily-history|custom script]]
  - to automatically record a daily history of values in `pnl` sheet
  - to force refreshing `IMPORTXML` function in `tmp_currentPrice` sheet, while the document is not opened
- Reason: watch the daily performance of my portfolio, to learn when I missed the chance to realize the profit.

2023-01-06 update:

- Refactor the formula to calculate the [Average Cost per Share](average-cost-per-share.md)

2023-01-16 update:

- Refactor the [[track-daily-history|custom script]] to automatically record a daily history of values in `pnl` sheet
- Reason: enhance the performance of the batch operations.

2023-01-17 update:

- Refactor the [[track-daily-history|custom script]] to automatically record a daily history of values in `pnl` sheet
- Reason: replace the configuration of installable trigger from UI to apps script

2023-04-09 update:
- separate the `orderBook` sheet and `pnl` into 2 different files. Ask Dad to manually enter transaction data into a form provided by [tally.so](https://tally.so/). These data will be synced manually into the `orderBook` sheet.
    - the data from `oderBook` sheet then will be imported into `pnl` sheet for calculation of the trading performance
    - reason: it's more fun when Dad can engage and play together. Dad currently use 3 brokerage services provided by ssi, abs and vcbs.
- the data source for current market price change from [investing.com](https://www.investing.com/) to [cafef.vn](https://cafef.vn/). Reason: much more stable when crawling price data using the `importxml` function
- update the custom formula to take into account of the transaction type `stock dividend` when calculating `costOfGoodsSold` and `realizedGainByTicker`.

2023-04-24 update:
- separate the `pnl_daily` sheet into a different file. I hope this could increase the performance of the calculation in main trading journal spreadsheet
- create a `Looker Studio` report with both `desktopView` and `mobileView` to visualize the movement of portfolio's performance

2023-07-13:
- update the custom formula to take into account of the transaction type `cash dividend` when calculating `averageCostOfUnsold` and `realizedGainByTicker`.

2023-07-21:
- create a new custom formula `getClosePriceTcbs` using public API from [TCBS](https://www.tcbs.com.vn/en_US/home) to retrieve the `closing price` instead of relying on [IMPORTXML](https://support.google.com/docs/answer/3093342?hl=en) formula to scrape data from [cafef](https://cafef.vn/thi-truong-chung-khoan.chn).
- The code was inspired by [this issue from vnstock](https://github.com/thinh-vu/vnstock/issues/10) and the [vn-stocks repo](https://github.com/telosma/vn-stocks)

2023-07-25:
- create a new custom formula `getClosePriceSsi` using public API from [SSI](https://iboard.ssi.com.vn/) to retrieve the `closing price`. Since the responses from the API of TCBS are not reliable (i.e. the response was not updated on real-time )

2023-08-09:
- create a new custom formula `getClosePriceEntrade` using public API from [DNSE](https://www.dnse.com.vn/) to retrieve the `closing price`. Since the API of SSI requires to manual refresh the `device-id` parameter every 5 days

2023-09-19:
- create new custom formula:
    - `tradingFeeByTickerBrokerDate`: calculate the total trading fee of filtered transactions by ticker-brokerageAccount-date
    - `incomeTaxByTickerBrokerDate`: calculate the total income tax (on selling securities and receiving dividends) of filtered transactions by ticker-brokerageAccount-date
    - `costBasisByTransaction`: calculate the cost basis of a specific ticker (FIFO method), from filtered transactions by ticker-brokerageAccount-date
    - `realizedGainByTransaction`: calculate the realized gain/loss from the most recent transaction, filtered by ticker-brokerageAccount-date
- refactor function `fifoCalc` to take into account of `tradingFee`, `incomeTaxOnSale`, `incomeTaxOnDividend`.
- `fifoCalc` now can calculate the realized gain and the cost basis from only the most recent `sell` transaction.
- in order to solve the issue of multiple transactions of the same type (eg. `sell`) of a specific ticker in a brokerage account, when i enter data of transactions, the `date` field should follow [ISO 8601](https://www.ionos.com/digitalguide/websites/web-development/iso-8601/), which is `yyyy-MM-dd'T'HH:mm:ss.SSSXXX`, for example, `2000-10-31T01:30:00.000-05:00`.

2023-09-22:
- created an entry data form using [Tally.so](https://tally.so/) to reduce error when user input data into spreadsheet. However, the end user cannot review what he submitted. This issue can be solve using the feature `Respondent email notifications`, which is available only in [Pro plan $29/month](https://tally.so/pricing)
- This lead me to the idea of create a form using [Glide](https://www.glideapps.com/), a no-code tool. With this web app, the respondent can see his recent submission.
- But another issue arises, which is I don't receive any notifications to know when we have new data entry via Glide web app. I will be happy if I receive an email when there is new submission. However, the [send-email Action](https://www.glideapps.com/docs/automation/actions/send-email) is only available for [paid plans](https://www.glideapps.com/pricing), starting at $25/month.
- Glide has integrated [Zapier Action](https://www.glideapps.com/docs/automation/actions/zapier-action), which can be used as a workaround. However the [Free plan](https://zapier.com/pricing) from Zapier is limited at 100 tasks/month.
- Reading the docs of Glide, I discover that they also have [webhook](https://www.glideapps.com/docs/automation/actions/webhook) to send data to other apps from Glide. This lead me to [make.com](https://www.make.com/en), which is similar to Zapier but with better [Free plan](https://www.make.com/en/pricing) 1,000 Ops/month
- The config to connect Glide and Make is quite straight forward with [this tutorial](https://www.make.com/en/help/app/glide). But instead of sending email when new submission arrives, I choose to connect a Telegram bot with Make. Now I will receive a notification in a Telegram private channel for new data entry.

2023-10-09:
- Replace [getValues()](https://developers.google.com/apps-script/reference/spreadsheet/range#getvalues) by [getDisplayValues()](https://developers.google.com/apps-script/reference/spreadsheet/range#getdisplayvalues) in the user-defined function `recordValues()`
- Reason: This change will retrieve the displayed values as strings, rather than the formula expressions. By working with the displayed values, I expect to reduce the likelihood of encountering errors caused by unresolved formulas (`#ERROR!`, `#NAME?`, `#VALUE!`), which usually happened in previous version when duplicating values from spreadsheet `pnl` to a backup spreadsheet using an Apps Script background task.

2023-10-16:
- Applied [this tutorial](https://www.youtube.com/watch?v=nLW8SerwnJo) to [[search-box|create a search box in spreadsheet]]. I intend to use this feature to filter data from `orderBook` sheet.

## Related

- Read tutorials
  - [Youtube | How to Use Google Sheets With Python](https://www.youtube.com/watch?v=bu5wXjz2KvU)
  - [Youtube | Google Sheets and Python - Tutorial](https://www.youtube.com/watch?v=T1vqS1NL89E)
  - [coupler | How to Connect Python to Google Sheets](https://blog.coupler.io/python-to-google-sheets/)
  - [Lucas Nunes Fernandes | How to locally run Python on Google Sheets](https://betterprogramming.pub/how-to-enable-pythons-access-to-google-sheets-e4264cdb545b)
  - [Youtube | Google Sheets Database with Python Web Scraping](https://www.youtube.com/watch?v=ct0xvw_Z0tU)
  - [Youtube | Google Sheets - Python API, Read & Write Data](https://www.youtube.com/watch?v=4ssigWmExak)
  - [Youtube | Google Colab Tutorial - Google Sheets, Read & Write Data](https://www.youtube.com/watch?v=cN7W2EPM-dw)
  - [Youtube | Google Colab Tutorial - Fuzzy Match Lookup with Google Sheets Data Using Python Fuzzy Pandas](https://www.youtube.com/watch?v=M3JYGiM_Xm8)

[^1]: <https://support.google.com/docs/answer/12188454?hl=en>