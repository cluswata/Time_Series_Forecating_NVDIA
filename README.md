# Time_Series_Forecating_NVDIA
Forecasting NVIDIA stock prices using a seasonal and trend model.


Data Description
The dataset used for this analysis is the historical daily stock prices of NVIDIA (NVDA), a leading technology company specializing in graphics processing units (GPUs). The timeframe of the data, adjusted for splits and dividends, spans several years, typically from the date NVIDIA became publicly traded in 1999 up to the most recent available data in 2024. 
Data Source: NVIDIA - 25 Year Stock Price History | NVDA | MacroTrends
Forecast
For the forecast, we utilized a seasonal and trend decomposition model, specifically the seasonal decomposition using LOESS (STL) method provided by python’s statsmodels library. This model separates the time series into trend, seasonal, and residual components:
Trend: The underlying long-term movement in NVIDIA stock prices, capturing gradual increases or decreases over time.
Seasonal: Regular patterns or cycles that repeat over a specific period, such as yearly, quarterly, or monthly variations.
Residual: The remaining variation in the data after removing the trend and seasonal components, representing noise or irregular fluctuations.
Presentation-Ready Plots
The plots presented in this study illustrate the components of the decomposition plus:
Observed vs. Trend: This plot shows the observed daily closing prices of NVIDIA stock alongside the trend component (by STL and by the 50-day moving average commonly used in financial markets), highlighting the overall movement over time.
Seasonal Component: Displays the seasonal variations in NVIDIA stock prices, capturing any recurring patterns or cycles.
Residuals: Examines the residuals of the model, highlighting any remaining variability after accounting for trend and seasonal effects.
Data splits: The dataset was split into training/history (tdata) set and testing/future (fdata) set, ratio 75:25.

Uncertainty
Model Evaluation: To evaluate the model on testing data, measures, Mean Absolute Error (MAE), and Root Mean Squared Error (RMSE), were calculated to quantify the model's performance against the actual stock prices.
Residual Analysis: Residuals were examined to help understand the model's predictive errors. Persistent patterns or high variability in residuals may suggest that the model has not captured all the underlying structure in the data.


Numeric Tests beyond the eye:
Autocorrelation:  Correlation of a time series with a lagged version of itself, measures how each observation in a time series is related to its past observations.
Durbin - Watson Statistic: Tests for autocorrelation in the residuals of a regression or time series model. It ranges from 0 to 4, where a value near 2 indicates no autocorrelation and Values significantly different from 2 indicate the presence of autocorrelation.
Stationarity: A crucial assumption for many time series models, as it ensures that the statistical properties of the series do not change over time. Significant spikes in Autocorrelation Plot for Residuals at various lags suggests that there may still be patterns in the residuals that are not captured by the trend and seasonal components hence non-stationarity.
Augmented Dickey-Fuller (ADF) test: Used to determine whether a time series is stationary or not. If the test statistic is less than the critical value from the ADF distribution, we reject the null hypothesis (suggesting stationarity). However, if the test statistic is greater than the critical value, we fail to reject the null hypothesis (indicating non-stationarity).


Findings and Interpretation:
Trend and Seasonality: There is a visible and significant up-trend as well as seasonality in the NVDIA stock prices data. 
Autocorrelation: Positive value of the Durbin – Watson test (0.73) indicates positive autocorrelation present suggesting that past values may influence future values in a positive manner. 
Stationarity: Significant spikes were observed in the autocorrelation plot of residuals at various lags suggesting that there may still be patterns in the residuals that are not captured by the trend and seasonal components hence non-stationarity. This was confirmed by the Augmented Dickey-Fuller (ADF) test for stationarity (statistic = 3.65; p-value > 0.05).
Model Evaluation/goodness of fit: The Mean Absolute Error (MAE) of 18.74 indicates that, on average, the forecasts are off by approximately 18.74 units from the actual values. Since RMSE involves squaring the errors before taking the square root, it tends to penalize larger errors more heavily than MAE.  The RMSE value of 27.29 means that, on average, the forecasts deviated from the actual values by approximately 27.29 units.

What could have caused the sudden upward spike in the stock price?
The explanation for the spike after crossing over the forecast line following the second attempt may be attributed to strong earnings reports (fundamental data), declining inflation (economic data), the CHIPS and Science Act signed into law by the president (news) that may have acted as a catalyst for the semi-conductor industrial group stocks. Also, the stock price’s break-out of the formed “cup” (consolidation phase) of the famous “Cup and Handle” technical pattern may have contributed to the spike. Furthermore, the markets tend to favor the stocks that lead every sector/industrial group and NVDA was the group leader for the semi-conductors even though the company did not directly benefit from the CHIPS and Science Act.

Markets are assumed to be efficient, hence The Efficient Market Hypothesis (EMH), but human behavior and cognitive biases can lead to market inefficiencies, that invalidate forecasts/statistical models, such as overreaction or underreaction to news which can be exploited by skilled investors/traders.

Consequences of Model Errors:
The errors in the model, reflected in the residuals, have implications for forecasting NVIDIA stock prices:
Forecast Reliability: High residual errors indicate potential challenges in accurately predicting future stock prices. This uncertainty can impact financial decisions and risk assessments based on the forecast.
Structural Insights: Persistent patterns or non-random behavior in residuals suggest that additional factors or variables may influence NVIDIA stock prices, beyond those accounted for in the current model. Exploring and incorporating such factors could improve forecast accuracy.

Conclusion:
In conclusion, the seasonal and trend decomposition model provided valuable insights into the historical trends and patterns in NVIDIA stock prices. However, residual analysis indicates remaining uncertainty and potential for further model refinement. Continued monitoring and adjustment based on new data and insights will enhance the accuracy and reliability of future forecasts.
Cup and Handle Pattern: How to Trade and Target with an Example (investopedia.com)
Efficient Market Hypothesis (EMH): Definition and Critique (investopedia.com)

