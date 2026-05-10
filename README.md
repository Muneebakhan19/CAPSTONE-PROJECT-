# CAPSTONE-PROJECT-
AAPL Investment Analysis Suite: A Three-Pillar Quantitative Decision Engine
Author: Muneeba
Project Status: Capstone Project - May 2026

 Project Overview
This project builds an institutional-grade decision-making pipeline for stock investments. Instead of relying on sentiment or rumors, this suite uses mathematical modeling to answer two critical questions:
Directional Forecast: Where is the price likely to go in the next 5 days?
Capital Protection: What is the maximum I could lose in a single day?

 Three-Pillar Methodology
The system evaluates a stock using three distinct quantitative lenses:
Pillar 1: ARIMA + GARCH (Forecasting)
Uses ARIMA to capture the price trend.
Uses GARCH to model "Volatility Clustering" (market swings).
Pillar 2: Value at Risk (Risk Management)
Calculates the 95% confidence maximum loss on a PKR 100,000 investment.
Pillar 3: Net Present Value (Valuation)
Compares stock growth against a 12% annual bank hurdle rate to ensure "Economic Profit."

 Key Results
Directional Accuracy: 60.00% (Verified through 15-day backtesting).
Optimal Model: ARIMA(1, 0, 0).
Daily Risk Shield (VaR): PKR 2,856.85.
Profit-to-Risk Ratio: 0.9930 (Exceeding the 0.15 investment threshold).
Final Verdict: STRONG BUY
2. Technical Documentation (Methodology)
Use this for your Project Report or the "Methodology" section of your GitHub.
Step 1: Data Pre-processing
Stock prices are non-stationary. To make the data predictable, we convert "Closing Prices" into Log Returns. This removes the price scale and focuses on percentage changes.
Step 2: The Backtest (15-Day Validation)
We don't trust the model blindly. We first run it on the last 15 days of known data.
Logic: If the model predicts an upward move and the market actually went up, we mark it as Correct.
Result: Our model achieved 9 correct hits out of 15, giving us the confidence to forecast the future.
Step 3: The 5-Day Forecast
We combine the ARIMA trend with GARCH volatility. This allows us to create a "noisy" forecast that mimics real market behavior rather than a perfect straight line.

3. Mathematical Framework (The "Manual" Logic)
This section proves you understand the math behind the code.
Value at Risk (VaR) Calculation
We calculate the risk for a PKR 100,000 investment at a 95% confidence level.
Formula: VaR = Investment \times Z_{score} \times \sigma_{predicted}
Your Values: 100,000 \times 1.6449 \times 0.01736 = \mathbf{PKR 2,856.85}
Meaning: There is only a 5% chance that your loss will exceed this amount in a single day.
Net Present Value (NPV) & 12% Hurdle
We compare the stock to a bank deposit.
Daily Bank Rate: Since the bank gives 12% a year, the daily rate is roughly 0.047%.
Discounting: We take each day's forecasted profit and "pull it back" to today's value using that 0.047% rate.
Result: Your NPV is PKR 2,836.99. Because it is positive, the stock is officially "Beating the Bank."

5. Insights & Real-World Use Cases
Use this for your "Conclusion" or "Insights" slides/reports.
Institutional Practice: This logic (VaR + GARCH) is used by risk managers at major banks  to manage portfolio limits.
Robo-Advisory: This "Decision Engine" logic is the core of automated apps that give Buy/Sell signals.
Business Relevance: By setting a Profit-to-Risk Ratio (ours is 0.99), we ensure we only take trades where the reward justifies the risk.
6. Future Improvements (What to do next?)
Sentiment Analysis: Integrate news headlines to see if "Twitter/X hype" affects the ARIMA forecast.
Exogenous Variables: Add the State Bank of Pakistan (SBP) policy rate as an input to the model.
Portfolio Optimization: Instead of one stock, use this model to manage a "basket" of 5-10 stocks.
