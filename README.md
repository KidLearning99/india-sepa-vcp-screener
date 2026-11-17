# India SEPA+VCP Screener

Automated daily screener for Indian stocks (NSE and BSE) using Minervini's SEPA trend template, VCP scoring, stage classification, technical indicators and basic fundamentals. Sibling of [us-sepa-vcp-screener](https://github.com/KidLearning99/us-sepa-vcp-screener) and [asx-sepa-vcp-screener](https://github.com/KidLearning99/asx-sepa-vcp-screener).

- **Universe:** NSE- and BSE-listed companies at or above ₹1,000 crore market cap, from Yahoo Finance's equity screener, one listing per company (NSE preferred, checked against NSE's official equity list; BSE-only names are tagged). REITs and InvITs are excluded. Change with the `MIN_MARKET_CAP` env var (in rupees; 1 crore = 10,000,000). `data/india_universe.txt` is a fallback snapshot.
- **Benchmark:** Nifty 50 (^NSEI) for relative strength, beta and correlation.
- **Recent IPOs:** listings with under 200 sessions are always kept and tagged, since they cannot pass the MA150/MA200 checks yet.
- **Data:** Yahoo Finance via `yfinance`.
- **Schedule:** GitHub Actions after the NSE close and mid-session, Mon-Fri. Output is deployed to the `gh-pages` branch.

Educational and research use only. Not financial advice. Prices in INR.
