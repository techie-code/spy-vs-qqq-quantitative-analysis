# SPY vs QQQ: Quantitative ETF Comparison

## Project Overview

This project presents a quantitative comparison of two widely traded US
equity exchange-traded funds (ETFs): **SPY** and **QQQ**.

The analysis compares historical daily returns, cumulative growth,
volatility, drawdowns and risk-adjusted performance over a five-year
sample.

**Research question:** Over the five-year sample, did QQQ's higher
average daily return come with greater risk, and which ETF delivered the
stronger risk-adjusted performance?

-   **SPY:** Tracks the S&P 500 Index and provides exposure to large-cap
    US equities.
-   **QQQ:** Tracks the Nasdaq-100 Index and provides exposure to large
    non-financial companies listed on the Nasdaq.

## Dataset

  -----------------------------------------------------------------------
  Parameter                           Details
  ----------------------------------- -----------------------------------
  Data source                         Yahoo Finance, accessed using
                                      `yfinance`

  Tickers                             SPY and QQQ

  Observation period in saved run     22 November 2021 to 20 November
                                      2026

  Frequency                           Daily

  Data fields                         Open, High, Low, Close and Volume
                                      (OHLCV)

  Price adjustment                    `auto_adjust=True`

  Observations                        1,255

  Columns                             10
  -----------------------------------------------------------------------

The notebook calculates returns from the adjusted closing prices. The
saved results reflect the data retrieved during the recorded run. Yahoo
Finance data may change when the notebook is re-executed.

## Tools and Libraries

-   **Python** for analysis
-   **pandas** and **NumPy** for data manipulation and numerical
    calculations
-   **yfinance** for historical market data retrieval
-   **Matplotlib** and **Plotly** for visualisation

## Analysis

The Jupyter notebook, `spy-vs-qqq-quantitative-analysis.ipynb`, covers:

1.  **Data collection and exploration** -- downloading daily market data
    and inspecting its structure, data types and missing values.
2.  **Data quality checks** -- checking missing values, duplicate dates,
    price-range consistency and negative trading volume.
3.  **Daily returns** -- calculating daily percentage returns from
    adjusted closing prices.
4.  **Average return and volatility** -- comparing mean daily returns,
    daily standard deviation and annualised volatility.
5.  **Cumulative growth** -- comparing the hypothetical growth of an
    initial investment with returns compounded over the sample.
6.  **Drawdown analysis** -- examining peak-to-trough declines.
7.  **Risk-adjusted performance** -- comparing Sharpe and Sortino
    ratios.
8.  **Rolling risk measures** -- examining rolling 252-trading-day
    Sharpe ratios and annualised volatility.
9.  **Event-window inspection** -- reviewing dates with large changes in
    rolling volatility and large absolute daily returns.

## Key Results

The following values are from the notebook's saved outputs.

### Return and volatility

  Metric                         QQQ        SPY
  ----------------------- ---------- ----------
  Average daily return       0.0477%    0.0429%
  Daily volatility           1.4809%    1.0985%
  Annualised volatility     23.5089%   17.4388%

### Drawdown and risk-adjusted performance

  Metric                     QQQ         SPY
  ------------------ ----------- -----------
  Maximum drawdown     -35.1187%   -24.4964%
  Sharpe Ratio            0.5110      0.6197
  Sortino Ratio           0.7276      0.8905

The Sharpe Ratio uses an assumed 0% annual risk-free rate. The Sortino
Ratio uses a 0% daily minimum acceptable return.

### Main observations

-   QQQ recorded the higher average daily return in the selected sample.
-   QQQ also had higher daily and annualised volatility.
-   QQQ experienced a deeper maximum drawdown than SPY.
-   SPY recorded higher full-period Sharpe and Sortino ratios.
-   In the saved latest rolling observations (20 November 2026), QQQ's
    annualised volatility was 22.2023%, compared with 14.2033% for SPY.
    The rolling Sharpe ratios were 0.2384 for QQQ and 0.4753 for SPY.

**Overall:** QQQ had the higher average daily return, while SPY showed
stronger results on the selected risk-adjusted measures and a shallower
maximum drawdown. These are historical, sample-specific findings, not
forecasts.

## How to Run

### 1. Clone the repository

``` bash
git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
cd YOUR-REPOSITORY
```

### 2. Install the required packages

``` bash
pip install pandas numpy yfinance matplotlib plotly jupyter
```

### 3. Start Jupyter Notebook

``` bash
jupyter notebook
```

Open `spy-vs-qqq-quantitative-analysis.ipynb` and run the cells in order.

An internet connection is required to download market data from Yahoo
Finance. Re-running the notebook may retrieve updated observations and
produce different results.

## Repository Structure

``` text
YOUR-REPOSITORY/
├── spy-vs-qqq-quantitative-analysis.ipynb
└── README.md
```

## Limitations

-   Results depend on the selected five-year observation period.
-   The Sharpe Ratio uses a constant 0% annual risk-free rate rather
    than historical Treasury yields.
-   Annualised volatility and rolling measures use a 252-trading-day
    convention.
-   Transaction costs, taxes, bid-ask spreads and tracking differences
    are not included.
-   Yahoo Finance is a third-party data source. Basic validation checks
    are performed, but the data have not been independently audited.
-   Event-window inspection is descriptive and does not establish the
    economic or news-related causes of market movements.

## Possible Extensions

-   Incorporate a time-varying risk-free rate.
-   Add benchmark-relative measures such as beta and information ratio.
-   Compare performance across different sub-periods and market
    conditions.
-   Conduct out-of-sample analysis.

## Disclaimer

This project is for educational and quantitative research purposes only.
It does not constitute financial or investment advice. Historical
performance does not guarantee future results.
