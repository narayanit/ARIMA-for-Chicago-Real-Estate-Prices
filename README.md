# Forecasting Chicago Housing Prices with ARIMA and SARIMA
Using ARIMA and SARIMAX to model Chicago's real estate prices

## Overview
This project explores how classical time-series models from Python's `statsmodels` library can be used to analyze and forecast housing prices in the Chicago real estate market.

The goal was twofold:

1. demonstrate the practical use of statistical software libraries for real-world forecasting, and  
2. predict housing prices as accurately as possible using ARIMA-style models.

The analysis focused on Chicago housing data at the zip-code level, with an investment-oriented framing: identifying useful forecasting insights for a buyer or investor working under practical budget constraints.

---

## Project Motivation
Real estate is often treated as a long-horizon investment, but local pricing patterns can still be studied with time-series methods to support better decisions.

This project was designed to answer a practical question:

> Can ARIMA-based forecasting help estimate future housing prices in Chicago well enough to support real estate investment decisions?

More specifically, the project considered a scenario involving:
- a purchase decision in 2020
- a budget under **USD 500,000**
- Chicago areas with historical average housing prices below the high-end luxury range

---

## Objectives
- Use `statsmodels` to implement ARIMA-style forecasting
- Prepare and reshape housing price time-series data for modeling
- Perform exploratory data analysis and visualization
- test for stationarity and autocorrelation
- apply seasonal modeling where appropriate
- compare expected vs predicted values
- evaluate forecast quality using **Mean Squared Error (MSE)**

---

## Methods Used

### 1. Data Preparation
The workflow began with importing the dataset and reshaping it into a format suitable for time-series analysis.

### 2. Exploratory Data Analysis
Basic EDA and visualization were used to inspect price trends over time and understand the structure of the data.

### 3. Seasonal Decomposition
A seasonal decomposition step was included to examine trend and seasonality in the housing price series.

### 4. Stationarity and Autocorrelation Testing
Before fitting ARIMA-family models, the project checked whether the time series behaved in a stationary way and examined autocorrelation patterns.

### 5. ARIMA / Seasonal ARIMA Modeling
The project used the `statsmodels` time-series framework to fit ARIMA-based models.

For ARIMA, the key parameters are:
- **p**: autoregressive order
- **d**: differencing order
- **q**: moving average order

Where seasonal structure was relevant, a **SARIMA-style** approach was applied across Chicago zip codes.

### 6. Forecasting
After fitting the model on training data, forecasts were generated using a **dynamic forecasting** approach.

### 7. Evaluation
Forecast quality was evaluated using **Mean Squared Error (MSE)** by comparing predicted values against expected values.

---

## Tools and Libraries
This project was built in Python using the following core libraries:

- **statsmodels** — statistical and time-series modeling
- **pandas** — data manipulation
- **numpy** — numerical computation
- **scipy** — scientific computing support
- **matplotlib** — plotting and visualization
- **patsy** — formula-based statistical modeling support
- **Jupyter / IPython** — interactive notebook workflow

---

## Why ARIMA?
ARIMA is a useful baseline model for time-series forecasting because it:

- works directly with historical observations
- can transform non-stationary data through differencing
- is widely used in forecasting tasks such as demand, prices, and financial series
- can perform reasonably well for **short-term forecasts**

This made it a good candidate for exploring real estate price prediction in a structured, statistical way.

---

## Key Findings
The project found that ARIMA-style modeling was useful for demonstrating forecasting workflow and statistical tooling, but prediction accuracy was limited.

The main reported result was a **high MSE on dynamic forecasts**, suggesting that the model did not predict future housing prices especially well in this setup.

In the project visualizations:
- the **predicted series** was shown in pink
- the **expected/actual series** was shown in blue

The gap between predicted and actual values indicated that the forecasting performance was weaker than desired.

---

## Interpretation
A high MSE does **not** necessarily mean the modeling workflow was useless.

Instead, it suggests a few practical realities:

- housing prices can be noisy and difficult to forecast
- long-horizon prediction is harder than short-horizon prediction
- dynamic forecasts often accumulate more error over time
- ARIMA-family models are sensitive to parameter selection
- seasonal structure alone may not be enough to explain price movement

In other words: the project succeeded as a modeling and software demonstration, even if the final predictive performance was not as strong as hoped.

---

## Limitations
Several limitations were identified in the project:

- **Parameter subjectivity**: choosing optimal `(p, d, q)` values is partly judgment-based
- **Weak long-term forecasting performance**: ARIMA tends to be stronger for short-term forecasting
- **Data demands**: reliable forecasting can require large, clean historical datasets
- **Compute cost**: these models can become time- and memory-intensive
- **Real-estate complexity**: housing prices may depend on factors not captured by a univariate time series alone

---

## Possible Improvements
If this project were extended, strong next steps would include:

- testing **SARIMAX** with exogenous variables such as:
  - interest rates
  - mortgage rates
  - local economic indicators
  - inventory or sales volume
- comparing against alternative models such as:
  - **Exponential Smoothing**
  - **Holt-Winters**
- using more systematic hyperparameter search
- evaluating performance by zip code and forecast horizon
- adding stronger feature engineering and richer validation

---

## Project Workflow Summary
1. Import libraries and housing dataset  
2. Reshape the data for time-series analysis  
3. Perform EDA and visualization  
4. Decompose the series to inspect seasonality  
5. Test stationarity and autocorrelation  
6. Fit ARIMA / SARIMA models with `statsmodels`  
7. Generate dynamic forecasts  
8. Compare predictions against actual values  
9. Evaluate model performance using MSE  
10. Interpret strengths, weaknesses, and investment relevance  

---

## Repository Note
The original notebook for this project is currently unavailable.

This README is a reconstruction based on the project slideshow and is intended to preserve:
- the original objective
- the modeling logic
- the software stack
- the forecasting workflow
- the key conclusions

If the notebook is recovered later, this README should be updated with:
- dataset source
- exact preprocessing steps
- model orders
- code snippets
- train/test split details
- final plots
- exact evaluation metrics

---

## Conclusion
This project demonstrates how `statsmodels` can be used to build an end-to-end time-series forecasting workflow for real estate data.

While the final forecasts were not highly accurate, the project remains valuable as:
- a practical application of ARIMA-family models
- a demonstration of statistical software usage
- an example of how forecasting can be applied to housing-market questions

It is best understood as a strong methodological project with room for improvement in predictive accuracy.

---

## Author
**Narayani Tulsian**  
Project focused on time-series forecasting, statistical modeling, and real estate price analysis in Chicago.
