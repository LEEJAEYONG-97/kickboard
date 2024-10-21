
# Shared Scooter Parking Improvement Project
The project goal is to analyze shared scooter towing data and parking zones to identify patterns of illegal and unauthorized parking, while capturing relevant footage to visually demonstrate the issues, ultimately seeking solutions for parking improvement.

![image alt](https://github.com/LEEJAEYONG-97/kickboard/blob/2fd67c70a1ef3ba3a76fb876959644cd7cba1873/data/img/wordcloud.jpg)

# Data Collection

**Comprehensive information on Seoul's bike-sharing system (따릉이 대여소)**:

  Rental Stations, Location, latitude, longitude

**Data on Seoul's electric scooter towing incidents**:

  Towing Incidents, Report date, address, type

**Current status of electric scooter parking zones in Seoul**:

  Parking Zones, Location, latitude, longitude

**Nationwide administrative district code information**:

  Administrative Codes, Address

**Source**: DATA.GO.KR

**Data common collection period**: July 2021 to September 2023

# Data Preprocessing Steps

1. **Date sorting**
2. **Type conversion**
3. **Missing value removal**

# EDA
**Exploratory Data Analysis (EDA)**
Chart of monthly confirmed cases and deaths

![image16](https://github.com/LEEJAEYONG-97/portfolio/blob/18685b37ed6c12806963fb97cff374a55bcf210e/app/static/images/eda.png)

![image3](https://github.com/LEEJAEYONG-97/portfolio/blob/18685b37ed6c12806963fb97cff374a55bcf210e/app/static/images/eda1.png)

Chart of confirmed cases and deaths by region

![image4](https://github.com/LEEJAEYONG-97/portfolio/blob/18685b37ed6c12806963fb97cff374a55bcf210e/app/static/images/eda2.png)

Chart of monthly confirmed cases and attendance figures

![image5](https://github.com/LEEJAEYONG-97/portfolio/blob/18685b37ed6c12806963fb97cff374a55bcf210e/app/static/images/eda3.png)

Chart of the number of games played without spectators by association

![image8](https://github.com/LEEJAEYONG-97/portfolio/blob/18685b37ed6c12806963fb97cff374a55bcf210e/app/static/images/eda4.png)

Chart of monthly attendance figures by sports association

![image9](https://github.com/LEEJAEYONG-97/portfolio/blob/18685b37ed6c12806963fb97cff374a55bcf210e/app/static/images/eda5.png)
![image12](https://github.com/LEEJAEYONG-97/portfolio/blob/18685b37ed6c12806963fb97cff374a55bcf210e/app/static/images/eda6.png)
![image13](https://github.com/LEEJAEYONG-97/portfolio/blob/18685b37ed6c12806963fb97cff374a55bcf210e/app/static/images/eda7.png)
![image14](https://github.com/LEEJAEYONG-97/portfolio/blob/18685b37ed6c12806963fb97cff374a55bcf210e/app/static/images/eda8.png)
![image15](https://github.com/LEEJAEYONG-97/portfolio/blob/18685b37ed6c12806963fb97cff374a55bcf210e/app/static/images/eda9.png)

Number of films released and number of screening theaters by year
![image17](https://github.com/LEEJAEYONG-97/portfolio/blob/18685b37ed6c12806963fb97cff374a55bcf210e/app/static/images/eda10.png)
# Model Design

1. **Data Preparation**
   - Confirm data characteristics
   - Handle missing values
   - Extract variables

2. **Input and Prediction Variable Setup**
   - Set up input and prediction variables
   - Create sequence data

3. **Data Normalization**
   - Apply MinMaxScaler for normalization
   - Encode categorical variables

4. **Data Splitting**
   - Split the data into training (80%) and testing (20%) sets

5. **Model Comparison**
   - Compare MSE and R² Score among four models (LSTM, VAR, SARIMA, ARIMA)

6. **Prediction Results Validation**
   - Validate the prediction results

7. **Web Implementation of Prediction Model**
   - Implement the prediction model as a web service

# Models

### LSTM (Long Short-Term Memory)
LSTM is a type of recurrent neural network (RNN) designed to model time series data and sequences. It addresses the problem of vanishing gradients in standard RNNs by using memory cells that can maintain information over long periods. This makes LSTM particularly effective for tasks like speech recognition, language modeling, and time series forecasting, where past information is crucial for making predictions.

### ARIMA (AutoRegressive Integrated Moving Average)
ARIMA is a popular statistical model used for forecasting time series data. It combines three components: 
- **AutoRegressive (AR)**: uses the relationship between an observation and a number of lagged observations.
- **Integrated (I)**: involves differencing the data to make it stationary (constant mean and variance).
- **Moving Average (MA)**: uses the dependency between an observation and a residual error from a moving average model.

ARIMA is well-suited for univariate time series forecasting, particularly when the data shows trends or seasonality.

### SARIMA (Seasonal AutoRegressive Integrated Moving Average)

**SARIMA** is an advanced time series forecasting model that incorporates seasonal effects alongside the features of the ARIMA model. It is particularly useful for datasets exhibiting seasonality, trends, and non-stationarity.

**Components:**
- **Seasonal (S)**: Captures seasonal patterns in the data, allowing the model to adjust for fluctuations that occur at regular intervals.
- **AutoRegressive (AR)**: Models the relationship between an observation and a specified number of lagged observations (previous time points).
- **Integrated (I)**: Involves differencing the data to achieve stationarity, which means the mean and variance of the series remain constant over time.
- **Moving Average (MA)**: Accounts for the relationship between an observation and a residual error from a moving average model applied to lagged observations.

**Model Specification:**
A SARIMA model is typically expressed as SARIMA(p, d, q)(P, D, Q, s), where:
- **p**: Order of the autoregressive component.
- **d**: Degree of differencing.
- **q**: Order of the moving average component.
- **P**: Order of the seasonal autoregressive component.
- **D**: Degree of seasonal differencing.
- **Q**: Order of the seasonal moving average component.
- **s**: Length of the seasonal cycle (e.g., 12 for monthly data).

**Applications:**
SARIMA is widely used for forecasting in various fields, including finance, economics, and environmental science, where data shows both trends and seasonal variations.

### VAR (Vector AutoRegression)

**VAR** is a statistical model used to capture the linear interdependencies among multiple time series. It is particularly useful when you want to model and forecast systems with multiple variables that influence each other.

**Components:**
- **Multivariate**: VAR models multiple time series simultaneously, allowing for interactions among the variables.
- **Lagged Relationships**: Each variable in the model is regressed on its own lagged values and the lagged values of all other variables in the system.

**Model Specification:**
A VAR model is typically expressed as VAR(p), where:
- **p**: Number of lags used in the model.

**Applications:**
VAR is widely used in econometrics and finance for forecasting, policy analysis, and understanding the dynamic relationships between variables such as GDP, interest rates, and inflation.

# Model Evaluation
Performance comparison of the LSTM multivariate time series model

||mse|R^2SCORE|
|:---:|:---:|:---:|
|<span style="color:red">LSTM</span>|1.3911326|0.999952|

Performance comparison of the ARIMA time series model

||mse|R^2SCORE|
|:---:|:---:|:---:|
|attendance|90915449.756|-8059363882.537|
|screen_cnt|31337.131|-2780133.524|
|total_sales|1.2273164|-4.3081347|
|audience|107229772671.164|-5459062054041.54|

Performance comparison of the SARIMA time series model

||mse|R^2SCORE|
|:---:|:---:|:---:|
|attendance|90858232.219|-8054291730.872|
|screen_cnt|31676.808|-2810268.624|
|total_sales|1.25505872|-4.405515|
|audience|110191715359.747|-5609854399625.223|

Performance comparison of the VAR multivariate time series model

||mse|R^2SCORE|
|:---:|:---:|:---:|
|VAR|5.239956|-0.332326|

Comparison of MSE and R² Score among the four models:

- **MSE**: LSTM > VAR > SARIMA > ARIMA  
- **R² Score**: LSTM > VAR > SARIMA > ARIMA  

The LSTM model demonstrates the best performance, as it has the highest MSE and R² Score.

# Web structure

![image7](https://github.com/LEEJAEYONG-97/portfolio/blob/18685b37ed6c12806963fb97cff374a55bcf210e/app/static/images/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%A8%EA%B5%AC%EC%A1%B0%EB%8F%84.png)

# WebService
![image10](https://github.com/LEEJAEYONG-97/portfolio/blob/18685b37ed6c12806963fb97cff374a55bcf210e/app/static/images/web2.png)

