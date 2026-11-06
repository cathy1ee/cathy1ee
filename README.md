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

#### [High-Frequency Market Microstructure & Order Book Analysis](https://github.com/cathy1ee/lob-microstructure)
R + SQL pipeline analyzing message-level Nasdaq order book data (LOBSTER): SQL computes microstructure measures from every order event; R fits the models and generates the report.
- Order flow imbalance explains 83.5% of 10-second price changes in INTC vs. 50.1% in AAPL
- Queue imbalance predicts the next mid-price move 65.3% of the time in INTC (P(up) 0.19 → 0.78 across deciles) vs. 55.7% in AAPL
- Shows how tick size shapes order book informativeness: deep one-tick queues (INTC) vs. thin, wide-spread books (AAPL)
- Price impact by trade size, effective/realized spread decomposition, volatility signature, and a built-in order book simulator

`R` · `SQL` · `SQLite` · `ggplot2`

#### [Limit Order Book & Matching Engine](https://github.com/cathy1ee/limit-order-book)

Price-time priority limit order book and matching engine in C++20, built to be correct first and then fast.

- ~38M ops/s with 84 ns p99 latency; a memory pool, a flat price-level array with a bitmap scan, and intrusive lists give 1.5× the throughput and ~⅓ lower tail latency vs. a `std::map` baseline
- Replays a full day of Nasdaq TotalView-ITCH 5.0 (368M messages, 8,695 symbols) with zero crossed adds, off-touch executions, or unknown order refs, handling halts and reopening auctions
- Differential testing: 100k-op random order flows must match a reference book after every operation; GoogleTest under ASan/UBSan in CI
- Limit and market orders, O(1) cancel, and modify with correct queue-priority rules

`C++20` · `CMake` · `GoogleTest` · `GitHub Actions`

#### Tech stack

**Languages**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat&logo=cplusplus&logoColor=white)
![Rust](https://img.shields.io/badge/Rust-000000?style=flat-square&logo=rust&logoColor=white)
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

