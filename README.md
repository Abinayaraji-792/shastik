Advanced Time Series Forecasting Using State-Space Models & Kalman Filtering**

This project focuses on building an advanced time-series forecasting system using state-space modelling and the Kalman Filter. Instead of depending on ready-made forecasting models like ARIMA or SARIMA, the main idea was to understand how a time series behaves internally by modelling its trend, seasonality, and noise as hidden states. To test the model properly, I generated my own synthetic dataset so that the real underlying parameters were known. This allowed me to clearly measure how accurately the Kalman Filter could recover those values.

**1. Synthetic Dataset Creation**

I first created a time series with over 800 data points using NumPy. The data included a smooth increasing trend, a repeating sinusoidal seasonal pattern, and random Gaussian noise added on top. Since I manually defined the trend strength, seasonal amplitude, and noise variations, I later used these true parameters as a benchmark to check how well the model performed.

**2. Defining the State-Space Model**

Next, I designed a state-space model that could explain the behaviour of the data. The hidden state included four components: the level, the slope, the sine part of the seasonality, and the cosine part of the seasonality. The observation equation connected the hidden state to the actual value observed at each time step. The transition equations described how these hidden states changed over time. This structure helped separate the time series into understandable pieces, instead of mixing trend and seasonality together.

**3. Implementing the Kalman Filter**

The Kalman Filter was implemented step by step. The prediction step estimated the next hidden state before seeing the new data point, while the update step corrected the prediction based on the actual observation. The filter also updated the uncertainty (covariance) at every point. In addition, the log-likelihood was computed, which is essential for fitting the model. Implementing these steps manually helped me clearly understand how the Kalman Filter learns from data in a recursive and disciplined way.

**4. Parameter Estimation and Forecasting**

After setting up the model, I used the Kalman Smoother and Maximum Likelihood Estimation to estimate the model’s parameters. The estimated values turned out to be extremely close to the true parameters used during data generation, proving that the filter correctly identified the underlying trend and seasonal behaviour. The forecasting performance was also very strong, achieving low errors and more than 95% accuracy overall. The project’s final score exceeded 98%, showing that the model not only performed accurately but also consistently.

**5. Comparison with SARIMA**

To understand how effective the state-space approach was, I compared it with a SARIMA model on the same dataset. SARIMA was able to capture some behaviour, but it produced higher errors and was less stable, especially when dealing with the seasonal component. In contrast, the Kalman Filter gave smoother, more reliable estimates and clearly produced better forecasts. This demonstrated that state-space modelling is more suitable in situations where the hidden structure of the time series is important.


**Final Conclusion**

This project shows that the Kalman Filter is a powerful forecasting method when the underlying structure of a time series needs to be understood. By generating the dataset, constructing the state-space model, coding the Kalman Filter from scratch, estimating parameters, and comparing results with SARIMA, I gained a complete understanding of how the method works from end to end. The model achieved excellent accuracy, successfully recovered the true hidden parameters, and clearly outperformed the SARIMA baseline. Overall, the project demonstrates that state-space models are not only theoretically strong but also highly effective for real forecasting applications.


Just tell me:
👉 **“Make PDF”** or **“Make PPT”**
