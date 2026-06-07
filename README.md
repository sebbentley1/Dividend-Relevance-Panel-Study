# Dividend Relevance — Panel Econometric Study

I'm a second year BSc Economics and Finance student. This is a solo summer project built to develop practical skills in Python, statistical analysis, and version control.

The theory comes from my Corporate Finance module: Modigliani and Miller's (1961) dividend irrelevance proposition. I wanted to actually test it empirically rather than just write about it in an exam. I had some prior experience with cross-sectional regression from a group project, so panel econometrics felt like the natural next step. I built it in Python and Jupyter Notebook, using AI as a tool to get up to speed with syntax I hadn't used before.

**[Read the full report →](report.html)**

---

## What it does

Tests whether dividend policy significantly predicts firm valuation across 25 large-cap US and UK stocks, 2020–2024. Runs Pooled OLS, Fixed Effects, and Random Effects with the preferred estimator selected via a Hausman test.

**Result:** Neither dividend variable is significant in any specification. Consistent with MM irrelevance.

---

## Stack

Python · pandas · numpy · statsmodels · linearmodels · SimFin · yfinance · scipy
