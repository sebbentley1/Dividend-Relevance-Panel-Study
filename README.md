Dividend Relevance — Panel Econometric Study
Testing the Modigliani-Miller (1961) dividend irrelevance proposition using a panel dataset of 25 large-cap US and UK equities, 2020–2024.
Read the full report →

What this project does
This project asks: does changing dividend policy actually affect how much a firm is worth? The MM irrelevance proposition says no — in efficient markets, value comes from earnings power, not from how those earnings are distributed. I test this empirically using panel econometrics.
The analysis runs three model specifications:

Pooled OLS — baseline, treats all observations as independent
Fixed Effects — controls for time-invariant firm characteristics
Random Effects — preferred by the Hausman test (p = 0.6752)

All models use firm-level clustered standard errors. A robustness check replaces Log Total Assets with Log Market Cap as the dependent variable.
Result: Neither the Dividend Payout Ratio nor Dividend Yield significantly predicts firm valuation in any specification. Consistent with MM irrelevance.

Key results
VariablePooled OLSFixed EffectsRandom EffectsDPRp = 0.552p = 0.700p = 0.548DivYieldp = 0.000***p = 0.328p = 0.568ROEp = 0.959p = 0.018*p = 0.034*Betap = 0.714p = 0.766p = 0.576
The DivYield significance in Pooled OLS is spurious — driven by between-firm heterogeneity that disappears once firm fixed effects are introduced. This is explained in detail in the report.
Hausman test: χ² = 2.331, p = 0.6752 → Random Effects preferred.

Data
Sources:

SimFin bulk API — fundamental data for 15 firms
yfinance — fundamental data for 10 firms not covered by SimFin's free tier (UK stocks, US banks)
yfinance — SPY daily prices for Beta computation

Sample: 25 large-cap value stocks across energy, banking, pharmaceuticals, consumer staples, telecoms, utilities, and industrials. 102 firm-year observations after cleaning.
Beta construction: Unlike a simple yfinance snapshot, Beta here is time-varying — computed each year by regressing 12 monthly firm returns against SPY monthly returns using OLS. This allows Beta to be estimated in all three model specifications.

Repo structure
├── dividend_panel_analysis.ipynb   # Full annotated notebook
├── dividend_panel_data.csv         # Final cleaned dataset (102 rows)
├── report.html                     # Full project report
└── README.md

How to run

Install dependencies:

bashpip install simfin yfinance linearmodels statsmodels scipy pandas numpy

Get a free SimFin API key at simfin.com and paste it into Cell 2 of the notebook.
Run all cells in order. The first run downloads ~50 MB of SimFin data and caches it locally — subsequent runs load from disk.


Limitations
This project is honest about what it cannot claim:

Five years is a short panel. Ideally this would use 10–15 years of data. SimFin's free tier limits history for this sample.
Log Total Assets measures firm size, not firm value. The theoretically correct dependent variable is Tobin's Q. Log Market Cap is used as a robustness check.
Hybrid data sourcing introduces potential inconsistencies between SimFin and yfinance, particularly for IFRS-reporting UK stocks.
Sample is large-cap value stocks only. Results may not generalise to growth firms or smaller companies.


Stack
Python · pandas · numpy · statsmodels · linearmodels · SimFin · yfinance · scipy
