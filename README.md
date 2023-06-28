# GARCH-model-to-forecast-in-excel-
I apply fundamental knowledge related to the GARCH model to make forecast the volatility of return of 10 big firms in the IT industry
Build up GARCH (1,1) model using Maximum Likelihood to predict the volatility of return on stock prices of 10 firms. You could read the following steps to get more insight into forecasting with the GARCH model:

1. In the model, we have 03 parameters: alpha (α), beta (β), and gamma (γ). The sum of those parameters must be equal to 1. We will use those 03 parameters to compute the long-run average variance rate as the formula below:
![image](https://github.com/LinhNguyen-MyLi/GARCH-model-to-forecast-in-excel/assets/128978862/553e4dff-e0a5-464a-9c34-7abe6931af7f)
We set ![image](https://github.com/LinhNguyen-MyLi/GARCH-model-to-forecast-in-excel/assets/128978862/66e80769-0f73-4269-a8ad-ff1ef93d4bf0)  with VL stand for long run daily variance => the formula change into:
![image](https://github.com/LinhNguyen-MyLi/GARCH-model-to-forecast-in-excel/assets/128978862/47cf1121-7cd7-4210-b7ba-a2d8fec2ee36)
With sum of 03 parameters equal to 1 => γ=1- α- β we have the formula:
![image](https://github.com/LinhNguyen-MyLi/GARCH-model-to-forecast-in-excel/assets/128978862/15bf331f-4ff7-4e31-98f5-e18b7839a72f)
Before running the solver we assume the following initial values for α, β, ω as following:
![image](https://github.com/LinhNguyen-MyLi/GARCH-model-to-forecast-in-excel/assets/128978862/e3fb58d3-ab34-442a-93ad-c54c4489fff9)
Based on those initial values and the formula V, we calculate V_L (long run daily variance), then take the square root of V_L to obtain Long run daily Std, then by multiplying the Long run daily Std with square root of 250 (number of trading days in a year), we achieve its annual value.
The result for parameters before running the solver (DELL):

   
3. We use the maximum likelihood method in this case instead of regular regression cause in this case, our data (the volatility of the rate of return) tends to fluctuate over time, and in traditional regression, it is often assumed that the errors (or residuals) have constant volatility. In maximum likelihood methods, we choose parameters that maximize the probability of observing the given rate of return data, in other words, choose the parameter that maximizes the likelihood function below, this function measures the probability of obtaining the observed data: 
