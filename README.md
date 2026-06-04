Dividend Relevance — Panel Econometric Study
I'm a second year BSc Economics and Finance student. This is a self-directed summer project I built to develop practical skills in Python, statistical analysis, and version control — areas I want to get stronger in outside of coursework.
The theory comes from my Corporate Finance module — Modigliani and Miller's (1961) dividend irrelevance proposition, which argues that in efficient markets, how a firm distributes its earnings shouldn't affect its value. I wanted to actually test it rather than just write about it in an exam.
I had some prior experience with cross-sectional regression from a group project, so panel econometrics felt like a natural next step up in complexity. I built the whole thing in Python and Jupyter Notebook, using AI as a learning tool to get up to speed with syntax I hadn't used before.
Read the full report →

What the project does
Tests whether dividend policy (measured by Dividend Payout Ratio and Dividend Yield) significantly predicts firm valuation across a panel of 25 large-cap US and UK stocks from 2020–2024.
Three model specifications are estimated — Pooled OLS, Fixed Effects, and Random Effects — with the preferred estimator selected via a Hausman test. All models use firm-level clustered standard errors.
Result: Neither dividend variable is significant in any specification. Consistent with MM irrelevance.

Key results
VariablePooled OLSFixed EffectsRandom EffectsDPRp = 0.552p = 0.700p = 0.548DivYieldp = 0.000***p = 0.328p = 0.568ROEp = 0.959p = 0.018*p = 0.034*Betap = 0.714p = 0.766p = 0.576
The DivYield significance in Pooled OLS is spurious — it disappears once firm fixed effects are introduced. This is explained in the report.
Hausman test: χ² = 2.331, p = 0.6752 → Random Effects preferred.

Data

SimFin bulk API — fundamentals for 15 firms
yfinance — fundamentals for 10 firms not on SimFin's free tier
yfinance — SPY prices for annual Beta computation

Beta is time-varying, computed each year by regressing monthly firm returns against SPY — an improvement on a single static snapshot.

Limitations

Five years is a short panel — ideally 10–15 years
Log Total Assets measures size not value — Tobin's Q would be more appropriate
Hybrid data sources introduce potential inconsistencies
Sample is large-cap value stocks only — results may not generalise


Stack
Python · pandas · numpy · statsmodels · linearmodels · SimFin · yfinance · scipy
