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


## Time Series Analysis Results
***

After preparing the data and creating the dataframe of historical CAD/JPY price data, I decomposed this price data into trend and noise components using a Hodrick-Prescott Filter (HP filter). 

***ARIMA Model takeways:*** Based on the model results, we would expect the Japanese Yen to decline against CAD over the next 5 days. However judging from the pvalues, this is a poor model as none of the coefficients had p-values under our statistically significant threshold of 0.05.

***GARCH Model takeways:*** Based on the graph above, the forecast for CAD/JPY volatility is that it is expected to rise over the next 5 days. The p-values for the GARCH model are far lower than the ARMA/ARIMA. Outside the of the alpha(2) p-value, all are significant, indicating overall a much better model performance. In other words, forecasting future volatility (in the short term) is easier than future returns.

## Linear Regression Model 
***

After fitting the linear regresion model to the training data, I then used this model to predict future returns based on the test data. S

Out-of-Sample Root Mean Squared Error (RMSE): 0.6445

In-sample Root Mean Squared Error (RMSE): 0.8342

## Conclusion 
***

To conclude based on the RMSE values above, we can see that the model actually performed better on the out-of-sample data than the in-sample data. As the amount of out-of-sample data we use on this model increases, we should expect the out-of-sample RMSE to eventually become higher than the in-sample RMSE.

While the model seems to capture some of the direction of the actual CAD/JPY returns, the model fails to accurately predict the actual returns.