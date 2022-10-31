# Analysing-and-predicting-the-stock-prices-based-on-search-traffic
## Background of the project
I am working as growth analyst at MercadoLibre to an external site. With over 200 million users, MercadoLibre is the most popular e-commerce site in Latin America. I have been tasked with analysing the company's financial and user data in clever ways to help the company grow. So, I want to find out if the ability to predict search traffic can translate into the ability to successfully trade the stock.
## Clients' Requirements
In a bid to drive revenue, I will produce a Jupyter notebook that contains data preparation, analysis and  visualisations for all the time series data that the company needs to understand.Specifically, this notebook contain the following:
* Visual depictions of seasonality (as measured by Google Search traffic) that are of interest to the company.
* An evaluation of how the company stock price correlates to its Google Search traffic.
* A Prophet forecast model that can predict hourly user search traffic.
 ## My approach for the analysis. 
 ### Find Unusual Patterns in Hourly Google Search Traffic
 The data science manager enquired if the Google Search traffic for the company links to any financial events at the company. Or, does the search traffic data just present random noise? To answer this question, I had to pick out any unusual patterns in the Google Search data for the company, and connect them to the corporate financial events.
 To do so,I followed the below steps: 
 * Read the search data into a DataFrame, and then slice the data to just the month of May 2020. (During this month, MercadoLibre released its quarterly financial results.) Use hvPlot to visualise the results.
 * Calculate the total search traffic for the month, and then compare the value to the monthly median across all months.
### Mine the Search Traffic Data for Seasonality
The marketing department realises that they can use the hourly search data too. If they can track and predict interest in the company and its platform for any time of day, they can focus their marketing efforts around the times that have the most traffic. This will get a greater return on investment (ROI) from their marketing budget.
To that end, I want to mine the search traffic data for predictable seasonal patterns of interest in the company. To do so, I followed the below steps:
* Grouped the hourly search data to plot the average traffic by the day of the week (for example, Monday vs. Friday).
* Used hvPlot to visualise this traffic as a heatmap, referencing 'index.hour' for the x-axis and 'index.dayofweek for the y-axis.
* Grouped the search data by the week of the year.

### Relate the Search Traffic to Stock Price Patterns
During a meeting with people in the finance group at the company, I mentioned about my work on the search traffic data. They want to know if any relationship between the search data and the company stock price exists, and they ask if you can investigate.
The steps followed are as follows:
* Read in and plot the stock price data. Concatenate the stock price data to the search data in a single DataFrame.
* Note that market events emerged during 2020 that many companies found difficult. But after the initial shock to global financial markets, new customers and revenue increased for e-commerce platforms. So, I have sliced the data to just the first half of 2020 (2020-01 to 2020-06 in the DataFrame), and then used hvPlot to plot the data.
* Created a new column in the DataFrame named “Lagged Search Trends” that offsets, or shifts, the search traffic by one hour. Create two additional columns:
** “Stock Volatility”, which holds an exponentially weighted four-hour rolling average of the company’s stock volatility
** “Hourly Stock Return”, which holds the percentage of change in the company stock price on an hourly basis.
### Created a Time Series Model by Using Prophet.
Now, I need to produce a time series model that analyses and forecasts patterns in the hourly search data which was acheived using the below steps:
Markup :* Set up the Google Search data for a Prophet forecasting model.
        * After estimating the model, plot the forecast.
        * Plotted the individual time series components of the model to answer the following questions:
            ** What time of day exhibits the greatest popularity?
            ** Which day of the week gets the most search traffic?
            ** What's the lowest point for search traffic in the calendar year?
