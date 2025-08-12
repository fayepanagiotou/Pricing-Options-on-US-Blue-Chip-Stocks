# Pricing Plain-Vanilla Options on US Large-Cap Blue-Chip Stocks

**Author:** Faye Panagiotou ([faye.panagiotou@hec.edu](mailto:faye.panagiotou@hec.edu))  
**Degree:** MSc International Finance, HEC Paris  

## 📌 Overview
This project performs **quantitative analysis of option prices** under different market dynamics, simulating conditions as they might be monitored on a **Sales & Trading (S&T) desk**.  
It compares three option pricing models - **Black-Scholes (1973)**, **Heston (1993)** and **Bates (1996)** - using historical stock data from 6 major US blue-chip equities.  

The analysis uses **Monte Carlo simulations** to price European call options, followed by a **scenario analysis** to observe the sensitivity of option prices to shocks in the underlying spot price.

---

## 🛠 Models Implemented
1. **Black–Scholes Model (1973)**  
   - Assumes constant volatility and risk-free rate.
   - Closed-form solution for European options.

2. **Heston Model (1993)**  
   - Stochastic volatility framework where variance follows a mean-reverting process.
   - Captures volatility clustering and skew/smile effects.

3. **Bates Model (1996)**  
   - Extension of Heston with jump components in the asset price.
   - Models sudden price movements and fat-tailed return distributions.

---

## 📊 Methodology
1. **Data Collection**  
   - Historical price data for: AAPL, MSFT, GOOGL, AMZN, META, NVDA.  
   - Source: [Investing.com](https://www.investing.com/) via `investpy` API.
   - Date range: 01/01/2024 to 01/01/2025.

2. **Simulation**  
   - Monte Carlo path generation for each model:
     - **Black–Scholes**: Geometric Brownian Motion.
     - **Heston**: Mean-reverting variance process with correlation to price.
     - **Bates**: Heston + jump diffusion process.
   - 6-month maturity (\(T = 0.5\) years), strike price = **105% of spot**, risk-free rate \(r = 2\%\).

3. **Scenario Analysis**  
   - Spot shocks tested: **-20%, -10%, -5%, 0%, +5%, +10%, +20%**.
   - Option prices computed for each shock and model.
   - Results expressed as **PnL change relative to the baseline (0% shock)**.

---

## 📈 Key Outputs
- **Historical Price Chart** - visualizes 1-year performance of all 6 stocks.
- **PnL vs Spot Shock Charts** - for each stock, compares how Black–Scholes, Heston and Bates respond to spot changes.
