CPI Forecasting with Machine Learning

BLUF (Bottom Line Up Front)

This project leverages machine learning, particularly Linear Regression and Ridge Regression, to forecast the U.S. Consumer Price Index (CPI) up to 12 months in advance using key macroeconomic indicators. By incorporating lagged features, time-aware cross-validation, and recursive forecasting, the model captures inflation momentum and delayed economic effects. The results indicate a consistent upward trend in CPI under stable monetary conditions, with Ridge Regression providing smoother and more conservative forecasts.

Project Overview

Inflation plays a critical role in shaping interest rates, consumer spending, investment strategies, and public policy. However, forecasting inflation is inherently difficult due to the time-lagged and interconnected nature of macroeconomic variables. This project addresses that challenge by:

Developing a CPI forecasting model that predicts monthly CPI up to 12 months ahead.

Exploring how changes in the Fed Funds Rate impact short- and medium-term inflation forecasts.

Evaluating model performance using time series-aware techniques such as TimeSeriesSplit.

Using recursive forecasting to simulate CPI trends under fixed monetary conditions.

Key insights include:

Lag features and economic inertia are vital for accurate short-term CPI forecasts.

Higher Fed Funds Rates in the model's training data coincided with higher inflation, leading to a counterintuitive positive relationship in predictions.

Ridge Regression's regularization smooths volatility and prevents overfitting, producing more stable forecasts.

Models Used

Linear Regression: Used as a baseline model due to its simplicity and interpretability.

Ridge Regression: Adds L2 regularization to reduce overfitting and manage multicollinearity among lagged variables.

Both models showed strong performance, with R² scores exceeding 0.99 on short-term forecasts.

Data Description & Preprocessing

Sources

Data was compiled from Federal Reserve Economic Data (FRED) and includes the following key indicators:

Consumer Price Index (CPI)

Fed Funds Rate

M2 Money Supply

10-Year Treasury Yield

GDP, Unemployment Rate, Sticky Inflation (included but not always used in all models)

Preprocessing Steps

The original data was in daily format and resampled to monthly frequency.

Start date was set to January 1981 to ensure inclusion of all macroeconomic variables.

For daily series like the 10-Year Treasury Yield, month-end values were used.

Lagged features were created (e.g., CPI_lag1, FedFundsRate_lag3, etc.) to capture inflation momentum and delayed policy effects.

Missing values were dropped after lagging.

Forecasting Method

Recursive Forecasting: Each predicted CPI value is used as input for the next month’s forecast.

Fixed Fed Funds Rate Scenario: Forecasts were generated with the Fed Funds Rate held constant to isolate the impact of monetary policy.

Results Summary

Linear Regression forecasted slightly higher CPI values, more sensitive to short-term fluctuations.

Ridge Regression yielded smoother, more conservative forecasts due to regularization.

Both models agreed on a consistent upward trend in CPI, with Ridge projecting 333.64 by July 2026 versus Linear Regression's 334.13.

Recursive forecasts under different Fed Rate scenarios (1.0% to 7.0%) showed inflation continuing to rise even with higher rates, reflecting model training on recent data patterns.
