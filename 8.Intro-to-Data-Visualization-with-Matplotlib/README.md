# Introduction to Data Visualization with Matplotlib
### Course Description
Visualizing data in plots and figures exposes the underlying patterns in the data and provides insights. Good visualizations also help you communicate your data to others, and are useful to data analysts and other consumers of the data. In this course, you will learn how to use Matplotlib, a powerful Python data visualization library. Matplotlib provides the building blocks to create rich visualizations of many different kinds of datasets. You will learn how to create visualizations for different kinds of data and how to customize, automate, and share these visualizations.

## Introduction to Matplotlib
- Using the matplotlib.pyplot interface
    - fig, ax = plt.subplots()
    - plt.show()
- Adding data to an Axes object
    - ax.plot(seattle_weather["MONTH"], seattle_weather["MLY-PRCP-NORMAL"])
    - ax.plot(austin_weather["MONTH"], austin_weather["MLY-PRCP-NORMAL"])
- Customizing data appearance
    - ax.plot(seattle_weather["MONTH"], seattle_weather["MLY-PRCP-NORMAL"], color="b", marker="o", linestyle="--")
    - ax.plot(austin_weather["MONTH"], austin_weather["MLY-PRCP-NORMAL"], color="r", marker="v", linestyle="--")
- Customizing axis labels and adding titles
    - ax.set_xlabel("Time (months)")
    - ax.set_ylabel("Precipitation (inches)")
    - ax.set_title("Weather patterns in Austin and Seattle")
- Small multiples with shared y axis
    - fig, ax = plt.subplots(2, 1, sharey=True)
    - ax[0].plot(seattle_weather['MONTH'], seattle_weather['MLY-PRCP-NORMAL'], color = 'b')
    - ax[0].plot(seattle_weather['MONTH'], seattle_weather["MLY-PRCP-25PCTL"], color = 'b', linestyle = '--')
    - ax[0].plot(seattle_weather['MONTH'], seattle_weather['MLY-PRCP-75PCTL'], color = 'b', linestyle = '--')

## Plotting time-series
- Read data with a time index
    - climate_change = pd.read_csv("climate_change.csv", parse_dates=["date"], index_col="date")
- Plot time-series data
    - ax.plot(climate_change.index, climate_change["relative_temp"])
    - ax.set_xlabel("Time")
    - ax.set_ylabel("Relative temperature (Celsius)")
- Using a time index to zoom in
    - seventies = climate_change["1970-01-01":"1979-12-31"]
- Plotting two variables
    - ax.plot(climate_change.index, climate_change["co2"], color='blue')
    - ax2 = ax.twinx()
    - ax2.plot(climate_change.index, climate_change["relative_temp"], color='red')
- Defining a function that plots time-series data
    - def plot_timeseries(axes, x, y, color, xlabel, ylabel):
    - axes.plot(x, y, color=color)
    - axes.set_xlabel(xlabel)
    - axes.set_ylabel(ylabel, color=color)
    - axes.tick_params('y', colors=color)
- Using a plotting function
    - plot_timeseries(ax, climate_change.index, climate_change["co2"], "blue", "Time (years)", "CO2 levels")
- Annotating a plot of time-series data
    - ax.annotate('>1 degree', (pd.Timestamp('2015-10-06'), 1))
- Plotting time-series: putting it all together