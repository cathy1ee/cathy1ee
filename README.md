<h1 align="center">Catherine Lee</h1> <p align="center"> <b>Quant Trading · Statistics · Software Engineering</b> </p>

#### About

I build trading systems from the ground up, with a focus on quantitative trading, statistics, and low-latency C++. I've been studying markets since I was 8; now I write the code behind them: a limit order book and matching engine, a market-making simulator, and an options pricing engine.




#### Featured projects

#### [Market-Making Simulator](https://github.com/cathy1ee/market-making-simulator)
Avellaneda–Stoikov market-making simulator comparing 3 quoting strategies (fixed spread, inventory-skewed, adaptive EWMA volatility) on identical markets across 81 parameter configurations.
- 1.2M simulated sessions (243M time steps) in ~20s; NumPy vectorization is 28× faster than a Python loop, matching to 3e-13- Inventory-aware quoting beat fixed spreads on Sharpe in 81/81 configurations (median 1.8), cutting max drawdown 76% while keeping 93.5% of P&L
- Reproduces the paper's baseline (Sharpe 4.8 → 8.9, inventory std 8.0 → 2.9)
- Regime-switching test: adaptive volatility estimation lifts Sharpe 6.6 → 7.6 at low risk aversion but backfires at high γ, where estimate noise is amplified by γσ²

`Python` · `NumPy` · `pandas`

#### [Options Pricing Engine](https://github.com/cathy1ee/options-pricing-engine)
European option pricer in C++17 (standard library only) that prices three ways and cross-checks them.
- Black–Scholes closed form at ~18.6M prices/sec (~54 ns each, single-threaded)
- Analytic Greeks (Δ, Γ, ν, Θ, ρ), validated against finite differences (max relative error 1.35e-5)
- Monte Carlo under GBM with antithetic variates, cutting variance ~50%; convergence slope −0.465 vs. theoretical −0.5
- 1,562 automated checks across 240 option configurations (put-call parity to 1e-10, Hull textbook values)

`C++17` · `Make`

#### [High-Frequency Market Microstructure & Order Book Analysis](https://github.com/cathy1ee/REPO-NAME)
End-to-end analysis of message-level limit order book data (LOBSTER format). SQL computes the microstructure measures from every order event; R fits the models and generates the report.
- Order Flow Imbalance (Cont–Kukanov–Stoikov) explains ~58% of 10-second mid-price changes
- Queue imbalance predicts the direction of the next mid-price move ~60% of the time
- Price impact by trade size (square-root law fit), effective/realized spread decomposition, Roll spread
- Volatility signature plot showing bid-ask bounce in high-frequency trade prices

`R` · `SQL` · `SQLite` · `ggplot2`

#### Tech stack

**Languages**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat&logo=cplusplus&logoColor=white)
![R](https://img.shields.io/badge/R-276DC3?style=flat&logo=r&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat&logo=mysql&logoColor=white)

**Data & ML**

![pandas](https://img.shields.io/badge/pandas-150458?style=flat&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat&logo=jupyter&logoColor=white)
![ggplot2](https://img.shields.io/badge/ggplot2-276DC3?style=flat&logo=r&logoColor=white)

**Tools**

![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)
![Git](https://img.shields.io/badge/Git-F05032?style=flat&logo=git&logoColor=white)
![CMake](https://img.shields.io/badge/CMake-064F8C?style=flat&logo=cmake&logoColor=white)

#### Contact

[Email](mailto:catherinelee693@gmail.com)

