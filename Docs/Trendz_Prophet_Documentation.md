# Forecasting Using Prophet Model in Trendz Analytics

## **Overview** 

Trendz Analytics provides built-in instruments for time-series prediction. All necessary tasks, including data filtering, normalization, and model training, are performed in the background. You can enable prediction for any fields, including calculated ones.

## **Prophet Model:**
* Prophet (or “Facebook Prophet”) is an open-source library for univariate time series forecasting developed by Facebook.
* It implements an additive time series forecasting model that supports trends, seasonality, and holidays.
* The library provides automatic parameter management related to seasonality and data stationarity.

## **Steps**

1. **Login:**

    * The first step is to log in to Trendz Analytics using the same email and password as your ThingsBoard.cloud account.

2. **Load the Dataset:**

    * We are using a dataset from a sealing machine, which consists of the following columns: id, times, shift, status, Lower Vertical Sealing Temperature, Upper Vertical Sealing Temperature, Front/Right Horizontal Sealing Temperature, and Back/Left Horizontal Sealing Temperature.

    * Our objective is to forecast the future values of the Lower Vertical Sealing Temperature and Upper Vertical Sealing Temperature.

    * To load the dataset, you can choose to visualize the data in card, table, line, or other formats. In this tutorial, we will visualize the data in **Table** to view the Lower Vertical Sealing Temperature and Upper Vertical Sealing Temperature. Then, we will choose **Line** to visualize the data in a graph and make forecasts.

    ![alt text](<format data visualization.png>)

    * Data visualization with Table

    ![alt text](<vertical bawah 26-29 march.png>)

    * Data visualization with Line

    ![alt text](<vertical bawah 26-29 march line.png>)

3. Forecasting with Prophet:
    * Visualize data in **Line**

    * Enable the **Prediction** checkbox for the forecast field, as shown in the image marked with a green box.

    ![alt text](<checkbox pred.png>)

    * Select **PROPHET** as the prediction model or method.

    ![alt text](<choose prophet.png>)

    * Set the **Prediction Unit** to days

    * Specify the **Prediction Range** (e.g., 1 days for the next 1 days)

    ![alt text](<1 day pred.png>)

4. Forecast Results with Prophet:
    * Lower Vertical Sealing Temperature: The following image shows the forecast results using Prophet for the next 1 day for the Lower Vertical Sealing Temperature.
    ![alt text](<new line__03_26_2024—03_29_2024 23_59_59_999__hour.png>)

    * Upper Vertical Sealing Temperature: The following image shows the forecast results using Prophet for the next 1 day for the Upper Vertical Sealing Temperature.
    ![alt text](<forecast_Va temp.png>)



5. Evaluate the Forecast Model:
    * Use in-sample forecast: To evaluate the performance of the Prophet model, we use sample data divided into training and testing datasets. In our case, we use data from 5 days, where 4 days are used for training and 1 day for testing.
    * Manually evaluate the forecast model using Python in Google Colaboratory. The evaluation metrics we use to measure the model's performance are MAE, MSE, RMSE, and MAPE. Here are the evaluation metric results for the Prophet model:


        | Temperature | MAE | MSE | RMSE | MAPE |
        |:---:|:---:|:---:|:---:|:---:|
        | Lower Vertical | 33.125 | 1357.95 | 36.85 | 16.94 |
        | Upper Vertical | 35.5 | 1975.83 | 44.45 | 20.70 |


## Conclusion
By following these steps, you can leverage the Prophet model in Trendz Analytics for accurate time series forecasting. For more details, refer to the [Trendz Analytics Documentation ](https://thingsboard.io/docs/trendz/). 

