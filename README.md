# STOCK-PRICE-FORECASTING-FOR-AN-INTEGRATED-OIL-GAS-COMPANY-IMPERIAL-OIL-LIMITED-
Forecasting Imperial Oil’s (IMO) stock price using machine learning models based on crude oil prices, CAD/USD exchange rates, and EV adoption trends. Includes data preprocessing, feature engineering, model comparison, and insights on key predictors.
This project builds a predictive analytics model to forecast the daily stock price of Imperial Oil Limited (IMO) by analyzing a combination of crude oil prices, macroeconomic indicators, and electric vehicle (EV) adoption trends in Canada. Using advanced data preprocessing, statistical modeling, and machine learning, the project identifies the most influential factors affecting IMO’s valuation and delivers a robust forecasting solution for the Canadian energy sector.

**#Project Overview**
Imperial Oil Limited operates in an industry heavily influenced by global oil markets, currency fluctuations, and the transition toward sustainable transportation.
This project aims to:
- Predict IMO’s daily closing price using multi-source time-series data
- Compare linear regression and Random Forest models
- Determine which variables have the strongest impact on stock price volatility
- Provide data-backed insights useful for investors, analysts, and policymakers


**Data Sources**
| Dataset                                 | Source                         |
| --------------------------------------- | ------------------------------ |
| IMO Stock Price                         | Yahoo Finance                  |
| Crude Oil Price (WTI)                   | Yahoo Finance                  |
| CAD/USD Exchange Rate                   | Yahoo Finance                  |
| Canadian Annual Car Sales (EV & Non-EV) | Our World in Data              |
| Fuel Price Data                         | Government of Canada Open Data |

Canadian car sales data (1995–2025) was extended using interpolation, seasonal adjustments, and a randomized daily distribution method to create a realistic high-frequency daily dataset.


**Data Preprocessing**
- Cleaned and merged time-series datasets
- Synchronized date indices across all sources
- Generated synthetic daily car sales (EV & non-EV)
- Created features for seasonality:
- Month_sin / Month_cos
- Weekday_sin / Weekday_cos
- Handled missing values through forward fill and interpolation
- Added lag features for market delay effects
- Feature scaling using StandardScaler

**Exploratory Data Analysis**
Key findings from correlation and statistical testing:
- Crude oil prices (WTI) show the strongest positive correlation with IMO stock price
- EV sales show a moderate correlation, reflecting emerging energy-transition effects
- CAD/USD exchange rate shows weak but meaningful influence
- Non-EV sales have almost no impact on IMO’s stock value

**Model Development**
**1. Linear Regression**
A baseline model to measure linear relationships.
- R²: 0.628
- RMSE: ~8.05
Strongest coefficients:
- Crude Oil Close
- CAD/USD Exchange Rate

**2. Random Forest Regressor (Best Model)**
Captures nonlinear relationships and complex interactions.
- R²: 0.9707
- RMSE: 2.26
Feature Importance Ranking:
- Crude Oil Price (WTI)
- CAD/USD Exchange Rate
- Seasonal Patterns
- EV Sales
- Non-EV Sales
Random Forest reduced prediction error by over 70% compared to linear regression.

**Hypothesis Testing**
Grouped predictors were tested to measure their significance:
| Variable Group                   | ΔR² Contribution | Conclusion       |
| -------------------------------- | ---------------- | ---------------- |
| **Crude Oil Prices**             | +38.2%           | Most influential |
| **Macroeconomic Factors**        | +11.1%           | Significant      |
| **Energy Transition (EV Sales)** | +4.7%            | Emerging impact  |




