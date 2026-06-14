# ⚫ Black-Scholes Options Pricing Model

A quantitative finance project that downloads real NVDA stock data, estimates historical volatility, prices European options using Black-Scholes, and analyzes the Greeks.

![Python](https://img.shields.io/badge/Python-3.9%2B-3776AB?style=flat&logo=python)
![SciPy](https://img.shields.io/badge/SciPy-1.10%2B-8CAAE6?style=flat)
![Data](https://img.shields.io/badge/Data-Real%20NVDA%20Prices-76b900?style=flat)

-----

## 📡 Real Data

Downloads NVDA daily prices via **yfinance** and computes σ from real daily log-returns. If unavailable, falls back to verified published NVDA annual returns.

|Parameter             |Value                           |Source                               |
|----------------------|--------------------------------|-------------------------------------|
|Current Price         |$204.04                         |Robinhood / Investing.com, Jun 7 2026|
|Historical Vol (5Y)   |~129%                           |Computed from daily log-returns      |
|Risk-Free Rate        |4.5%                            |US Treasury yield, Jun 2026          |
|Annual Returns 2020-24|+122%, +125%, −50%, +239%, +171%|FinanceCharts / Macrotrends          |

-----

## 📐 What Black-Scholes Does

Gives a formula to price European call and put options:

```
Call price = S·N(d₁) − K·e^(−rT)·N(d₂)
Put  price = K·e^(−rT)·N(−d₂) − S·N(−d₁)
```

And computes 5 Greeks that tell you how the price reacts to changes in the market.

-----

## 🚀 How to Run

```bash
pip install -r requirements.txt
python black_scholes.py
```

-----

## 📊 Outputs

```
figures/
  fig1_nvda_overview.png   # Annual returns bar chart + price vs. strike
  fig2_sensitivity.png     # Vol sensitivity, theta decay, delta, vega
  fig3_greeks.png          # All 5 Greeks across stock price range

outputs/
  nvda_options.csv         # Prices and Greeks for all contracts
```

-----

## 📂 Project Structure

```
black-scholes/
├── black_scholes.py    # Main script
├── requirements.txt
├── README.md
├── figures/
└── outputs/
```

-----
## Sample Results

![Overview](figures/fig1_nvda_overview.png)

![Sensitivity Analysis](figures/fig2_sensitivity.png)

![Greeks](figures/fig3_greeks.png)

--------

## 👤 Author

**Jahari Lockett** — Data Science & Analytics, Florida Atlantic University
[LinkedIn](https://www.linkedin.com/in/jahari-e-lockett-b4aa04246/) · [lockettj2023@fau.edu](mailto:lockettj2023@fau.edu)
