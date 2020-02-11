# ULTA Project Report
## Stock Price History
The goal of this project was to prep data using Extract, Transform, Load (ETL) methodology to perform a deep dive of existing UTLA stock price history data using machine learning. The pre-existing data
allows a creation of analysis to make a prediction relative to future stock. 

We began the process by extracting the most valuable data points relative to stock history from the TD Ameritrade API, transforming the dataset with Python Pandas and Tableau for further analysis.
Below was our process:

### Extract/Data Utilized
The historical stock price data was received from TD Ameritrade website for developers (https://developer.tdameritrade.com). We structured a Resource URL using the TD Ameritrade API for the
ULTA stock symbol for price history from November 1, 2015 - February 4, 2020. The data was output in a JSON content type. More than 30,000 records were yielded from the API results. 

### Transformation
Once the dataset was extracted, the data was transformed using the Python Pandas - the following columns was used in in the transformation from the stock price history dataset:

- timestamp
- open
- high
- low
- close
- volume

Originally, a total of 10 years of historical data was yielded. However, due to delays in loading that was caused by the volume of data a smaller dataset of the aforementioned date range was used. 

### Load
Tableau was used with the fbprophet package to perform a machine learning forecast. Prophet is a procedure for forecasting time series data based on an mixed regression model with backend incorporation of
Scikit-Learn. This model takes non-linear, highly seasonal trends and fits daily data against yearly, weekly, and daily seasonality, plus holiday affects. Prophet is robust to missing data and shifts in the trend,
and typically handles outliers well. 

The code written utilizing the fbprophet package was then deployed to a local TabPy server. After deployment interactive visualizations were created in Tableau which update with every new load of data.
TabPy is a RESTful API framework that allows Tableau to remotely execute Python code. It has two components:

- A process built on Tornado, which allows for the remote execution of Python code through a set of REST APIs. The code can either be immediately executed or persisted in the server process and exposed
as a REST endpoint, to be called later.

- A tools library, based on Python functions which enables the deployment of such endpoints.

Tableau can connect to the TabPy server to execute Python code on the fly and display results in Tableau visualizations. Users can control data and parameters being sent to TabPy by interacting
with their Tableau worksheets, dashboard or stories.

### Next Steps
The next step in the process was to further analyze the cleaned dataset to identify any trends or patterns that were common among ULTA stock price data based on timeframe.

### Analyze
There are dramatic changes in the time series due to volatility of the stock market. 

### Visualize
Tableau was used to illustrate the correlation between open, high, low, close, volume and timestamp. 
