# Week_10_Assignment - Unit 10—A Yen for the Future
![unit-10-readme-photo](https://user-images.githubusercontent.com/85688247/171132556-e64ecc4a-fdcb-4d09-8f33-07199dad0bd7.jpg)

In this project I aim to test several time series tools in order to predict future movements in the value of the Canadian dollar vs. the Japanese Yen. 

**Jupyter Notebooks:**

(i)***Time Series Notebook:*** in this notebook I first parse the historical futures price data for CAD/JPY and then go through several time series analysis tools. 

*Step by Step process:*
1. Decomposition using a Hodrick-Prescott filter (decompose the settle price into trend and noise).
2. Forecasting returns using an ARMA model.
3. Forecasting the exchange rate price using an ARIMA model.
4. Forecasting volatility with GARCH.



(ii)***Linear Regression Analysis:*** in this notebook I built a Scikit-Learn linear regression model to predict CAD/JPY returns with lagged CAD/JPY futures returns and categorical calendar seasonal effects.

*Step by Step process:*

1. Data preparation (creating returns and lagged returns, and splitting the data into training and testing data)
2. Fitting a linear regression model.
3. Making predictions using the testing data.
4. Out-of-sample performance.
5. In-sample performance.



